# SEEDS_2

Average score:	13.69	out of 17.25
Total score:	438	out of 552
Average time: 	247.58	s / picture
Average time normalized:	242.78	s / picture *


SEEDS_2 is not a widely standardized sampler like Euler, DPM++, or DDIM. Instead, it appears to be a custom, experimental, or implementation-specific sampler, likely introduced in specialized tools such as ComfyUI, Kohya, or internal forks of Stable Diffusion. From naming conventions and community analysis, SEEDS_2 is most likely: a multi-seed variation sampler — designed to blend or interpolate outputs from multiple seeds in a structured way.


About:
- it is not deterministic
- Likely works across standard 20–30 step ranges
- CFG range between 6–10 (if based on standard diffusion)
- output is expressive, but may vary more wildly than traditional samplers
- best used for creative experiments, seed morphing, variation exploration


⚠️ Limitations
- Not part of official Stable Diffusion or Diffusers library
- May only work in specific UIs (like ComfyUI with custom nodes)
- Lacks academic documentation or peer-reviewed validation
- Behavior might change across implementations or updates


𝙋𝙞𝙘𝙩𝙪𝙧𝙚 𝙜𝙚𝙣𝙚𝙧𝙖𝙩𝙞𝙤𝙣 𝙨𝙚𝙩𝙩𝙞𝙣𝙜𝙨:
- 4 prompts (you can find them here: https://github.com/gctanita/understandingImageGeneration/blob/master/experimentPrompts.md )
- Each prompt was generated 8 times with different seeds (each seed was used across each prompt)
- 𝙎𝙩𝙚𝙥𝙨: 20
- 𝘾𝙁𝙂: 3
- 𝙒𝙞𝙙𝙩𝙝: 512
- 𝙃𝙚𝙞𝙜𝙝𝙩: 512
- 𝙎𝙘𝙝𝙚𝙙𝙪𝙡𝙚𝙧: simple


You can find the raw data here: 
- https://github.com/gctanita/understandingImageGeneration/blob/master/Samplers/SEEDS_2/seeds_2-raw-data.md


Scoring criteria for each series can be found here:
- https://github.com/gctanita/understandingImageGeneration/blob/master/Samplers/scoring_criteria.md


Hardware the setup:
- Graphic Card: NVIDIA GeForce RTX 4060 Ti with 8Gb VRAM 
- CPU: AMD Ryzen 5 5500, 3.60 GHz
- RAM: 32.0 GB, speed of 2400 MT/s 


For each image I gave it a score based on some on a set of subjective criteria designed to assess visual quality and consistency across different samplers. Each anomaly observed in the generated images deducted points from the total score, resulting in a binary scale (1 = acceptable, 0 = flawed). And for each image I recorded how much it took to generate them. Average normalized time means that I have eliminated the biggest 4 times from the series, that contained the loading of the model and / or parsing of the prompt for the first time. 