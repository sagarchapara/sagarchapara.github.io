---
title: "Visualizing Transformer Loss Landscapes"
categories:
  - research
  - transformers
tags:
  - optimization
  - visualization
excerpt: "What the curvature of a transformer loss surface can tell us about convergence and generalization."
---

Understanding how transformers traverse their loss landscape is critical for designing stable training schedules. In this note we derive the local quadratic approximation around a parameter snapshot and discuss how to interpret the resulting geometry.

## Hessian intuition

Given a model parameter vector $\theta$ and loss function $\mathcal{L}(\theta)$, the second-order Taylor expansion around a point $\theta_0$ is

$$
\mathcal{L}(\theta) \approx \mathcal{L}(\theta_0) + (\theta - \theta_0)^T \nabla \mathcal{L}(\theta_0) + \tfrac{1}{2} (\theta - \theta_0)^T H(\theta_0) (\theta - \theta_0),
$$

where $H(\theta_0)$ is the Hessian. The eigenvalues of $H(\theta_0)$ indicate the curvature along principal axes. Large positive eigenvalues signal sharp directions that may cause gradient descent to overshoot.

## Practical estimation

To estimate the top-$k$ eigenvalues in practice we can use stochastic Lanczos quadrature. The algorithm iteratively multiplies random probe vectors $v_i$ by the Hessian-vector product $H v_i$ using autograd:

```python
for i in range(k):
    v = sample_unit_vector()
    for _ in range(num_steps):
        v = normalize(hvp(model, loss_fn, batch, v))
    eigenvalue = rayleigh_quotient(v, hvp(model, loss_fn, batch, v))
    spectrum.append(eigenvalue)
```

The resulting spectrum helps you tune learning rates and weight decay, especially when fine-tuning large language models.
