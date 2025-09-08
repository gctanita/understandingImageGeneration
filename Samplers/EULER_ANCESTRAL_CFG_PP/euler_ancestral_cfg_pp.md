# EULER_ANCESTRAL_CFG_PP

Average score:	11.75	out of 17.25
Total score:	376	out of 552
Average time: 	127.78	s / picture
Average time normalized:	125.44	s / picture *

Euler Ancestral CFG PP is an experimental sampler that combines three components: Euler Ancestral: A fast, stochastic (randomized) sampler known for vibrant, artistic, and creative outputs with CFG: Classifier-Free Guidance — steers the image more toward your prompt and PP: CFG Preconditioning — a technique that stabilizes and improves CFG, especially at higher values (8–15). In short: euler_ancestral_cfg_pp = fast + random + stable guidance. It's useful when you want the creative variety of Euler Ancestral, but with more precision and control in how the prompt is followed.


About
- It is not deterministic it is stochastic, output varies across runs
- Very fast
- 20–30 steps recomended
- Works well even at CFG 10–12+ without going unstable
- Usually compatible with karras or exponential


✅ Pros
- Creative and vibrant outputs (thanks to ancestral noise)
- Better stability than Euler a at high CFG
- Variety-friendly: good for generating batches of stylized outputs
- Improved prompt adherence with less overexposure or melting

⚠️ Cons
- Non-deterministic (you won’t get the exact same image twice)
- Still not ideal for realism or inpainting workflows
- Experimental — may behave differently across UI implementations (e.g. ComfyUI, A1111 forks)


𝙋𝙞𝙘𝙩𝙪𝙧𝙚 𝙜𝙚𝙣𝙚𝙧𝙖𝙩𝙞𝙤𝙣 𝙨𝙚𝙩𝙩𝙞𝙣𝙜𝙨:
- 4 prompts (you can find them here: https://github.com/gctanita/understandingImageGeneration/blob/master/experimentPrompts.md )
- Each prompt was generated 8 times with different seeds (each seed was used across each prompt)
- 𝙎𝙩𝙚𝙥𝙨: 20
- 𝘾𝙁𝙂: 3
- 𝙒𝙞𝙙𝙩𝙝: 512
- 𝙃𝙚𝙞𝙜𝙝𝙩: 512
- 𝙎𝙘𝙝𝙚𝙙𝙪𝙡𝙚𝙧: simple


You can find the raw data here: 
- https://github.com/gctanita/understandingImageGeneration/blob/master/Samplers/EULER_ANCESTRAL_CFG_PP/euler_ancestral_cfg_pp-raw-data.md


Scoring criteria for each series can be found here:
- https://github.com/gctanita/understandingImageGeneration/blob/master/Samplers/scoring_criteria.md


Hardware the setup:
- Graphic Card: NVIDIA GeForce RTX 4060 Ti with 8Gb VRAM 
- CPU: AMD Ryzen 5 5500, 3.60 GHz
- RAM: 32.0 GB, speed of 2400 MT/s 


For each image I gave it a score based on some on a set of subjective criteria designed to assess visual quality and consistency across different samplers. Each anomaly observed in the generated images deducted points from the total score, resulting in a binary scale (1 = acceptable, 0 = flawed). And for each image I recorded how much it took to generate them. Average normalized time means that I have eliminated the biggest 4 times from the series, that contained the loading of the model and / or parsing of the prompt for the first time. 