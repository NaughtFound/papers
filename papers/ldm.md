## Why I read it
Training in pixel space is too expensive for 3D scans. Latent diffusion is the standard fix.

## The idea
Train an autoencoder once, then train the diffusion model on its latent codes. Conditioning enters through cross-attention layers in the denoising network.

## Notes for medical imaging
- Reconstruction quality of the autoencoder sets a ceiling. Subtle lesions can disappear.
- Worth checking the latent space for anatomical structure before building on it.
