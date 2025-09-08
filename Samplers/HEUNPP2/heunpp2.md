# HEUNPP2

Average score:	13.91	out of 17.25
Total score:	445	out of 552
Average time: 	356.50	s / picture
Average time normalized:	353.26	s / picture *

HeunPP2 is an advanced, second-order deterministic sampler used in image generation with diffusion models. It is an improved version of the classic Heun sampler, part of the DPM++ sampler family, and is designed to be faster and more accurate by combining the Heun method (a 2nd-order ODE solver) with DPM++ enhancements for stability and better denoising behavior and preconditioning techniques (likely the “PP2” part) to improve guidance accuracy and reduce artifacts. Think of HeunPP2 as “Heun++, optimized for modern diffusion models” — better prompt fidelity, smoother gradients, and less distortion.


About:
- 2nd-order ODE with prompt preconditioning
- It is deterministic
- 20-40 steps recommended
- Fast — similar to Heun, slightly slower than Euler
- CFG stability is very good — less distortion at high values (10–15)
- Supports epsilon, v, or score-based models for noise prediction


✅ Pros
- Better accuracy than standard Heun or Euler
- Produces stable lighting, shading, and detail
- Repeatable — deterministic behavior
- Handles complex prompts better (faces, hands, lighting)
- Compatible with modern schedulers like Karras, Exponential, etc.

⚠️ Cons
- Slightly slower than Euler or DDIM
- May still lack ultra-high fidelity of samplers like DPM++ 3M SDE
- Not stochastic — not suitable if you want creative variation across generations


𝙋𝙞𝙘𝙩𝙪𝙧𝙚 𝙜𝙚𝙣𝙚𝙧𝙖𝙩𝙞𝙤𝙣 𝙨𝙚𝙩𝙩𝙞𝙣𝙜𝙨:
- 4 prompts (you can find them here: https://github.com/gctanita/understandingImageGeneration/blob/master/experimentPrompts.md )
- Each prompt was generated 8 times with different seeds (each seed was used across each prompt)
- 𝙎𝙩𝙚𝙥𝙨: 20
- 𝘾𝙁𝙂: 3
- 𝙒𝙞𝙙𝙩𝙝: 512
- 𝙃𝙚𝙞𝙜𝙝𝙩: 512
- 𝙎𝙘𝙝𝙚𝙙𝙪𝙡𝙚𝙧: simple


You can find the raw data here: 
- https://github.com/gctanita/understandingImageGeneration/blob/master/Samplers/HEUNPP2/heunpp2-raw-data.md


Scoring criteria for each series can be found here:
- https://github.com/gctanita/understandingImageGeneration/blob/master/Samplers/scoring_criteria.md


Hardware the setup:
- Graphic Card: NVIDIA GeForce RTX 4060 Ti with 8Gb VRAM 
- CPU: AMD Ryzen 5 5500, 3.60 GHz
- RAM: 32.0 GB, speed of 2400 MT/s 


For each image I gave it a score based on some on a set of subjective criteria designed to assess visual quality and consistency across different samplers. Each anomaly observed in the generated images deducted points from the total score, resulting in a binary scale (1 = acceptable, 0 = flawed). And for each image I recorded how much it took to generate them. Average normalized time means that I have eliminated the biggest 4 times from the series, that contained the loading of the model and / or parsing of the prompt for the first time. 