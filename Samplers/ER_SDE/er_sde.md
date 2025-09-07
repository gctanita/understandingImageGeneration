# ER_SDE

Average score:	13.84	out of 17.25
Total score:	443	out of 552
Average time: 	129.72	s / picture
Average time normalized:	126.24	s / picture *

ER_SDE stands for "Euler–Rauch Stochastic Differential Equation", and it is a stochastic sampler used in diffusion-based image generation. It blends ideas from Euler methods (common in basic samplers like Euler or Euler a), SDE (Stochastic Differential Equation)-based noise schedules and Likely enhanced or experimental formulations from the DPM++ or advanced scheduler families. In short: ER_SDE is an SDE-driven, noise-aware sampler that offers creative variation and smooth transitions, optimized for diverse, stable outputs.


About
- You’ll mostly find it in UIs like ComfyUI, Kohya_ss, InvokeAI, or cutting-edge builds of AUTOMATIC1111
- Its exact implementation may vary between platforms
- Documentation is limited, and it may evolve or change
- 25–40 steps for most results
- It is not deterministic — it is stochastic, so results vary with same seed
- Best at smooth gradients, balanced structure
- Generates stylized realism, portraits, painterly lighting, variable detail


✅ Pros
- Stochastic → encourages creative, diverse outputs
- Smooth lighting, natural tone transitions
- More exploratory than deterministic samplers
- May avoid overfitting or oversharpening seen in some deterministic samplers

⚠️ Cons
- Not deterministic — difficult to exactly reproduce results
- Less documentation — harder to tweak or benchmark
- May not be ideal for high-fidelity photorealism (better suited for stylized or creative prompts)


𝙋𝙞𝙘𝙩𝙪𝙧𝙚 𝙜𝙚𝙣𝙚𝙧𝙖𝙩𝙞𝙤𝙣 𝙨𝙚𝙩𝙩𝙞𝙣𝙜𝙨:
- 4 prompts (you can find them here: https://github.com/gctanita/understandingImageGeneration/blob/master/experimentPrompts.md )
- Each prompt was generated 8 times with different seeds (each seed was used across each prompt)
- 𝙎𝙩𝙚𝙥𝙨: 20
- 𝘾𝙁𝙂: 3
- 𝙒𝙞𝙙𝙩𝙝: 512
- 𝙃𝙚𝙞𝙜𝙝𝙩: 512
- 𝙎𝙘𝙝𝙚𝙙𝙪𝙡𝙚𝙧: simple


You can find the raw data here: 
- https://github.com/gctanita/understandingImageGeneration/blob/master/Samplers/ER_SDE/er_sde-raw-data.md


Scoring criteria for each series can be found here:
- https://github.com/gctanita/understandingImageGeneration/blob/master/Samplers/scoring_criteria.md


Hardware the setup:
- Graphic Card: NVIDIA GeForce RTX 4060 Ti with 8Gb VRAM 
- CPU: AMD Ryzen 5 5500, 3.60 GHz
- RAM: 32.0 GB, speed of 2400 MT/s 


For each image I gave it a score based on some on a set of subjective criteria designed to assess visual quality and consistency across different samplers. Each anomaly observed in the generated images deducted points from the total score, resulting in a binary scale (1 = acceptable, 0 = flawed). And for each image I recorded how much it took to generate them. Average normalized time means that I have eliminated the biggest 4 times from the series, that contained the loading of the model and / or parsing of the prompt for the first time. 