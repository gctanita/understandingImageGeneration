# UNI_PC

Average score:	13.78	out of 17.25
Total score:	441	out of 552
Average time: 	130.89	s / picture
Average time normalized:	125.89	s / picture *

UNI_PC stands for Unified Predictor-Corrector, a fast, high-precision sampler designed to unify and generalize various existing diffusion solvers into a single framework. It was introduced in the paper:"UniPC: A Unified Predictor-Corrector Framework for Fast Sampling of Diffusion Models" by Zhang et al., 2023


About:
- it is deterministic
- works surprisingly well with as few as 8–15 steps
- very fast
- excellent for few-step generation
- recommended for real-time apps, low-latency rendering, mobile/stage demos


✅ Pros
- Extremely fast generation (rivals or beats DDIM, LCM)
- Works well with few steps (8–12 often sufficient)
- Maintains structure and color balance
- Robust even with high CFG and complex prompts
- Can be integrated with Karras scheduler and others

⚠️ Cons
- Slightly lower fidelity than full 30–50-step samplers like DPM++ 3M SDE
- May produce softer details if pushed too hard (e.g., 6 steps)
- Limited configurability compared to res_multistep or euler_ancestral


𝙋𝙞𝙘𝙩𝙪𝙧𝙚 𝙜𝙚𝙣𝙚𝙧𝙖𝙩𝙞𝙤𝙣 𝙨𝙚𝙩𝙩𝙞𝙣𝙜𝙨:
- 4 prompts (you can find them here: https://github.com/gctanita/understandingImageGeneration/blob/master/experimentPrompts.md )
- Each prompt was generated 8 times with different seeds (each seed was used across each prompt)
- 𝙎𝙩𝙚𝙥𝙨: 20
- 𝘾𝙁𝙂: 3
- 𝙒𝙞𝙙𝙩𝙝: 512
- 𝙃𝙚𝙞𝙜𝙝𝙩: 512
- 𝙎𝙘𝙝𝙚𝙙𝙪𝙡𝙚𝙧: simple


You can find the raw data here: 
- https://github.com/gctanita/understandingImageGeneration/blob/master/Samplers/UNI_PC/uni_pc-raw-data.md


Scoring criteria for each series can be found here:
- https://github.com/gctanita/understandingImageGeneration/blob/master/Samplers/scoring_criteria.md


Hardware the setup:
- Graphic Card: NVIDIA GeForce RTX 4060 Ti with 8Gb VRAM 
- CPU: AMD Ryzen 5 5500, 3.60 GHz
- RAM: 32.0 GB, speed of 2400 MT/s 


For each image I gave it a score based on some on a set of subjective criteria designed to assess visual quality and consistency across different samplers. Each anomaly observed in the generated images deducted points from the total score, resulting in a binary scale (1 = acceptable, 0 = flawed). And for each image I recorded how much it took to generate them. Average normalized time means that I have eliminated the biggest 4 times from the series, that contained the loading of the model and / or parsing of the prompt for the first time. 