# SA_SOLVER

Average score:	13.19	out of 17.25
Total score:	422	out of 552
Average time: 	138.18	s / picture
Average time normalized:	126.21	s / picture *

SA_SOLVER stands for Stochastic Analytic Solver, a relatively new and experimental sampling method designed to accelerate diffusion while maintaining image quality. It is stochastic (it introduces randomness like ancestral samplers), analytic (it leverages exact mathematical approximations for the diffusion process) and solver (it uses numerical techniques to solve the reverse diffusion ODE/SDE equations). In essence SA_SOLVER is a fast sampler that aims to balance speed, randomness, and detail. It can work well in low-step setups and generate diverse but structurally accurate outputs.


About: 
- it is not deterministic
- 12–30 recommended steps (often works well even at 15–20 steps)
- fast
- output usually has good structure, creative textures, minimal artifacts
- recommended for artistic scenes, character portraits, dynamic lighting


✅ Pros
- Fast generation with good quality
- Expressive results due to stochasticity
- Handles complex prompts well (e.g., glowing effects, fire, magic, etc.)
- Compatible with modern schedulers (karras, exponential)

⚠️ Cons
- Not deterministic — results vary even with same seed
- Still experimental — not as consistent as DPM++ or RES_MULTISTEP
- Not great for ultra-low-step (e.g., 4-step) generation — better than Euler but not LCM-level


𝙋𝙞𝙘𝙩𝙪𝙧𝙚 𝙜𝙚𝙣𝙚𝙧𝙖𝙩𝙞𝙤𝙣 𝙨𝙚𝙩𝙩𝙞𝙣𝙜𝙨:
- 4 prompts (you can find them here: https://github.com/gctanita/understandingImageGeneration/blob/master/experimentPrompts.md )
- Each prompt was generated 8 times with different seeds (each seed was used across each prompt)
- 𝙎𝙩𝙚𝙥𝙨: 20
- 𝘾𝙁𝙂: 3
- 𝙒𝙞𝙙𝙩𝙝: 512
- 𝙃𝙚𝙞𝙜𝙝𝙩: 512
- 𝙎𝙘𝙝𝙚𝙙𝙪𝙡𝙚𝙧: simple


You can find the raw data here: 
- https://github.com/gctanita/understandingImageGeneration/blob/master/Samplers/SA_SOLVER/sa_solver-raw-data.md


Scoring criteria for each series can be found here:
- https://github.com/gctanita/understandingImageGeneration/blob/master/Samplers/scoring_criteria.md


Hardware the setup:
- Graphic Card: NVIDIA GeForce RTX 4060 Ti with 8Gb VRAM 
- CPU: AMD Ryzen 5 5500, 3.60 GHz
- RAM: 32.0 GB, speed of 2400 MT/s 


For each image I gave it a score based on some on a set of subjective criteria designed to assess visual quality and consistency across different samplers. Each anomaly observed in the generated images deducted points from the total score, resulting in a binary scale (1 = acceptable, 0 = flawed). And for each image I recorded how much it took to generate them. Average normalized time means that I have eliminated the biggest 4 times from the series, that contained the loading of the model and / or parsing of the prompt for the first time. 