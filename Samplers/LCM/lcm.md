# LCM

Average score:	13.00	out of 17.25
Total score:	416	out of 552
Average time: 	130.56	s / picture
Average time normalized:	126.63	s / picture *

LCM stands for Latent Consistency Model — a new generation of samplers that aim to drastically reduce the number of steps needed to generate high-quality images. Unlike traditional samplers (like Euler, DDIM, or DPM++), LCM is not just a sampling method — it's an entirely different architecture and training paradigm. In short: LCM is a sampler + model training strategy that enables high-quality images in as few as 2–8 steps.


About:
- You must use an LCM-trained model (e.g., LCM-LoRA or LCM-SDXL)
- As low as 2–8 steps
- It is deterministic
- Extremely fast
- Compatible UIs: ComfyUI, AUTOMATIC1111 (with LCM support), Fooocus, etc.

✅ Pros
- Insanely fast generation (1–2 seconds for full image on GPU)
- High quality even at 4 steps
- Works well with ControlNet, LoRA, and other conditioning tools
- Deterministic — reproducible outputs
- Ideal for real-time applications, mobile UIs, or interactive generation

⚠️ Cons
- Requires LCM-compatible model (can’t use standard SD 1.5 or SDXL alone)
- Can sometimes produce softer images or minor artifacts at very low steps
- Not as flexible for fine-tuning small details compared to 30–50-step samplers


𝙋𝙞𝙘𝙩𝙪𝙧𝙚 𝙜𝙚𝙣𝙚𝙧𝙖𝙩𝙞𝙤𝙣 𝙨𝙚𝙩𝙩𝙞𝙣𝙜𝙨:
- 4 prompts (you can find them here: https://github.com/gctanita/understandingImageGeneration/blob/master/experimentPrompts.md )
- Each prompt was generated 8 times with different seeds (each seed was used across each prompt)
- 𝙎𝙩𝙚𝙥𝙨: 20
- 𝘾𝙁𝙂: 3
- 𝙒𝙞𝙙𝙩𝙝: 512
- 𝙃𝙚𝙞𝙜𝙝𝙩: 512
- 𝙎𝙘𝙝𝙚𝙙𝙪𝙡𝙚𝙧: simple


You can find the raw data here: 
- https://github.com/gctanita/understandingImageGeneration/blob/master/Samplers/LCM/lcm-raw-data.md


Scoring criteria for each series can be found here:
- https://github.com/gctanita/understandingImageGeneration/blob/master/Samplers/scoring_criteria.md


Hardware the setup:
- Graphic Card: NVIDIA GeForce RTX 4060 Ti with 8Gb VRAM 
- CPU: AMD Ryzen 5 5500, 3.60 GHz
- RAM: 32.0 GB, speed of 2400 MT/s 


For each image I gave it a score based on some on a set of subjective criteria designed to assess visual quality and consistency across different samplers. Each anomaly observed in the generated images deducted points from the total score, resulting in a binary scale (1 = acceptable, 0 = flawed). And for each image I recorded how much it took to generate them. Average normalized time means that I have eliminated the biggest 4 times from the series, that contained the loading of the model and / or parsing of the prompt for the first time. 