https://pytorch.org/docs/stable/generated/torch.nn.parallel.DistributedDataParallel.html#torch.nn.parallel.DistributedDataParallel

```python
torch.nn.parallel.DistributedDataParallel(_module_, _device_ids=None_, _output_device=None_, _dim=0_, _broadcast_buffers=True_, _process_group=None_, _bucket_cap_mb=25_, _find_unused_parameters=False_, _check_reduction=False_, _gradient_as_bucket_view=False_, _static_graph=False_, _delay_all_reduce_named_params=None_, _param_to_hook_all_reduce=None_, _mixed_precision=None_)
```

This container provides data parallelism by synchronizing gradients across each model replica.