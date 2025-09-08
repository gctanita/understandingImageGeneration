# RES_MULTISTEP

Average score:	13.66	out of 17.25
Total score:	437	out of 552
Average time: 	132.44	s / picture
Average time normalized:	127.46	s / picture *


RES_MULTISTEP stands for Residual Multistep Sampler, an experimental and high-efficiency sampler that combines ideas from Multistep solvers (like DPM++) with residual estimation — refining predictions by using leftover (residual) error information. It aims to achieve faster sampling and better output quality with fewer steps by using previous step information to predict the next noise state more accurately.


About:
- multistep residual-enhanced ODE sampler
- it is deterministic
- 15–30 steps recommended
- slightly slower than Euler, faster than DPM++ 3M
- output quality is on par with DPM++ 2M, sharper than DDIM/LMS
- best for balanced photorealism + speed; portraits; fantasy scenes


✅ Pros
- Sharper output than DDIM or Euler at same step count
- Reduces artifacts caused by accumulated noise
- Good at structure preservation (eyes, faces, hands)
- Works well even with moderate CFG (7–10)
- More efficient than DPM++ 3M or ancestral samplers

⚠️ Cons
- Still experimental — may not be in every UI or stable release
- Slightly slower than Euler or Heun
- Less tested in very low (4–8) step ranges compared to LCM


𝙋𝙞𝙘𝙩𝙪𝙧𝙚 𝙜𝙚𝙣𝙚𝙧𝙖𝙩𝙞𝙤𝙣 𝙨𝙚𝙩𝙩𝙞𝙣𝙜𝙨:
- 4 prompts (you can find them here: https://github.com/gctanita/understandingImageGeneration/blob/master/experimentPrompts.md )
- Each prompt was generated 8 times with different seeds (each seed was used across each prompt)
- 𝙎𝙩𝙚𝙥𝙨: 20
- 𝘾𝙁𝙂: 3
- 𝙒𝙞𝙙𝙩𝙝: 512
- 𝙃𝙚𝙞𝙜𝙝𝙩: 512
- 𝙎𝙘𝙝𝙚𝙙𝙪𝙡𝙚𝙧: simple


You can find the raw data here: 
- https://github.com/gctanita/understandingImageGeneration/blob/master/Samplers/RES_MULTISTEP/res_multistep-raw-data.md


Scoring criteria for each series can be found here:
- https://github.com/gctanita/understandingImageGeneration/blob/master/Samplers/scoring_criteria.md


Hardware the setup:
- Graphic Card: NVIDIA GeForce RTX 4060 Ti with 8Gb VRAM 
- CPU: AMD Ryzen 5 5500, 3.60 GHz
- RAM: 32.0 GB, speed of 2400 MT/s 


For each image I gave it a score based on some on a set of subjective criteria designed to assess visual quality and consistency across different samplers. Each anomaly observed in the generated images deducted points from the total score, resulting in a binary scale (1 = acceptable, 0 = flawed). And for each image I recorded how much it took to generate them. Average normalized time means that I have eliminated the biggest 4 times from the series, that contained the loading of the model and / or parsing of the prompt for the first time. 