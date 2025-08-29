# DDIM

Average score: 14.03 out of 17.25
Total score: 449 out of 552
Average time: 134.405 s / picture
Average time normalized: 125.88 s / picture *

DDIM stands for Denoising Diffusion Implicit Models. It is a type of sampler used in image generation models (like Stable Diffusion) to speed up the denoising process while preserving image quality.

DDIM is an acceleration technique introduced in 2021 by Jiaming Song et al. to generate images faster and with more control.
- It reduces the number of denoising steps needed (e.g., from 1000 to 20–50).
- Unlike standard samplers (like DDPM), which are stochastic (random), DDIM can work in a deterministic mode, meaning:
  - Given the same seed, prompt, and settings, it always gives the same image.
- It's a non-Markovian sampler, meaning each step depends on all previous steps, not just the immediate last one.

✅ Pros
- Fast image generation
- Deterministic (good for reproducibility)
- Less noisy than stochastic samplers
- Works without retraining the diffusion model

⚠️ Cons
- Sometimes less diverse than stochastic samplers
- May generate less fine detail than longer-step samplers like DPM++ with higher steps

I have used the following setup for DDIM:
- 5 prompts (you can find them here: https://github.com/gctanita/understandingImageGeneration/blob/master/experimentPrompts.md )
- Each prompt was generated 8 times with different seeds (each seed was used across each prompt)

For each image I gave it a score based on some on a set of subjective criteria designed to assess visual quality and consistency across different samplers. Each anomaly observed in the generated images deducted points from the total score, resulting in a binary scale (1 = acceptable, 0 = flawed). And for each image I recorded how much it took to generate them. Average normalized time means that I have eliminated the biggest 4 times from the series, that contained the loading of the model and / or parsing of the prompt for the first time. 

Hardware the setup:
- Graphic Card: NVIDIA GeForce RTX 4060 Ti with 8Gb VRAM 
- CPU: AMD Ryzen 5 5500, 3.60 GHz
- RAM: 32.0 GB, speed of 2400 MT/s 



