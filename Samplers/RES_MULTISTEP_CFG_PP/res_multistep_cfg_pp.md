# RES_MULTISTEP_CFG_PP

Average score:	0.00	out of 17.25
Total score:	0	out of 552
Average time: 	132.52	s / picture
Average time normalized:	125.94	s / picture *


RES_MULTISTEP_CFG_PP is a deterministic, high-accuracy sampler that combines residual prediction (to refine noise estimates), multistep solvers (for better denoising accuracy) and CFG_PP = Classifier-Free Guidance with Prompt Preconditioning (for stability at high guidance values).


About:
- it is deterministic 
- 20–30 recommended steps (25+ yields better fidelity)
- clean lines, good structure, balanced lighting
- slower than Euler, faster than DPM++ 3M
- recommended for realism, character design, clean fantasy, editorial-style renders


✅ Pros
- Excellent stability at high CFG (8–14)
- Great structure preservation (faces, hands, objects)
- Minimal noise or over-sharpening
- Fully deterministic — same output from same prompt + seed
- Compatible with modern schedulers (karras, exponential, etc.)

⚠️ Cons
- Less creative variety than ancestral or LCM-based samplers
- Not ideal for chaotic, expressive styles (use *_ancestral or LCM instead)
- Slightly slower than first-order methods (e.g., Euler)


𝙋𝙞𝙘𝙩𝙪𝙧𝙚 𝙜𝙚𝙣𝙚𝙧𝙖𝙩𝙞𝙤𝙣 𝙨𝙚𝙩𝙩𝙞𝙣𝙜𝙨:
- 4 prompts (you can find them here: https://github.com/gctanita/understandingImageGeneration/blob/master/experimentPrompts.md )
- Each prompt was generated 8 times with different seeds (each seed was used across each prompt)
- 𝙎𝙩𝙚𝙥𝙨: 20
- 𝘾𝙁𝙂: 3
- 𝙒𝙞𝙙𝙩𝙝: 512
- 𝙃𝙚𝙞𝙜𝙝𝙩: 512
- 𝙎𝙘𝙝𝙚𝙙𝙪𝙡𝙚𝙧: simple


You can find the raw data here: 
- https://github.com/gctanita/understandingImageGeneration/blob/master/Samplers/RES_MULTISTEP_CFG_PP/res_multistep_cfg_pp-raw-data.md


Scoring criteria for each series can be found here:
- https://github.com/gctanita/understandingImageGeneration/blob/master/Samplers/scoring_criteria.md


Hardware the setup:
- Graphic Card: NVIDIA GeForce RTX 4060 Ti with 8Gb VRAM 
- CPU: AMD Ryzen 5 5500, 3.60 GHz
- RAM: 32.0 GB, speed of 2400 MT/s 


For each image I gave it a score based on some on a set of subjective criteria designed to assess visual quality and consistency across different samplers. Each anomaly observed in the generated images deducted points from the total score, resulting in a binary scale (1 = acceptable, 0 = flawed). And for each image I recorded how much it took to generate them. Average normalized time means that I have eliminated the biggest 4 times from the series, that contained the loading of the model and / or parsing of the prompt for the first time. 