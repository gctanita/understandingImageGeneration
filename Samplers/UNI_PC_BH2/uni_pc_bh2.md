# UNI_PC_BH2

Average score:	13.25	out of 17.25
Total score:	424	out of 552
Average time: 	130.44	s / picture
Average time normalized:	125.90	s / picture *


UNI_PC_BH2 is a variant of the UNI_PC (Unified Predictor-Corrector) sampler — designed for faster and more stable diffusion sampling. The BH2 part stands for a second-order B(h) method, which is a specific numerical solver technique that improves accuracy while keeping computations efficient.


About:
- it is deterministic
- very fast, especially in low step setups
- steps recommended 8-20
- output is smoother than UNI_PC, better structure retention
- creative variation is low to medium (fidelity-focused)
- best used on mobile apps, fast pipelines, real-time previews, low-latency rendering


✅ Pros
- Improved precision over plain UNI_PC (less noise, better edges)
- Works well in low-step settings (8–12 steps)
- Good CFG stability up to ~12
- Fast, clean, consistent results

⚠️ Cons
- Less expressive than stochastic samplers like Euler a or SA_SOLVER
- Slightly more memory-intensive than UNI_PC due to extra computations
- Not ideal for artistic chaos or morphing


𝙋𝙞𝙘𝙩𝙪𝙧𝙚 𝙜𝙚𝙣𝙚𝙧𝙖𝙩𝙞𝙤𝙣 𝙨𝙚𝙩𝙩𝙞𝙣𝙜𝙨:
- 4 prompts (you can find them here: https://github.com/gctanita/understandingImageGeneration/blob/master/experimentPrompts.md )
- Each prompt was generated 8 times with different seeds (each seed was used across each prompt)
- 𝙎𝙩𝙚𝙥𝙨: 20
- 𝘾𝙁𝙂: 3
- 𝙒𝙞𝙙𝙩𝙝: 512
- 𝙃𝙚𝙞𝙜𝙝𝙩: 512
- 𝙎𝙘𝙝𝙚𝙙𝙪𝙡𝙚𝙧: simple


You can find the raw data here: 
- https://github.com/gctanita/understandingImageGeneration/blob/master/Samplers/UNI_PC_BH2/uni_pc_bh2-raw-data.md


Scoring criteria for each series can be found here:
- https://github.com/gctanita/understandingImageGeneration/blob/master/Samplers/scoring_criteria.md


Hardware the setup:
- Graphic Card: NVIDIA GeForce RTX 4060 Ti with 8Gb VRAM 
- CPU: AMD Ryzen 5 5500, 3.60 GHz
- RAM: 32.0 GB, speed of 2400 MT/s 


For each image I gave it a score based on some on a set of subjective criteria designed to assess visual quality and consistency across different samplers. Each anomaly observed in the generated images deducted points from the total score, resulting in a binary scale (1 = acceptable, 0 = flawed). And for each image I recorded how much it took to generate them. Average normalized time means that I have eliminated the biggest 4 times from the series, that contained the loading of the model and / or parsing of the prompt for the first time. 