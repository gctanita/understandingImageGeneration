# IPNDM

Average score:	13.69	out of 17.25
Total score:	438	out of 552
Average time: 	129.35	s / picture
Average time normalized:	125.84	s / picture *


IPNDM stands for "Implicit Predictive Noise Diffusion Model" — an experimental sampler used in diffusion-based image generation. It’s designed to approximate denoising trajectories more efficiently by focusing on the noise prediction process, rather than simulating the entire diffusion path in traditional steps.


About:
- It is deterministic
- 10-30 steps recommended
- Fast — designed for reduced computation
- Quality currently decent but not photorealistic
- Broad strokes, strong shapes, but lower texture fidelity
- Usually supports epsilon, v, or score predictions


✅ Pros
- Very fast — can work with fewer steps
- Designed for efficient noise prediction
- Deterministic
- Great for preview generation or mobile/low-power environments

⚠️ Cons
- Still experimental — not production-quality in many setups
- May lack fine detail, especially in hands, faces, or soft textures
- Not ideal for photorealism or high-precision tasks
- Limited documentation — implementation may vary by UI


𝙋𝙞𝙘𝙩𝙪𝙧𝙚 𝙜𝙚𝙣𝙚𝙧𝙖𝙩𝙞𝙤𝙣 𝙨𝙚𝙩𝙩𝙞𝙣𝙜𝙨:
- 4 prompts (you can find them here: https://github.com/gctanita/understandingImageGeneration/blob/master/experimentPrompts.md )
- Each prompt was generated 8 times with different seeds (each seed was used across each prompt)
- 𝙎𝙩𝙚𝙥𝙨: 20
- 𝘾𝙁𝙂: 3
- 𝙒𝙞𝙙𝙩𝙝: 512
- 𝙃𝙚𝙞𝙜𝙝𝙩: 512
- 𝙎𝙘𝙝𝙚𝙙𝙪𝙡𝙚𝙧: simple


You can find the raw data here: 
- https://github.com/gctanita/understandingImageGeneration/blob/master/Samplers/IPNDM/ipndm-raw-data.md


Scoring criteria for each series can be found here:
- https://github.com/gctanita/understandingImageGeneration/blob/master/Samplers/scoring_criteria.md


Hardware the setup:
- Graphic Card: NVIDIA GeForce RTX 4060 Ti with 8Gb VRAM 
- CPU: AMD Ryzen 5 5500, 3.60 GHz
- RAM: 32.0 GB, speed of 2400 MT/s 


For each image I gave it a score based on some on a set of subjective criteria designed to assess visual quality and consistency across different samplers. Each anomaly observed in the generated images deducted points from the total score, resulting in a binary scale (1 = acceptable, 0 = flawed). And for each image I recorded how much it took to generate them. Average normalized time means that I have eliminated the biggest 4 times from the series, that contained the loading of the model and / or parsing of the prompt for the first time. 