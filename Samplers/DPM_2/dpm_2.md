# DPM_2

Average score: 14.03 out of 17.25
Total score: 449 out of 552
Average time: 246.04 s / picture
Average time normalized: 242.64 s / picture *


DPM_2 is a sampler used in image generation with diffusion models, and it's part of the DPM (Denoising Probabilistic Models) family — specifically one of the second-order solvers for accelerating and improving sampling.


How It Works
- In classic diffusion sampling (like DDPM), each denoising step uses simple first-order approximations (Euler method, etc.).
DPM_2, however:
- Uses a second-order solver (like Runge-Kutta-style methods).
- Looks at more than just the current step — it considers two prior states for a more accurate and stable update.
- Allows for fewer steps with better accuracy.
- Is usually paired with noise prediction models (like epsilon, v, or score types).


✅ Pros
- Better quality at low steps vs Euler or DDIM
- More stable edges and lighting
- Deterministic if configured properly (good for reproducibility)

⚠️ Cons
- Slightly slower than DDIM or Euler due to the second-order computation
- Can sometimes produce less contrast or flattened details if not well-tuned
- May not be optimal for abstract/artistic prompts that benefit from randomness


𝙋𝙞𝙘𝙩𝙪𝙧𝙚 𝙜𝙚𝙣𝙚𝙧𝙖𝙩𝙞𝙤𝙣 𝙨𝙚𝙩𝙩𝙞𝙣𝙜𝙨:
- 4 prompts (you can find them here: https://github.com/gctanita/understandingImageGeneration/blob/master/experimentPrompts.md )
- Each prompt was generated 8 times with different seeds (each seed was used across each prompt)
- 𝙎𝙩𝙚𝙥𝙨: 20
- 𝘾𝙁𝙂: 3
- 𝙒𝙞𝙙𝙩𝙝: 512
- 𝙃𝙚𝙞𝙜𝙝𝙩: 512
- 𝙎𝙘𝙝𝙚𝙙𝙪𝙡𝙚𝙧: simple


You can find the raw data here: 
- https://github.com/gctanita/understandingImageGeneration/blob/master/Samplers/DPM_2/dpm_2-raw-data.md


Scoring criteria for each series can be found here:
- https://github.com/gctanita/understandingImageGeneration/blob/master/Samplers/scoring_criteria.md


Hardware the setup:
- Graphic Card: NVIDIA GeForce RTX 4060 Ti with 8Gb VRAM 
- CPU: AMD Ryzen 5 5500, 3.60 GHz
- RAM: 32.0 GB, speed of 2400 MT/s 


For each image I gave it a score based on some on a set of subjective criteria designed to assess visual quality and consistency across different samplers. Each anomaly observed in the generated images deducted points from the total score, resulting in a binary scale (1 = acceptable, 0 = flawed). And for each image I recorded how much it took to generate them. Average normalized time means that I have eliminated the biggest 4 times from the series, that contained the loading of the model and / or parsing of the prompt for the first time. 
