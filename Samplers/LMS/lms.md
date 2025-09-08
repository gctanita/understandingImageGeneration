# LMS

Average score:	10.19	out of 17.25
Total score:	326	out of 552
Average time: 	128.45	s / picture
Average time normalized:	125.53	s / picture *


LMS stands for Laplacian Pyramid Multiscale Sampler — but in the context of diffusion models (like Stable Diffusion), it usually refers to the Linear Multistep Sampler, which is a deterministic, ODE-based sampling algorithm designed to produce images faster and with higher quality than early samplers like DDPM or Euler. LMS is a deterministic, fast, and relatively old sampler. It has largely been replaced in modern workflows by improved variants like DPM++ 2M or Heun, but it is still available in many UIs like AUTOMATIC1111, InvokeAI, and ComfyUI.


About:
- it is deterministic
- 20-40 steps recommended (less effective at very low steps)
- fast
- quality is moderate - better than Euler, worse than DPM++
- good for general-porpouse generation with stable output


✅ Pros
- Fast and deterministic
- Cleaner results than Euler or DDIM at the same step count
- Good for older Stable Diffusion 1.4 / 1.5 models
- Great for batch generation or reproducible pipelines


⚠️ Cons
- Lower fidelity than modern samplers like DPM++ 2M or 3M SDE
- Can be unstable at high CFG values
- Not optimal for realistic lighting or subtle textures
- Rarely used in new workflows (often replaced by DPM++)


𝙋𝙞𝙘𝙩𝙪𝙧𝙚 𝙜𝙚𝙣𝙚𝙧𝙖𝙩𝙞𝙤𝙣 𝙨𝙚𝙩𝙩𝙞𝙣𝙜𝙨:
- 4 prompts (you can find them here: https://github.com/gctanita/understandingImageGeneration/blob/master/experimentPrompts.md )
- Each prompt was generated 8 times with different seeds (each seed was used across each prompt)
- 𝙎𝙩𝙚𝙥𝙨: 20
- 𝘾𝙁𝙂: 3
- 𝙒𝙞𝙙𝙩𝙝: 512
- 𝙃𝙚𝙞𝙜𝙝𝙩: 512
- 𝙎𝙘𝙝𝙚𝙙𝙪𝙡𝙚𝙧: simple


You can find the raw data here: 
- https://github.com/gctanita/understandingImageGeneration/blob/master/Samplers/LMS/lms-raw-data.md


Scoring criteria for each series can be found here:
- https://github.com/gctanita/understandingImageGeneration/blob/master/Samplers/scoring_criteria.md


Hardware the setup:
- Graphic Card: NVIDIA GeForce RTX 4060 Ti with 8Gb VRAM 
- CPU: AMD Ryzen 5 5500, 3.60 GHz
- RAM: 32.0 GB, speed of 2400 MT/s 


For each image I gave it a score based on some on a set of subjective criteria designed to assess visual quality and consistency across different samplers. Each anomaly observed in the generated images deducted points from the total score, resulting in a binary scale (1 = acceptable, 0 = flawed). And for each image I recorded how much it took to generate them. Average normalized time means that I have eliminated the biggest 4 times from the series, that contained the loading of the model and / or parsing of the prompt for the first time. 