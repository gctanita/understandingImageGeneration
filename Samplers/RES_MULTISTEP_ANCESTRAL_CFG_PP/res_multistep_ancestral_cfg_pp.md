# RES_MULTISTEP_ANCESTRAL_CFG_PP

Average score:	0.00	out of 17.25
Total score:	0	out of 552
Average time: 	131.36	s / picture
Average time normalized:	126.10	s / picture *


RES_MULTISTEP_ANCESTRAL_CFG_PP is a highly advanced, hybrid sampler that merges multistep sampling (accurate and stable denoising using previous steps) with ancestral noise injection (adds creative variability and texture), residual correction (reduces accumulated error during generation) and Classifier-Free Guidance + Prompt Preconditioning (CFG_PP) — improves precision and detail retention under high CFG.


About:
- not deterministic - due to ancestral noise injection
- 20-30 steps recommended
- moderate speed (slower than Euler, faster than DPM++ 3M)
- output quality very high with rich gradients, accurate details, and creative flare
- works well even at CFG 10–14
- recommended for artistic portraits, fantasy scenes, concept art, soft realism


✅ Pros
- Super detailed, even under high CFG
- Great color dynamics, lighting, and texture variety
- Reduced artifacting from CFG or noise prediction
- Creative yet accurate → best of both worlds
- Amazing for portraits, fantasy, atmospheric scenes

⚠️ Cons
- Not deterministic — slight changes = different results
- Slightly slower than simpler samplers (like Euler or DDIM)
- Not ideal for scientific, exact, or photoreal renderings that require pixel-consistent results


𝙋𝙞𝙘𝙩𝙪𝙧𝙚 𝙜𝙚𝙣𝙚𝙧𝙖𝙩𝙞𝙤𝙣 𝙨𝙚𝙩𝙩𝙞𝙣𝙜𝙨:
- 4 prompts (you can find them here: https://github.com/gctanita/understandingImageGeneration/blob/master/experimentPrompts.md )
- Each prompt was generated 8 times with different seeds (each seed was used across each prompt)
- 𝙎𝙩𝙚𝙥𝙨: 20
- 𝘾𝙁𝙂: 3
- 𝙒𝙞𝙙𝙩𝙝: 512
- 𝙃𝙚𝙞𝙜𝙝𝙩: 512
- 𝙎𝙘𝙝𝙚𝙙𝙪𝙡𝙚𝙧: simple


You can find the raw data here: 
- https://github.com/gctanita/understandingImageGeneration/blob/master/Samplers/RES_MULTISTEP_ANCESTRAL_CFG_PP/res_multistep_ancestral_cfg_pp-raw-data.md


Scoring criteria for each series can be found here:
- https://github.com/gctanita/understandingImageGeneration/blob/master/Samplers/scoring_criteria.md


Hardware the setup:
- Graphic Card: NVIDIA GeForce RTX 4060 Ti with 8Gb VRAM 
- CPU: AMD Ryzen 5 5500, 3.60 GHz
- RAM: 32.0 GB, speed of 2400 MT/s 


For each image I gave it a score based on some on a set of subjective criteria designed to assess visual quality and consistency across different samplers. Each anomaly observed in the generated images deducted points from the total score, resulting in a binary scale (1 = acceptable, 0 = flawed). And for each image I recorded how much it took to generate them. Average normalized time means that I have eliminated the biggest 4 times from the series, that contained the loading of the model and / or parsing of the prompt for the first time. 