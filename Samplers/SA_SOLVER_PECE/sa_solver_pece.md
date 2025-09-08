# SA_SOLVER_PECE

Average score:	13.91	out of 17.25
Total score:	445	out of 552
Average time: 	244.62	s / picture
Average time normalized:	238.78	s / picture *


SA_SOLVER_PECE is a variant of the SA_SOLVER (Stochastic Analytic Solver) that uses a numerical technique called PECE — short for Predict – Evaluate – Correct – Evaluate. This method is a refined multistep approach for solving the reverse diffusion process more accurately and stably, especially when randomness (stochasticity) is involved.


About:
- it is not deterministic
- 15–30 steps recommended (20+ gives great balance)
- at speed it is slightly slower than sa_solver, faster than dpm++ 3m
- it has better edge clarity and lighting consistency than sa_solver
- recommended for expressive and dynamic compositions needing stable variation


✅ Pros
- Better precision than sa_solver alone
- Great for glow, motion, expressive details
- Improved handling of complex lighting and soft shadows
- Works well at CFG 7–12

⚠️ Cons
- Not reproducible (random component)
- Slightly slower than Euler or basic SA_SOLVER
- Not ideal for scientific, exact-match or face-consistent generation


𝙋𝙞𝙘𝙩𝙪𝙧𝙚 𝙜𝙚𝙣𝙚𝙧𝙖𝙩𝙞𝙤𝙣 𝙨𝙚𝙩𝙩𝙞𝙣𝙜𝙨:
- 4 prompts (you can find them here: https://github.com/gctanita/understandingImageGeneration/blob/master/experimentPrompts.md )
- Each prompt was generated 8 times with different seeds (each seed was used across each prompt)
- 𝙎𝙩𝙚𝙥𝙨: 20
- 𝘾𝙁𝙂: 3
- 𝙒𝙞𝙙𝙩𝙝: 512
- 𝙃𝙚𝙞𝙜𝙝𝙩: 512
- 𝙎𝙘𝙝𝙚𝙙𝙪𝙡𝙚𝙧: simple


You can find the raw data here: 
- https://github.com/gctanita/understandingImageGeneration/blob/master/Samplers/SA_SOLVER_PECE/sa_solver_pece-raw-data.md


Scoring criteria for each series can be found here:
- https://github.com/gctanita/understandingImageGeneration/blob/master/Samplers/scoring_criteria.md


Hardware the setup:
- Graphic Card: NVIDIA GeForce RTX 4060 Ti with 8Gb VRAM 
- CPU: AMD Ryzen 5 5500, 3.60 GHz
- RAM: 32.0 GB, speed of 2400 MT/s 


For each image I gave it a score based on some on a set of subjective criteria designed to assess visual quality and consistency across different samplers. Each anomaly observed in the generated images deducted points from the total score, resulting in a binary scale (1 = acceptable, 0 = flawed). And for each image I recorded how much it took to generate them. Average normalized time means that I have eliminated the biggest 4 times from the series, that contained the loading of the model and / or parsing of the prompt for the first time. 