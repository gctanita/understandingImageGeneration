# DPMPP_SDE

Average score:	13.56	out of 17.25
Total score:	434	out of 552
Average time: 	253.51	s / picture
Average time normalized:	248.81	s / picture *


DPM++ SDE is a modern, SDE-based sampler from the DPM++ family, designed to deliver smooth, detailed, and stable image generation by leveraging a stochastic differential equation (SDE) noise schedule — without being tied to a specific solver order (like 2M, 2S, or 3M). It serves as a baseline SDE sampler in many UI toolkits such as ComfyUI, AUTOMATIC1111, etc.


About
- it is deterministic
- recomended scheduler is SDE-based (adds robustness and gradient smoothness)
- 20–30 steps for good balance, 40+ for maximum quality
- compatible with epsilon, v, or score noise prediction models


✅ Pros
- Natural transitions and lighting, especially good with SDE noise modeling
- Deterministic — reproducible results
- Good for portraits, environments, and soft-glow lighting
- Useful for inpainting, refinement, or clean renders
- Balanced output even with medium CFG values (6–10)

⚠️ Cons
- Less refined than specific samplers like DPM++ 2M SDE or 3M SDE
- May not exploit solver-specific optimizations (slightly lower fidelity)
- Not ideal for super stylized prompts or high randomness scenarios


𝙋𝙞𝙘𝙩𝙪𝙧𝙚 𝙜𝙚𝙣𝙚𝙧𝙖𝙩𝙞𝙤𝙣 𝙨𝙚𝙩𝙩𝙞𝙣𝙜𝙨:
- 4 prompts (you can find them here: https://github.com/gctanita/understandingImageGeneration/blob/master/experimentPrompts.md )
- Each prompt was generated 8 times with different seeds (each seed was used across each prompt)
- 𝙎𝙩𝙚𝙥𝙨: 20
- 𝘾𝙁𝙂: 3
- 𝙒𝙞𝙙𝙩𝙝: 512
- 𝙃𝙚𝙞𝙜𝙝𝙩: 512
- 𝙎𝙘𝙝𝙚𝙙𝙪𝙡𝙚𝙧: simple


You can find the raw data here: 
- https://github.com/gctanita/understandingImageGeneration/blob/master/Samplers/DPMPP_SDE/dpmpp_sde-raw-data.md


Scoring criteria for each series can be found here:
- https://github.com/gctanita/understandingImageGeneration/blob/master/Samplers/scoring_criteria.md


Hardware the setup:
- Graphic Card: NVIDIA GeForce RTX 4060 Ti with 8Gb VRAM 
- CPU: AMD Ryzen 5 5500, 3.60 GHz
- RAM: 32.0 GB, speed of 2400 MT/s 


For each image I gave it a score based on some on a set of subjective criteria designed to assess visual quality and consistency across different samplers. Each anomaly observed in the generated images deducted points from the total score, resulting in a binary scale (1 = acceptable, 0 = flawed). And for each image I recorded how much it took to generate them. Average normalized time means that I have eliminated the biggest 4 times from the series, that contained the loading of the model and / or parsing of the prompt for the first time. 