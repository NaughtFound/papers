## Why I read it
This is the paper that made diffusion practical. My thesis builds on it, so I wanted to re-read the training objective carefully.

## The idea
Gradually add Gaussian noise to an image over many steps, then train a network to reverse each step. The network predicts the noise that was added, and the loss is a plain mean squared error.

> The weighted variational bound is replaced by an unweighted version that puts more focus on harder denoising steps.

## What I would question
- Slow sampling. Later work such as DDIM trades steps for quality.
- No notion of cause and effect: the model learns correlations in pixels, which matters for medical images.

## Open question for the discussion
How would you inject a causal graph into the forward process without breaking the closed-form noising step?
