## Why I read it

I read this paper because it introduces a continuous-time perspective for deep learning that replaces discrete layers with ordinary differential equations. This foundational framework forms the mathematical backbone for continuous normalizing flows and modern flow-matching / diffusion-based generative models.

## New Concept

**Adjoint Sensitivity Method** is a mathematical technique used to compute gradients for differential equations without needing to store intermediate steps in memory.

> **Why it matters:**
> * In standard deep learning, you store every layer's activations in memory to calculate backpropagation.
> * For Neural ODEs, the continuous nature means an ODE solver might take hundreds of tiny steps. Storing all of them would crash your memory.
> * The adjoint method solves this by **reconstructing the states backward in time** during the backward pass, trading a bit of extra computation time to keep memory usage constant ($O(1)$).