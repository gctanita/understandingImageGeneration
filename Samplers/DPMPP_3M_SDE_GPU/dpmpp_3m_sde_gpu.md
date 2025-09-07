# DPMPP_3M_SDE_GPU

Average score:	12.25	out of 17.25
Total score:	392	out of 552
Average time: 	130.21	s / picture
Average time normalized:	126.56	s / picture *


DPM++ 3M SDE GPU is the GPU-accelerated version of the DPM++ 3M SDE sampler — one of the highest-quality samplers in the diffusion family. It combines 3rd-order multistep precision (3M) with Stochastic Differential Equation noise schedule (SDE) and GPU optimization for significantly faster performance without sacrificing quality. This sampler is designed to produce ultra-detailed, photorealistic, and stable outputs — just like DPM++ 3M SDE, but much faster when run on a compatible GPU.


About
- it is deterministic
- 30–50 steps needed for best detail, but great even at 25+ steps
- recommended scheduler is Karras (for smooth transitions and lighting)
- much faster than regular DPM++ 3M SDE (thanks to fused CUDA ops)
- generates high-end photorealism, cinematic lighting, realistic anatomy/portraits


✅ Pros
- Highest image fidelity with smooth transitions and rich texture
- Much faster than the non-GPU version — up to 2× or more
- Deterministic — excellent for reproducible results
- Great for portraits, product renders, landscapes, glass/reflections
- Excels in subtle gradients, realistic lighting, and high-contrast scenes

⚠️ Cons
- Still slower than Euler a or DPM++ 2S a in absolute terms (but higher quality)
- May be overkill for stylized or cartoonish prompts
- Needs a compatible GPU and backend to fully benefit (e.g., CUDA ≥11, torch.compile, etc.)


𝙋𝙞𝙘𝙩𝙪𝙧𝙚 𝙜𝙚𝙣𝙚𝙧𝙖𝙩𝙞𝙤𝙣 𝙨𝙚𝙩𝙩𝙞𝙣𝙜𝙨:
- 4 prompts (you can find them here: https://github.com/gctanita/understandingImageGeneration/blob/master/experimentPrompts.md )
- Each prompt was generated 8 times with different seeds (each seed was used across each prompt)
- 𝙎𝙩𝙚𝙥𝙨: 20
- 𝘾𝙁𝙂: 3
- 𝙒𝙞𝙙𝙩𝙝: 512
- 𝙃𝙚𝙞𝙜𝙝𝙩: 512
- 𝙎𝙘𝙝𝙚𝙙𝙪𝙡𝙚𝙧: simple


You can find the raw data here: 
- https://github.com/gctanita/understandingImageGeneration/blob/master/Samplers/DPMPP_3M_SDE_GPU/dpmpp_3m_sde_gpu-raw-data.md


Scoring criteria for each series can be found here:
- https://github.com/gctanita/understandingImageGeneration/blob/master/Samplers/scoring_criteria.md


Hardware the setup:
- Graphic Card: NVIDIA GeForce RTX 4060 Ti with 8Gb VRAM 
- CPU: AMD Ryzen 5 5500, 3.60 GHz
- RAM: 32.0 GB, speed of 2400 MT/s 


For each image I gave it a score based on some on a set of subjective criteria designed to assess visual quality and consistency across different samplers. Each anomaly observed in the generated images deducted points from the total score, resulting in a binary scale (1 = acceptable, 0 = flawed). And for each image I recorded how much it took to generate them. Average normalized time means that I have eliminated the biggest 4 times from the series, that contained the loading of the model and / or parsing of the prompt for the first time. 