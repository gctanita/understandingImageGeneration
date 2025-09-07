# DPMPP_2S_ANCESTRAL

Average score:	13.69	out of 17.25
Total score:	438	out of 552
Average time: 	247.34	s / picture
Average time normalized:	243.43	s / picture *


DPM++ 2S Ancestral is a second-order, single-step, stochastic sampler from the DPM++ family, designed to combine high-quality generation with increased diversity and creativity in the outputs. It’s one of the best options when you want natural randomness, variation between generations, and still maintain clean, sharp results.


About
- 20-30 steps usually gives good results
- not deterministic - same seed and prompt might give slightly different results
- faster than multistep samplers (2M, 3M)
- compatible with schedulers like Karras for optimal results
- output is varied, natural, slightly “noisy” in a good way


✅ Pros
- Stochastic — good for generating variations
- Higher accuracy than basic Euler a
- Produces crisp, detailed, and vibrant images
- Excellent for artistic prompts, portraits, environments
- Fast and efficient for high-quality outputs

⚠️ Cons
- Not deterministic — harder to reproduce exactly the same image
- May introduce subtle inconsistencies in fine detail (especially in upscaling workflows)
- Slightly less predictable than 2M or 2M CFG PP samplers


𝙋𝙞𝙘𝙩𝙪𝙧𝙚 𝙜𝙚𝙣𝙚𝙧𝙖𝙩𝙞𝙤𝙣 𝙨𝙚𝙩𝙩𝙞𝙣𝙜𝙨:
- 4 prompts (you can find them here: https://github.com/gctanita/understandingImageGeneration/blob/master/experimentPrompts.md )
- Each prompt was generated 8 times with different seeds (each seed was used across each prompt)
- 𝙎𝙩𝙚𝙥𝙨: 20
- 𝘾𝙁𝙂: 3
- 𝙒𝙞𝙙𝙩𝙝: 512
- 𝙃𝙚𝙞𝙜𝙝𝙩: 512
- 𝙎𝙘𝙝𝙚𝙙𝙪𝙡𝙚𝙧: simple


You can find the raw data here: 
- https://github.com/gctanita/understandingImageGeneration/blob/master/Samplers/DPMPP_2S_ANCESTRAL/dpmpp_2s_ancestral-raw-data.md


Scoring criteria for each series can be found here:
- https://github.com/gctanita/understandingImageGeneration/blob/master/Samplers/scoring_criteria.md


Hardware the setup:
- Graphic Card: NVIDIA GeForce RTX 4060 Ti with 8Gb VRAM 
- CPU: AMD Ryzen 5 5500, 3.60 GHz
- RAM: 32.0 GB, speed of 2400 MT/s 


For each image I gave it a score based on some on a set of subjective criteria designed to assess visual quality and consistency across different samplers. Each anomaly observed in the generated images deducted points from the total score, resulting in a binary scale (1 = acceptable, 0 = flawed). And for each image I recorded how much it took to generate them. Average normalized time means that I have eliminated the biggest 4 times from the series, that contained the loading of the model and / or parsing of the prompt for the first time. 