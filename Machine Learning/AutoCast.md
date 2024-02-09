Get rid of OutOfMemory Errors by putting autocast, so the models would automatically be casted into floatX precision (int, float16, float32, etc)

```python
 optimizer = ...


for epoch in range(...):
    for i, sample in enumerate(dataloader):
        inputs, labels = sample
        optimizer.zero_grad()

        # ⭐️ ⭐️ Autocasting
	with torch.cuda.amp.autocast():
	    # Forward Pass
            outputs = model(inputs)
            # Compute Loss and Perform Back-propagation
	    loss = loss_fn(outputs, labels)

        loss.backward()
	# Update Optimizer
        optimizer.step()
```


## *autocast(enabled=False)*
`autocast(enabled=False)` subregions can be nested in autocast-enabled regions. Locally disabling autocast can be useful, for example, if you want to force a subregion to run in a particular `dtype`. Disabling autocast gives you explicit control over the execution type. In the subregion, inputs from the surrounding region should be cast to `dtype` before use:

```python
# Creates some tensors in default dtype (here assumed to be float32)
a_float32 = torch.rand((8, 8), device="cuda")
b_float32 = torch.rand((8, 8), device="cuda")
c_float32 = torch.rand((8, 8), device="cuda")
d_float32 = torch.rand((8, 8), device="cuda")

with torch.autocast(device_type="cuda"):
    e_float16 = torch.mm(a_float32, b_float32)
    with torch.autocast(device_type="cuda", enabled=False):
        # Calls e_float16.float() to ensure float32 execution
        # (necessary because e_float16 was created in an autocasted region)
        f_float32 = torch.mm(c_float32, e_float16.float())

    # No manual casts are required when re-entering the autocast-enabled region.
    # torch.mm again runs in float16 and produces float16 output, regardless of input types.
    g_float16 = torch.mm(d_float32, f_float32)
```