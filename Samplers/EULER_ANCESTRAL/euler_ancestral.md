# EULER_ANCESTRAL

Average score:	13.56	out of 17.25
Total score:	434	out of 552
Average time: 	128.14	s / picture
Average time normalized:	125.37	s / picture *


Euler Ancestral is a stochastic version of the classic Euler sampler, widely used in diffusion image generation. It introduces random noise (ancestral sampling) during each denoising step, allowing for creative variability, natural texture, and high prompt sensitivity. It’s one of the most popular samplers for producing vibrant, expressive, and varied images, especially in artistic or fantasy prompts.


About
- It is not deterministic — different runs = different outputs
- 20–30 steps is a sweet spot
- High CFG sensitivity — can produce distortions at CFG > 10
- Very fast (comparable to Euler)
- best for fantasy, surreal art, stylized renders
- not good for photorealism, consistency, exact inpainting


✅ Pros
- Great for artistic, dreamlike, or fantasy prompts
- Creative variability — good for generating many versions
- Fast and efficient
- Often yields rich color and dramatic lighting

⚠️ Cons
- Not reproducible (unless you fix seed and settings — and even then, variation can occur)
- Can introduce artifacts, melting, or warping at high CFG
- Not ideal for photorealistic or technical prompts



𝙋𝙞𝙘𝙩𝙪𝙧𝙚 𝙜𝙚𝙣𝙚𝙧𝙖𝙩𝙞𝙤𝙣 𝙨𝙚𝙩𝙩𝙞𝙣𝙜𝙨:
- 4 prompts (you can find them here: https://github.com/gctanita/understandingImageGeneration/blob/master/experimentPrompts.md )
- Each prompt was generated 8 times with different seeds (each seed was used across each prompt)
- 𝙎𝙩𝙚𝙥𝙨: 20
- 𝘾𝙁𝙂: 3
- 𝙒𝙞𝙙𝙩𝙝: 512
- 𝙃𝙚𝙞𝙜𝙝𝙩: 512
- 𝙎𝙘𝙝𝙚𝙙𝙪𝙡𝙚𝙧: simple


You can find the raw data here: 
- https://github.com/gctanita/understandingImageGeneration/blob/master/Samplers/EULER_ANCESTRAL/euler_ancestral-raw-data.md


Scoring criteria for each series can be found here:
- https://github.com/gctanita/understandingImageGeneration/blob/master/Samplers/scoring_criteria.md


Hardware the setup:
- Graphic Card: NVIDIA GeForce RTX 4060 Ti with 8Gb VRAM 
- CPU: AMD Ryzen 5 5500, 3.60 GHz
- RAM: 32.0 GB, speed of 2400 MT/s 


For each image I gave it a score based on some on a set of subjective criteria designed to assess visual quality and consistency across different samplers. Each anomaly observed in the generated images deducted points from the total score, resulting in a binary scale (1 = acceptable, 0 = flawed). And for each image I recorded how much it took to generate them. Average normalized time means that I have eliminated the biggest 4 times from the series, that contained the loading of the model and / or parsing of the prompt for the first time. 