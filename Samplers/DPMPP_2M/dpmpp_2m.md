# DPMPP_2M

Average score:	13.72	out of 17.25
Total score:	439	out of 552
Average time: 	131.12	s / picture
Average time normalized:	125.90	s / picture *


DPM++ 2M is a modern, high-quality, deterministic sampler from the DPM++ family. It is designed to produce sharp, stable, and accurate images using second-order multi-step solvers. It’s one of the most recommended samplers in modern Stable Diffusion tools like AUTOMATIC1111, ComfyUI, and others — especially when quality and consistency matter.


How It Works (High-Level)
- Unlike Euler or DDIM, which use just the previous step, DPM++ 2M uses multiple previous noise states to improve denoising.
- It solves the reverse diffusion ODE with high accuracy, while keeping steps low (like 20–30).
- It’s deterministic (same seed, prompt, CFG → same image).


✅ Pros
- Very high image quality
- Repeatable (great for controlled experiments)
- Good detail retention at lower steps
- Less noisy and more stable than Euler/Heun
- Excellent balance between speed and accuracy

⚠️ Cons
- Slightly less "creative" or "loose" than stochastic samplers like dpm++ 2s a
- May look too "clean" or synthetic for some artistic styles
- Requires compatible noise scheduler (e.g., Karras for best results)


𝙋𝙞𝙘𝙩𝙪𝙧𝙚 𝙜𝙚𝙣𝙚𝙧𝙖𝙩𝙞𝙤𝙣 𝙨𝙚𝙩𝙩𝙞𝙣𝙜𝙨:
- 4 prompts (you can find them here: https://github.com/gctanita/understandingImageGeneration/blob/master/experimentPrompts.md )
- Each prompt was generated 8 times with different seeds (each seed was used across each prompt)
- 𝙎𝙩𝙚𝙥𝙨: 20
- 𝘾𝙁𝙂: 3
- 𝙒𝙞𝙙𝙩𝙝: 512
- 𝙃𝙚𝙞𝙜𝙝𝙩: 512
- 𝙎𝙘𝙝𝙚𝙙𝙪𝙡𝙚𝙧: simple


You can find the raw data here: 
- https://github.com/gctanita/understandingImageGeneration/blob/master/Samplers/DPMPP_2M/dpmpp_2m-raw-data.md


Scoring criteria for each series can be found here:
- https://github.com/gctanita/understandingImageGeneration/blob/master/Samplers/scoring_criteria.md


Hardware the setup:
- Graphic Card: NVIDIA GeForce RTX 4060 Ti with 8Gb VRAM 
- CPU: AMD Ryzen 5 5500, 3.60 GHz
- RAM: 32.0 GB, speed of 2400 MT/s 


For each image I gave it a score based on some on a set of subjective criteria designed to assess visual quality and consistency across different samplers. Each anomaly observed in the generated images deducted points from the total score, resulting in a binary scale (1 = acceptable, 0 = flawed). And for each image I recorded how much it took to generate them. Average normalized time means that I have eliminated the biggest 4 times from the series, that contained the loading of the model and / or parsing of the prompt for the first time. 