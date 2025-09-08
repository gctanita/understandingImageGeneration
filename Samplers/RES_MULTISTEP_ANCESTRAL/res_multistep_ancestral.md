# RES_MULTISTEP_ANCESTRAL 

Average score:	4.56	out of 17.25
Total score:	146	out of 552
Average time: 	130.40	s / picture
Average time normalized:	126.01	s / picture *

RES_MULTISTEP_ANCESTRAL is an experimental image generation sampler that blends multistep solvers (for accuracy and stability) with residual correction (to reduce denoising errors) and ancestral sampling (adds controlled noise at each step for creative variation).

This sampler is built on 3 core ideas:
- Multistep method — Uses previous step data to more accurately predict future noise states (like DPM++)
- Residual estimation — Corrects predictions using the "leftover error" from previous steps
- Ancestral sampling — Reintroduces controlled randomness (noise) at each step, allowing for more varied, organic, and less deterministic results

This combination makes it:
- More expressive than purely deterministic samplers
- More stable than raw ancestral samplers like Euler a
- Suitable for creative, dynamic, and complex prompts


About:
- not deterministic due to ancestral randomness
- 20-30 steps recommended (for good texture recommended 24+)
- speed is moderate, faster than DPM++ 3M SDE
- output is detailed, expressive, organic textures
- variation is high — even with same prompt and seed
- recommended for creative scenes, fantasy art, portraits with natural imperfections


✅ Pros
- Creative, less rigid outputs than deterministic samplers
- Refined details due to residual correction
- Excellent for faces, nature, fantasy, and emotional scenes
- Multistep noise evolution improves color transitions and shading

⚠️ Cons
- Not reproducible — small changes = different image (due to noise injection)
- Slower than Euler, slightly slower than res_multistep
- May need fine-tuning CFG and steps for best results


𝙋𝙞𝙘𝙩𝙪𝙧𝙚 𝙜𝙚𝙣𝙚𝙧𝙖𝙩𝙞𝙤𝙣 𝙨𝙚𝙩𝙩𝙞𝙣𝙜𝙨:
- 4 prompts (you can find them here: https://github.com/gctanita/understandingImageGeneration/blob/master/experimentPrompts.md )
- Each prompt was generated 8 times with different seeds (each seed was used across each prompt)
- 𝙎𝙩𝙚𝙥𝙨: 20
- 𝘾𝙁𝙂: 3
- 𝙒𝙞𝙙𝙩𝙝: 512
- 𝙃𝙚𝙞𝙜𝙝𝙩: 512
- 𝙎𝙘𝙝𝙚𝙙𝙪𝙡𝙚𝙧: simple


You can find the raw data here: 
- https://github.com/gctanita/understandingImageGeneration/blob/master/Samplers/RES_MULTISTEP_ANCESTRAL/res_multistep_ancestral-raw-data.md


Scoring criteria for each series can be found here:
- https://github.com/gctanita/understandingImageGeneration/blob/master/Samplers/scoring_criteria.md


Hardware the setup:
- Graphic Card: NVIDIA GeForce RTX 4060 Ti with 8Gb VRAM 
- CPU: AMD Ryzen 5 5500, 3.60 GHz
- RAM: 32.0 GB, speed of 2400 MT/s 


For each image I gave it a score based on some on a set of subjective criteria designed to assess visual quality and consistency across different samplers. Each anomaly observed in the generated images deducted points from the total score, resulting in a binary scale (1 = acceptable, 0 = flawed). And for each image I recorded how much it took to generate them. Average normalized time means that I have eliminated the biggest 4 times from the series, that contained the loading of the model and / or parsing of the prompt for the first time. 