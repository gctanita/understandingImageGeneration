# EULER

Average score:	14.13	out of 17.25
Total score:	452	out of 552
Average time: 	132.70	s / picture
Average time normalized:	126.50	s / picture *


Euler is a first-order deterministic sampler used in diffusion-based image generation. It’s one of the simplest and fastest samplers, based on the classic Euler method for solving differential equations. It produces sharp, high-contrast images but tends to be less stable at high CFG values and may introduce artifacts or distortions at times. It’s commonly used for quick prototyping or when you want fast, punchy results.


About
- The Euler method is a numerical technique for solving ordinary differential equations (ODEs).
- In the context of diffusion models, it’s used to step through the denoising process in a simple, direct way.
- It's a deterministic sampler, meaning same seed + prompt = same output
- 20–30 steps (higher may cause over-sharpening or banding)
- Very fast
- Works with epsilon or v-prediction models


✅ Pros
- Extremely fast
- Produces sharp, bold images
- Deterministic (reliable for reproducibility)
- Great for batch generation, testing prompts, or lower-resource environments

⚠️ Cons
- Can hallucinate or distort fine features (faces, hands) at higher CFG
- Lower realism compared to DPM++ samplers
- Not ideal for subtle lighting, gradients, soft shadows


𝙋𝙞𝙘𝙩𝙪𝙧𝙚 𝙜𝙚𝙣𝙚𝙧𝙖𝙩𝙞𝙤𝙣 𝙨𝙚𝙩𝙩𝙞𝙣𝙜𝙨:
- 4 prompts (you can find them here: https://github.com/gctanita/understandingImageGeneration/blob/master/experimentPrompts.md )
- Each prompt was generated 8 times with different seeds (each seed was used across each prompt)
- 𝙎𝙩𝙚𝙥𝙨: 20
- 𝘾𝙁𝙂: 3
- 𝙒𝙞𝙙𝙩𝙝: 512
- 𝙃𝙚𝙞𝙜𝙝𝙩: 512
- 𝙎𝙘𝙝𝙚𝙙𝙪𝙡𝙚𝙧: simple


You can find the raw data here: 
- https://github.com/gctanita/understandingImageGeneration/blob/master/Samplers/EULER/euler-raw-data.md


Scoring criteria for each series can be found here:
- https://github.com/gctanita/understandingImageGeneration/blob/master/Samplers/scoring_criteria.md


Hardware the setup:
- Graphic Card: NVIDIA GeForce RTX 4060 Ti with 8Gb VRAM 
- CPU: AMD Ryzen 5 5500, 3.60 GHz
- RAM: 32.0 GB, speed of 2400 MT/s 


For each image I gave it a score based on some on a set of subjective criteria designed to assess visual quality and consistency across different samplers. Each anomaly observed in the generated images deducted points from the total score, resulting in a binary scale (1 = acceptable, 0 = flawed). And for each image I recorded how much it took to generate them. Average normalized time means that I have eliminated the biggest 4 times from the series, that contained the loading of the model and / or parsing of the prompt for the first time. 