# DPMPP_3M_SDE

Average score:	12.00	out of 17.25
Total score:	384	out of 552
Average time: 	130.51	s / picture
Average time normalized:	126.75	s / picture *


DPM++ 3M SDE is one of the most advanced, high-fidelity, and precise samplers available in the diffusion model ecosystem today. It combines DPM++ → an improved family of samplers based on ODE/SDE solvers with 3M → a third-order, multistep solver (more accurate than 2M or 2S) and SDE → uses Stochastic Differential Equations to guide the sampling process with added robustness and smoother transitions. Together, this creates a premium-quality sampler for ultra-detailed, photorealistic image generation — especially in scenes requiring complex lighting, gradients, or realism.


About
- Steps Recommended: 30–50 for best results (but can look good even at 25+)
- Is deterministic - same seed and prompt → same output
- Noise Scheduler Karras is highly recommended
- Is slower than 2M/2S, but worth it for quality
- Best for high-end photorealism, portraits, detailed textures, gradients


✅ Pros
- Highest detail and realism among mainstream samplers
- Very accurate sampling, especially in difficult prompts (e.g. dark lighting, mist, glass)
- Deterministic — perfect for reproducible outputs
- Smooth gradients, subtle lighting, and refined edge transitions
- Excellent with high-res, portrait, or scene-based prompts

⚠️ Cons
- Slower than 2M/2S or DDIM — uses more computation per step
- May appear too "clean" or over-smooth for gritty/artistic styles
- Might not benefit stylized/cartoonish prompts as much as photorealistic ones

𝙋𝙞𝙘𝙩𝙪𝙧𝙚 𝙜𝙚𝙣𝙚𝙧𝙖𝙩𝙞𝙤𝙣 𝙨𝙚𝙩𝙩𝙞𝙣𝙜𝙨:
- 4 prompts (you can find them here: https://github.com/gctanita/understandingImageGeneration/blob/master/experimentPrompts.md )
- Each prompt was generated 8 times with different seeds (each seed was used across each prompt)
- 𝙎𝙩𝙚𝙥𝙨: 20
- 𝘾𝙁𝙂: 3
- 𝙒𝙞𝙙𝙩𝙝: 512
- 𝙃𝙚𝙞𝙜𝙝𝙩: 512
- 𝙎𝙘𝙝𝙚𝙙𝙪𝙡𝙚𝙧: simple


You can find the raw data here: 
- https://github.com/gctanita/understandingImageGeneration/blob/master/Samplers/DPMPP_3M_SDE/dpmpp_3m_sde-raw-data.md


Scoring criteria for each series can be found here:
- https://github.com/gctanita/understandingImageGeneration/blob/master/Samplers/scoring_criteria.md


Hardware the setup:
- Graphic Card: NVIDIA GeForce RTX 4060 Ti with 8Gb VRAM 
- CPU: AMD Ryzen 5 5500, 3.60 GHz
- RAM: 32.0 GB, speed of 2400 MT/s 


For each image I gave it a score based on some on a set of subjective criteria designed to assess visual quality and consistency across different samplers. Each anomaly observed in the generated images deducted points from the total score, resulting in a binary scale (1 = acceptable, 0 = flawed). And for each image I recorded how much it took to generate them. Average normalized time means that I have eliminated the biggest 4 times from the series, that contained the loading of the model and / or parsing of the prompt for the first time. 