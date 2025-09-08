# IPNDM_V

Average score:	8.59	out of 17.25
Total score:	275	out of 552
Average time: 	133.81	s / picture
Average time normalized:	126.83	s / picture *

IPNDM_V stands for Implicit Predictive Noise Diffusion Model – V-prediction, and it is a variant of the IPNDM sampler that specifically uses the "v-prediction" noise format, which is one of the internal ways modern diffusion models (like Stable Diffusion v2+) represent denoising steps. It is experimental, fast, designed for models trained with v-prediction (instead of epsilon- or score-prediction) and used in ComfyUI, Kohya_ss, and other advanced frameworks.


About:
- It is deterministic
- 10-30 steps recommended
- Very fast
- Output quality is reasonable, but not ultra-detailed
- Best for previews, fast renders, mobile diffusion apps


✅ Pros
- Extremely fast
- Tailored for v-prediction models
- Deterministic
- Good for previewing prompts, concept iteration, or low-power devices

⚠️ Cons
- Not suitable for realism or detailed anatomy (faces, hands, etc.)
- Slightly less detailed than ipndm with epsilon-prediction
- Limited to v-prediction models (won’t work with older SD1.5-based pipelines)


𝙋𝙞𝙘𝙩𝙪𝙧𝙚 𝙜𝙚𝙣𝙚𝙧𝙖𝙩𝙞𝙤𝙣 𝙨𝙚𝙩𝙩𝙞𝙣𝙜𝙨:
- 4 prompts (you can find them here: https://github.com/gctanita/understandingImageGeneration/blob/master/experimentPrompts.md )
- Each prompt was generated 8 times with different seeds (each seed was used across each prompt)
- 𝙎𝙩𝙚𝙥𝙨: 20
- 𝘾𝙁𝙂: 3
- 𝙒𝙞𝙙𝙩𝙝: 512
- 𝙃𝙚𝙞𝙜𝙝𝙩: 512
- 𝙎𝙘𝙝𝙚𝙙𝙪𝙡𝙚𝙧: simple


You can find the raw data here: 
- https://github.com/gctanita/understandingImageGeneration/blob/master/Samplers/IPNDM_V/ipndm_v-raw-data.md


Scoring criteria for each series can be found here:
- https://github.com/gctanita/understandingImageGeneration/blob/master/Samplers/scoring_criteria.md


Hardware the setup:
- Graphic Card: NVIDIA GeForce RTX 4060 Ti with 8Gb VRAM 
- CPU: AMD Ryzen 5 5500, 3.60 GHz
- RAM: 32.0 GB, speed of 2400 MT/s 


For each image I gave it a score based on some on a set of subjective criteria designed to assess visual quality and consistency across different samplers. Each anomaly observed in the generated images deducted points from the total score, resulting in a binary scale (1 = acceptable, 0 = flawed). And for each image I recorded how much it took to generate them. Average normalized time means that I have eliminated the biggest 4 times from the series, that contained the loading of the model and / or parsing of the prompt for the first time. 