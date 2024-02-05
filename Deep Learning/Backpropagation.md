Backpropagation is a process of calibrating the weights of  [[Fully-connected (Linear) Layer]] through [[Computational Graph]]s.

## Properties
### Pros
- Simple (only estimate linear coefficient)
- Local (use unit's shared connections only)
- Well understood 
### Cons
- Slow (many weight updates)
- Unstable, overparametrized
- Non-convex error minimization (no unique solution)