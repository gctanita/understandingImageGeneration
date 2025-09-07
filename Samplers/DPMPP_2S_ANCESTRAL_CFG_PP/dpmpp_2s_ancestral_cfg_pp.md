# DPMPP_2S_ANCESTRAL_CFG_PP

Average score:	0.00	out of 17.25
Total score:	0	out of 552
Average time: 	255.74	s / picture
Average time normalized:	246.41	s / picture *

DPM++ 2S Ancestral CFG PP is a high-performance, stochastic sampler from the DPM++ family that combines DPM++ 2S — a second-order, single-step solver (fast and accurate) with  Ancestral — adds randomness for natural variation and creativity and CFG PP — Classifier-Free Guidance Preconditioning, which improves stability and detail when using higher CFG values (e.g. 7–15). In short, this sampler should be Fast + Random + CFG-stable + High-detail + Creative-friendly


About
- Not deterministic — each generation will vary, even with the same seed
- Best CFG range is 7–12 — performs very well with strong guidance
- Steps recommended is 20–30 is optimal
- Very fast (single-step solvers are quicker than multistep)
- Noise schedule is compatible with Karras or other high-quality schedules

✅ Pros
- Stochastic — great for creative variation
- CFG PP helps prevent overshooting, artifacts, or washed-out faces at high CFG
- Good detail, sharpness, and natural lighting
- Fast and responsive — ideal for iterative workflows or dynamic scenes
- Great for portraits, concept art, stylized realism

⚠️ Cons
- Not reproducible (no guarantee of identical output on repeated runs)
- Slightly more chaotic than deterministic samplers like 2M CFG PP
- May introduce subtle noise in background if CFG is too low or high


𝙋𝙞𝙘𝙩𝙪𝙧𝙚 𝙜𝙚𝙣𝙚𝙧𝙖𝙩𝙞𝙤𝙣 𝙨𝙚𝙩𝙩𝙞𝙣𝙜𝙨:
- 4 prompts (you can find them here: https://github.com/gctanita/understandingImageGeneration/blob/master/experimentPrompts.md )
- Each prompt was generated 8 times with different seeds (each seed was used across each prompt)
- 𝙎𝙩𝙚𝙥𝙨: 20
- 𝘾𝙁𝙂: 3
- 𝙒𝙞𝙙𝙩𝙝: 512
- 𝙃𝙚𝙞𝙜𝙝𝙩: 512
- 𝙎𝙘𝙝𝙚𝙙𝙪𝙡𝙚𝙧: simple


You can find the raw data here: 
- https://github.com/gctanita/understandingImageGeneration/blob/master/Samplers/DPMPP_2S_ANCESTRAL_CFG_PP/dpmpp_2s_ancestral_cfg_pp-raw-data.md


Scoring criteria for each series can be found here:
- https://github.com/gctanita/understandingImageGeneration/blob/master/Samplers/scoring_criteria.md


Hardware the setup:
- Graphic Card: NVIDIA GeForce RTX 4060 Ti with 8Gb VRAM 
- CPU: AMD Ryzen 5 5500, 3.60 GHz
- RAM: 32.0 GB, speed of 2400 MT/s 


For each image I gave it a score based on some on a set of subjective criteria designed to assess visual quality and consistency across different samplers. Each anomaly observed in the generated images deducted points from the total score, resulting in a binary scale (1 = acceptable, 0 = flawed). And for each image I recorded how much it took to generate them. Average normalized time means that I have eliminated the biggest 4 times from the series, that contained the loading of the model and / or parsing of the prompt for the first time. 