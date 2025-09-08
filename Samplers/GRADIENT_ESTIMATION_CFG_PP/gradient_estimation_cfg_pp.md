# GRADIENT_ESTIMATION_CFG_PP

Average score:	0.00	out of 17.25
Total score:	0	out of 552
Average time: 	130.63	s / picture
Average time normalized:	126.44	s / picture *

GRADIENT_ESTIMATION_CFG_PP is an experimental, GPU-accelerated sampler that combines Gradient Estimation — a fast, non-traditional sampling method that approximates denoising gradients rather than simulating full reverse diffusion steps with CFG — Classifier-Free Guidance, to steer the image generation toward your prompt and CFG PP — Preconditioned Guidance, which improves stability and fidelity when using high CFG values (e.g., 8–15+). In short gradient_estimation_cfg_pp = fast + guided + stable + experimental. It is typically found in ComfyUI or custom forks of generation frameworks (e.g., diffusion toolkits with experimental samplers enabled).=0


About:
- usually it is deterministic
- 10-25 steps recomended 
- speed - very fast (especially on GPU)
- quality - may lack fine texture or realism, but stable
- supports high CFG (10–15) without major quality drop


✅ Pros
- Extremely fast sampler — excellent for previews, real-time applications, or mobile/gen AI UI tools
- CFG PP makes it stable even at high prompt guidance values
- Good prompt alignment, especially for simple, high-level prompts
- Deterministic, so good for consistent results across runs

⚠️ Cons
- Still experimental — behavior may vary across versions/backends
- May generate blurry or undersaturated images compared to DPM++ samplers
- Not ideal for high-end photorealism or detailed anatomy (hands, faces, etc.)


𝙋𝙞𝙘𝙩𝙪𝙧𝙚 𝙜𝙚𝙣𝙚𝙧𝙖𝙩𝙞𝙤𝙣 𝙨𝙚𝙩𝙩𝙞𝙣𝙜𝙨:
- 4 prompts (you can find them here: https://github.com/gctanita/understandingImageGeneration/blob/master/experimentPrompts.md )
- Each prompt was generated 8 times with different seeds (each seed was used across each prompt)
- 𝙎𝙩𝙚𝙥𝙨: 20
- 𝘾𝙁𝙂: 3
- 𝙒𝙞𝙙𝙩𝙝: 512
- 𝙃𝙚𝙞𝙜𝙝𝙩: 512
- 𝙎𝙘𝙝𝙚𝙙𝙪𝙡𝙚𝙧: simple


You can find the raw data here: 
- https://github.com/gctanita/understandingImageGeneration/blob/master/Samplers/GRADIENT_ESTIMATION_CFG_PP/gradient_estimation_cfg_pp-raw-data.md


Scoring criteria for each series can be found here:
- https://github.com/gctanita/understandingImageGeneration/blob/master/Samplers/scoring_criteria.md


Hardware the setup:
- Graphic Card: NVIDIA GeForce RTX 4060 Ti with 8Gb VRAM 
- CPU: AMD Ryzen 5 5500, 3.60 GHz
- RAM: 32.0 GB, speed of 2400 MT/s 


For each image I gave it a score based on some on a set of subjective criteria designed to assess visual quality and consistency across different samplers. Each anomaly observed in the generated images deducted points from the total score, resulting in a binary scale (1 = acceptable, 0 = flawed). And for each image I recorded how much it took to generate them. Average normalized time means that I have eliminated the biggest 4 times from the series, that contained the loading of the model and / or parsing of the prompt for the first time. 