# DPMPP_2M_SDE_GPU

Average score:	13.72	out of 17.25
Total score:	439	out of 552
Average time: 	133.73	s / picture
Average time normalized:	126.52	s / picture *


DPM++ 2M SDE GPU is a GPU-optimized version of the DPM++ 2M SDE sampler — one of the most high-quality, deterministic, and noise-aware samplers available in diffusion-based image generation.


Key Features
- 2nd-order multistep with SDE noise schedule
- Deterministic — consistent output with same seed/settings
- Noise Schedule SDE — handles soft gradients, contrast, and fine textures well
- GPU Optimization — it is designed to run faster using CUDA or low-level kernels
- Output Quality — extremely high for realism, portraits, subtle scenes


✅ Pros
- Faster than the regular DPM++ 2M SDE due to GPU acceleration
- Very high-quality images — especially good with realistic lighting, skin, landscapes
- Deterministic, great for batch workflows or rerendering the same image
- Handles subtle tone, gradients, and details better than older samplers

⚠️ Cons
- Slightly slower than fast samplers like Euler or DDIM (but much better quality)
- Only available in certain implementations (e.g. ComfyUI, A1111 with GPU optimizations)
- Might require specific conditions (e.g. torch.compile, CUDA 11+, etc.)


𝙋𝙞𝙘𝙩𝙪𝙧𝙚 𝙜𝙚𝙣𝙚𝙧𝙖𝙩𝙞𝙤𝙣 𝙨𝙚𝙩𝙩𝙞𝙣𝙜𝙨:
- 4 prompts (you can find them here: https://github.com/gctanita/understandingImageGeneration/blob/master/experimentPrompts.md )
- Each prompt was generated 8 times with different seeds (each seed was used across each prompt)
- 𝙎𝙩𝙚𝙥𝙨: 20
- 𝘾𝙁𝙂: 3
- 𝙒𝙞𝙙𝙩𝙝: 512
- 𝙃𝙚𝙞𝙜𝙝𝙩: 512
- 𝙎𝙘𝙝𝙚𝙙𝙪𝙡𝙚𝙧: simple


You can find the raw data here: 
- https://github.com/gctanita/understandingImageGeneration/blob/master/Samplers/DPMPP_2M_SDE_GPU/dpmpp_2m_sde_gpu-raw-data.md


Scoring criteria for each series can be found here:
- https://github.com/gctanita/understandingImageGeneration/blob/master/Samplers/scoring_criteria.md


Hardware the setup:
- Graphic Card: NVIDIA GeForce RTX 4060 Ti with 8Gb VRAM 
- CPU: AMD Ryzen 5 5500, 3.60 GHz
- RAM: 32.0 GB, speed of 2400 MT/s 


For each image I gave it a score based on some on a set of subjective criteria designed to assess visual quality and consistency across different samplers. Each anomaly observed in the generated images deducted points from the total score, resulting in a binary scale (1 = acceptable, 0 = flawed). And for each image I recorded how much it took to generate them. Average normalized time means that I have eliminated the biggest 4 times from the series, that contained the loading of the model and / or parsing of the prompt for the first time. 