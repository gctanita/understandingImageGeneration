# EULER_CFG_PP

Average score:	10.50	out of 17.25
Total score:	336	out of 552
Average time: 	127.82	s / picture
Average time normalized:	125.38	s / picture *


Euler CFG PP is an experimental deterministic sampler that combines Euler — a fast, first-order, deterministic solver with CFG (Classifier-Free Guidance) — guides the image more toward the text prompt and PP (CFG Preconditioning) — a stabilizing technique that improves the accuracy, sharpness, and control of CFG, especially at higher values (e.g. 8–12+). In simple terms euler_cfg_pp = classic Euler sampler + smarter CFG guidance. It retains Euler’s speed and determinism but improves image consistency at higher CFG levels.

CFG Preconditioning modifies how guidance is applied during sampling:
- Prevents overexposure, warping, or burned highlights at high CFG
- Leads to sharper edges, clearer subject separation, and less distortion
- Introduced in Karras et al. 2023 and used in advanced samplers like dpmpp_2m_cfg_pp

About:
- It is deterministic
- 20–30 steps recommended (classic Euler sweet spot)
- Works well even at CFG 10–12 without blowing out details
- Very fast (as fast or faster than standard Euler)
- Output is sharp, bold, high contrast — but more controlled than standard Euler

✅ Pros
- Extremely fast
- Repeatable results
- Handles high CFG values better than original Euler
- Less distortion on faces, hands, text, etc.
- More accurate prompt adherence vs vanilla Euler

⚠️ Cons
- Still has some hard edge artifacts in soft scenes (due to Euler base)
- Not ideal for realism (like DPM++ SDE or DDIM)
- Experimental — not always available in every UI


𝙋𝙞𝙘𝙩𝙪𝙧𝙚 𝙜𝙚𝙣𝙚𝙧𝙖𝙩𝙞𝙤𝙣 𝙨𝙚𝙩𝙩𝙞𝙣𝙜𝙨:
- 4 prompts (you can find them here: https://github.com/gctanita/understandingImageGeneration/blob/master/experimentPrompts.md )
- Each prompt was generated 8 times with different seeds (each seed was used across each prompt)
- 𝙎𝙩𝙚𝙥𝙨: 20
- 𝘾𝙁𝙂: 3
- 𝙒𝙞𝙙𝙩𝙝: 512
- 𝙃𝙚𝙞𝙜𝙝𝙩: 512
- 𝙎𝙘𝙝𝙚𝙙𝙪𝙡𝙚𝙧: simple


You can find the raw data here: 
- https://github.com/gctanita/understandingImageGeneration/blob/master/Samplers/EULER_CFG_PP/euler_cfg_pp-raw-data.md


Scoring criteria for each series can be found here:
- https://github.com/gctanita/understandingImageGeneration/blob/master/Samplers/scoring_criteria.md


Hardware the setup:
- Graphic Card: NVIDIA GeForce RTX 4060 Ti with 8Gb VRAM 
- CPU: AMD Ryzen 5 5500, 3.60 GHz
- RAM: 32.0 GB, speed of 2400 MT/s 


For each image I gave it a score based on some on a set of subjective criteria designed to assess visual quality and consistency across different samplers. Each anomaly observed in the generated images deducted points from the total score, resulting in a binary scale (1 = acceptable, 0 = flawed). And for each image I recorded how much it took to generate them. Average normalized time means that I have eliminated the biggest 4 times from the series, that contained the loading of the model and / or parsing of the prompt for the first time. 