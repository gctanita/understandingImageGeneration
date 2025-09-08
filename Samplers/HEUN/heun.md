# HEUN

Average score:	13.59	out of 17.25
Total score:	435	out of 552
Average time: 	245.10	s / picture
Average time normalized:	242.20	s / picture *

Heun is a second-order, deterministic sampler used in diffusion image generation. It is part of the family of ODE-based solvers and is more accurate than Euler, while still being relatively fast. Think of it as “Euler but smarter”. It’s commonly available in tools like AUTOMATIC1111, ComfyUI, InvokeAI, etc.

Heun’s method is a predictor-corrector technique used for solving ordinary differential equations (ODEs):
- It’s a second-order Runge-Kutta method, also called improved Euler.
- It first predicts a step using Euler, then corrects that prediction by averaging slopes (gradients).
- In diffusion models, this means it estimates denoising more accurately than Euler, especially in scenes with complex gradients (e.g. soft lighting, reflections, facial structure).


About:
- It is deterministic 
- 2nd-order ODE solver
- 20–30 recommended steps is typical, 40+ steps for extra clarity
- Fast (slightly slower than Euler, faster than multistep samplers)
- Works with epsilon, v, or score prediction


✅ Pros
- More accurate than Euler, especially at fewer steps
- Deterministic and consistent
- Produces cleaner, more stable images with smoother gradients
- Still quite fast, even on lower-end GPUs
- Works well with a wide range of prompts

⚠️ Cons
- Slightly slower than Euler and DDIM
- Can still struggle with high CFG values (e.g., >12) — faces/hands may distort
- Not as detail-rich as DPM++ 2M, 3M SDE, or other advanced samplers


𝙋𝙞𝙘𝙩𝙪𝙧𝙚 𝙜𝙚𝙣𝙚𝙧𝙖𝙩𝙞𝙤𝙣 𝙨𝙚𝙩𝙩𝙞𝙣𝙜𝙨:
- 4 prompts (you can find them here: https://github.com/gctanita/understandingImageGeneration/blob/master/experimentPrompts.md )
- Each prompt was generated 8 times with different seeds (each seed was used across each prompt)
- 𝙎𝙩𝙚𝙥𝙨: 20
- 𝘾𝙁𝙂: 3
- 𝙒𝙞𝙙𝙩𝙝: 512
- 𝙃𝙚𝙞𝙜𝙝𝙩: 512
- 𝙎𝙘𝙝𝙚𝙙𝙪𝙡𝙚𝙧: simple


You can find the raw data here: 
- https://github.com/gctanita/understandingImageGeneration/blob/master/Samplers/HEUN/heun-raw-data.md


Scoring criteria for each series can be found here:
- https://github.com/gctanita/understandingImageGeneration/blob/master/Samplers/scoring_criteria.md


Hardware the setup:
- Graphic Card: NVIDIA GeForce RTX 4060 Ti with 8Gb VRAM 
- CPU: AMD Ryzen 5 5500, 3.60 GHz
- RAM: 32.0 GB, speed of 2400 MT/s 


For each image I gave it a score based on some on a set of subjective criteria designed to assess visual quality and consistency across different samplers. Each anomaly observed in the generated images deducted points from the total score, resulting in a binary scale (1 = acceptable, 0 = flawed). And for each image I recorded how much it took to generate them. Average normalized time means that I have eliminated the biggest 4 times from the series, that contained the loading of the model and / or parsing of the prompt for the first time. 