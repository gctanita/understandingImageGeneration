# DPMPP_2M_SDE

Average score:	13.78	out of 17.25
Total score:	441	out of 552
Average time: 	129.68	s / picture
Average time normalized:	126.50	s / picture *


DPM++ 2M SDE is a high-quality, deterministic, and noise-aware sampler from the DPM++ family, specifically optimized to work with SDE (Stochastic Differential Equation)-based noise schedules. It blends the advantages of DPM++ 2M: a 2nd-order, multistep, deterministic sampler and SDE: a stochastic noise schedule that enhances robustness and sample diversity resulting in crisp, stable, realistic images, even in challenging prompts or low-step configurations


About
- Typically 20–40 necessary for clean results
- It is deterministic (no randomness, same seed = same output)
- Works with epsilon, v, or score prediction models
- Typically uses Karras or Exponential noise schedule
- Best for clean realism, subtle lighting, photorealistic skin/eyes, sharp textures

✅ Pros
- Deterministic, great for reproducibility
- High-quality results at lower steps
- Handles subtle gradients, lighting, and contrast very well
- Good with photorealistic, natural, and sharp scenes
- Works very well with CFG preconditioning, ControlNet, and upscaling workflows

⚠️ Cons
- Slightly slower than DDIM or Euler
- Can appear too clean or "safe" in highly creative/artistic prompts
- Requires SDE-compatible noise schedulers for best results


𝙋𝙞𝙘𝙩𝙪𝙧𝙚 𝙜𝙚𝙣𝙚𝙧𝙖𝙩𝙞𝙤𝙣 𝙨𝙚𝙩𝙩𝙞𝙣𝙜𝙨:
- 4 prompts (you can find them here: https://github.com/gctanita/understandingImageGeneration/blob/master/experimentPrompts.md )
- Each prompt was generated 8 times with different seeds (each seed was used across each prompt)
- 𝙎𝙩𝙚𝙥𝙨: 20
- 𝘾𝙁𝙂: 3
- 𝙒𝙞𝙙𝙩𝙝: 512
- 𝙃𝙚𝙞𝙜𝙝𝙩: 512
- 𝙎𝙘𝙝𝙚𝙙𝙪𝙡𝙚𝙧: simple


You can find the raw data here: 
- https://github.com/gctanita/understandingImageGeneration/blob/master/Samplers/DPMPP_2M_SDE/dpmpp_2m_sde-raw-data.md


Scoring criteria for each series can be found here:
- https://github.com/gctanita/understandingImageGeneration/blob/master/Samplers/scoring_criteria.md


Hardware the setup:
- Graphic Card: NVIDIA GeForce RTX 4060 Ti with 8Gb VRAM 
- CPU: AMD Ryzen 5 5500, 3.60 GHz
- RAM: 32.0 GB, speed of 2400 MT/s 


For each image I gave it a score based on some on a set of subjective criteria designed to assess visual quality and consistency across different samplers. Each anomaly observed in the generated images deducted points from the total score, resulting in a binary scale (1 = acceptable, 0 = flawed). And for each image I recorded how much it took to generate them. Average normalized time means that I have eliminated the biggest 4 times from the series, that contained the loading of the model and / or parsing of the prompt for the first time. 