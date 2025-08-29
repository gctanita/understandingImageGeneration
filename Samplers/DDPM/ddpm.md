# DDPM

Average score: 5.43 out of 17.25
Total score: 174 out of 552
Average time: 130.58 s / picture
Average time normalized: 126.15 s / picture *

DDPM stands for Denoising Diffusion Probabilistic Models — and it's the original type of sampler used in diffusion models like Stable Diffusion.


Diffusion models start with random noise and iteratively denoise it step by step to produce an image. DDPM is:
- Stochastic → Adds random noise in every reverse step during generation.
- Markovian → Each step depends only on the previous step.
- Requires hundreds or even thousands of steps to get a high-quality image.
- The reverse denoising is based on learned noise predictions.


Mathematical Core
- The forward process adds Gaussian noise to the image over T steps.
- The reverse process (DDPM) tries to learn how to undo that noise using a neural network that predicts the original image or noise.
- It's trained to minimize a variational bound, ensuring the predicted noise closely matches the true noise.


✅ Pros
- High quality output with smooth transitions
- Well-tested and stable (it's the original method)
- Sets a baseline for comparing other samplers

⚠️ Cons
- Slower than optimized samplers like DDIM or DPM++
- Less control due to internal randomness
- Not ideal for low-step fast generation (20–30 steps)


𝙋𝙞𝙘𝙩𝙪𝙧𝙚 𝙜𝙚𝙣𝙚𝙧𝙖𝙩𝙞𝙤𝙣 𝙨𝙚𝙩𝙩𝙞𝙣𝙜𝙨:
- 4 prompts (you can find them here: https://github.com/gctanita/understandingImageGeneration/blob/master/experimentPrompts.md )
- Each prompt was generated 8 times with different seeds (each seed was used across each prompt)
- 𝙎𝙩𝙚𝙥𝙨: 20
- 𝘾𝙁𝙂: 3
- 𝙒𝙞𝙙𝙩𝙝: 512
- 𝙃𝙚𝙞𝙜𝙝𝙩: 512
- 𝙎𝙘𝙝𝙚𝙙𝙪𝙡𝙚𝙧: simple


You can find the raw data here: 
- https://github.com/gctanita/understandingImageGeneration/blob/master/Samplers/DDPM/ddpm-raw-data.md


Scoring criteria for each series can be found here:
- https://github.com/gctanita/understandingImageGeneration/blob/master/Samplers/scoring_criteria.md


Hardware the setup:
- Graphic Card: NVIDIA GeForce RTX 4060 Ti with 8Gb VRAM 
- CPU: AMD Ryzen 5 5500, 3.60 GHz
- RAM: 32.0 GB, speed of 2400 MT/s 


For each image I gave it a score based on some on a set of subjective criteria designed to assess visual quality and consistency across different samplers. Each anomaly observed in the generated images deducted points from the total score, resulting in a binary scale (1 = acceptable, 0 = flawed). And for each image I recorded how much it took to generate them. Average normalized time means that I have eliminated the biggest 4 times from the series, that contained the loading of the model and / or parsing of the prompt for the first time. 



