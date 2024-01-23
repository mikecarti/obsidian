[torch.cuda.amp.GradScaler](https://pytorch.org/docs/stable/amp.html#torch.cuda.amp.GradScaler) - Automatic Gradient Scaling for writing compute efficient training loops. *Automated Mixed-Precision* (AMP) training.

## Why is it needed
Common error in any [[Deep Learning]] model is that gradients are too small to be taken into account. ```float16``` tensors often ignore extremely small variations. 

To prevent this, gradients are scaled by some factor to not be flushed to zero. Do not confuse with [[Vanishing Gradients]].


## Example
```
scaler = torch.cuda.amp.GradScaler()
optimizer = .﻿.﻿.
﻿
for epoch in range﻿(﻿.﻿.﻿.﻿)﻿:
    for i, sample in enumerate﻿(dataloader)﻿:
        inputs, labels = sample
        optimizer.zero_grad(﻿)
﻿
	# Forward Pass
        outputs = model(inputs)
        # Compute Loss and Perform Back-propagation
	loss = loss_fn(outputs, labels)
	
	# ⭐️ ⭐️ Scale Gradients
        scaler.scale(loss).backward()
	# ⭐️ ⭐️ Update Optimizer
	scaler.step(optimizer)
        scaler.update()
```

