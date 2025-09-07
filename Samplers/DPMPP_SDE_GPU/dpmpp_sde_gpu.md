# DPMPP_SDE_GPU

Average score:	13.66	out of 17.25
Total score:	437	out of 552
Average time: 	248.74	s / picture
Average time normalized:	243.80	s / picture *

DPM++ SDE GPU is the GPU-accelerated version of the DPM++ SDE sampler — combining the smoothness and realism of Stochastic Differential Equation (SDE)-based noise handling with the speed of GPU-optimized computation. It is designed to provide a balanced mix of quality and speed, offering stable, clean, and photorealistic results faster than its CPU-based counterpart.


About
- 20–35 steps for general use; 40+ steps for photorealism
- it is deterministic
- best with Karras or Exponential noise schedules
- faster than dpmpp_sde, approaching dpmpp_2m_sde_gpu
- generates high-quality, smooth, fast generations on CUDA-compatible GPUs


✅ Pros
- GPU-accelerated — fast, efficient rendering on modern GPUs
- Stable and clean outputs, thanks to SDE-based sampling
- Deterministic, unlike stochastic/ancestral samplers
- Balanced output — good contrast, good detail, no harsh edges
- Performs well even at medium step counts (20–30)

⚠️ Cons
- Slightly less detailed than DPM++ 3M SDE GPU at same steps
- May not capture ultra-fine textures or very high-frequency patterns
- Requires a CUDA-capable GPU to achieve intended performance


𝙋𝙞𝙘𝙩𝙪𝙧𝙚 𝙜𝙚𝙣𝙚𝙧𝙖𝙩𝙞𝙤𝙣 𝙨𝙚𝙩𝙩𝙞𝙣𝙜𝙨:
- 4 prompts (you can find them here: https://github.com/gctanita/understandingImageGeneration/blob/master/experimentPrompts.md )
- Each prompt was generated 8 times with different seeds (each seed was used across each prompt)
- 𝙎𝙩𝙚𝙥𝙨: 20
- 𝘾𝙁𝙂: 3
- 𝙒𝙞𝙙𝙩𝙝: 512
- 𝙃𝙚𝙞𝙜𝙝𝙩: 512
- 𝙎𝙘𝙝𝙚𝙙𝙪𝙡𝙚𝙧: simple


You can find the raw data here: 
- https://github.com/gctanita/understandingImageGeneration/blob/master/Samplers/DPMPP_SDE_GPU/dpmpp_2m_sde_gpu-raw-data.md


Scoring criteria for each series can be found here:
- https://github.com/gctanita/understandingImageGeneration/blob/master/Samplers/scoring_criteria.md


Hardware the setup:
- Graphic Card: NVIDIA GeForce RTX 4060 Ti with 8Gb VRAM 
- CPU: AMD Ryzen 5 5500, 3.60 GHz
- RAM: 32.0 GB, speed of 2400 MT/s 


For each image I gave it a score based on some on a set of subjective criteria designed to assess visual quality and consistency across different samplers. Each anomaly observed in the generated images deducted points from the total score, resulting in a binary scale (1 = acceptable, 0 = flawed). And for each image I recorded how much it took to generate them. Average normalized time means that I have eliminated the biggest 4 times from the series, that contained the loading of the model and / or parsing of the prompt for the first time. 