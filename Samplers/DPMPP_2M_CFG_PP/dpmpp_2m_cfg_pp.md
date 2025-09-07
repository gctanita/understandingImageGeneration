# DPMPP_2M_CFG_PP

Average score:	0.00	out of 17.25
Total score:	0	out of 552
Average time: 	133.14	s / picture
Average time normalized:	128.10	s / picture *


DPM++ 2M CFG PP is an advanced, high-quality, deterministic sampler that combines: DPM++ 2M — a second-order multistep sampler, already known for its clean, stable, high-detail outputs and CFG Preconditioning (PP) — an optimization technique that enhances classifier-free guidance (CFG) to make the denoising more stable, consistent, and detailed, especially under high CFG values (e.g. 7–12)


What Makes DPM++ 2M CFG PP Special?
- It stabilizes guidance, especially at high CFG scales (e.g. 10–15)
- Reduces artifacts or overexposed areas that often appear with regular samplers at high CFG
- Makes the image generation process more robust and consistent, especially when strong prompt emphasis is desired
- it is deterministic


✅ Pros
- Repeatable results
- Sharper and more stable than regular DPM++ samplers at high CFG
- Handles strong guidance (CFG) without falling apart
- Balanced between quality and speed
- Great for photorealism, portraits, inpainting, and control-based workflows

⚠️ Cons
- Slightly slower than ultra-fast samplers like Euler or DDIM
- May look too “clean” or “safe” for stylized or abstract prompts
- Needs a compatible scheduler (Karras is often best)


𝙋𝙞𝙘𝙩𝙪𝙧𝙚 𝙜𝙚𝙣𝙚𝙧𝙖𝙩𝙞𝙤𝙣 𝙨𝙚𝙩𝙩𝙞𝙣𝙜𝙨:
- 4 prompts (you can find them here: https://github.com/gctanita/understandingImageGeneration/blob/master/experimentPrompts.md )
- Each prompt was generated 8 times with different seeds (each seed was used across each prompt)
- 𝙎𝙩𝙚𝙥𝙨: 20
- 𝘾𝙁𝙂: 3
- 𝙒𝙞𝙙𝙩𝙝: 512
- 𝙃𝙚𝙞𝙜𝙝𝙩: 512
- 𝙎𝙘𝙝𝙚𝙙𝙪𝙡𝙚𝙧: simple


You can find the raw data here: 
- https://github.com/gctanita/understandingImageGeneration/blob/master/Samplers/DPMPP_2M_CFG_PP/dpmpp_2m_cfg_pp-raw-data.md


Scoring criteria for each series can be found here:
- https://github.com/gctanita/understandingImageGeneration/blob/master/Samplers/scoring_criteria.md


Hardware the setup:
- Graphic Card: NVIDIA GeForce RTX 4060 Ti with 8Gb VRAM 
- CPU: AMD Ryzen 5 5500, 3.60 GHz
- RAM: 32.0 GB, speed of 2400 MT/s 


For each image I gave it a score based on some on a set of subjective criteria designed to assess visual quality and consistency across different samplers. Each anomaly observed in the generated images deducted points from the total score, resulting in a binary scale (1 = acceptable, 0 = flawed). And for each image I recorded how much it took to generate them. Average normalized time means that I have eliminated the biggest 4 times from the series, that contained the loading of the model and / or parsing of the prompt for the first time. 