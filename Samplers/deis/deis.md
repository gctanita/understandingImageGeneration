# DEIS

Average score: 13.78 out of 17.25
Total score: 441 out of 552
Average time: 131.39 s / picture
Average time normalized: 126.83 s / picture *

DEIS stands for Deterministic Elucidated Implicit Sampler — it is a relatively new sampler used in image generation with diffusion models like Stable Diffusion, ComfyUI, or AUTOMATIC1111. It’s part of the family of implicit samplers (like DDIM), but with more accurate ODE (Ordinary Differential Equation) solvers and higher-order step approximations, making it faster and more precise.


DEIS is:
- A deterministic sampler (same seed + prompt = same image).
- Designed to accelerate sampling (fewer steps needed).
- Based on elucidated diffusion models, which use a clearer mathematical framework to improve efficiency.
- A non-Markovian sampler like DDIM, but using more advanced mathematical approximations to better estimate how noise should be removed.


Technical Breakdown
- Built on top of the Elucidated Diffusion Model framework (by Karras et al.).
- DEIS reformulates the sampling process into an ODE, which allows it to compute the denoising path directly without randomness.
- Uses higher-order numerical solvers to approximate the denoising trajectory with more precision in fewer steps (e.g., 15–25 instead of 50–100).
- Often paired with custom noise schedules for better accuracy and flexibility.


✅ Pros 
- Deterministic – Same prompt + seed = same image (great for reproducibility)
- Fast sampling – High-quality results with fewer steps (as low as 15–20)
- Mathematically efficient – Uses advanced ODE solvers for better denoising precision
- Sharper, more coherent images – Especially in low-step scenarios
- No retraining required – Can be used with existing diffusion models
- Less noise/artifacts – Often cleaner than stochastic samplers
- Good at preserving structure – Better spatial consistency than DDIM

⚠️ Cons
- Less tested in community – Not as widely used or benchmarked as Euler or DPM++
- Lower output diversity – Deterministic nature may reduce variety in generations
- Sensitive to scheduler/configs – Requires proper noise schedule setup for best results
- May underperform in artistic randomness – Less "creative" than some stochastic samplers
- Not always supported – Some UIs or model configs may not yet offer DEIS
- Steeper learning curve – Fewer tutorials or community presets available


𝙋𝙞𝙘𝙩𝙪𝙧𝙚 𝙜𝙚𝙣𝙚𝙧𝙖𝙩𝙞𝙤𝙣 𝙨𝙚𝙩𝙩𝙞𝙣𝙜𝙨:
- 4 prompts (you can find them here: https://github.com/gctanita/understandingImageGeneration/blob/master/experimentPrompts.md )
- Each prompt was generated 8 times with different seeds (each seed was used across each prompt)
- 𝙎𝙩𝙚𝙥𝙨: 20
- 𝘾𝙁𝙂: 3
- 𝙒𝙞𝙙𝙩𝙝: 512
- 𝙃𝙚𝙞𝙜𝙝𝙩: 512
- 𝙎𝙘𝙝𝙚𝙙𝙪𝙡𝙚𝙧: simple


You can find the raw data here: 
- https://github.com/gctanita/understandingImageGeneration/blob/master/Samplers/deis/deis-raw-data.md


Scoring criteria for each series can be found here:
- https://github.com/gctanita/understandingImageGeneration/blob/master/Samplers/scoring_criteria.md


Hardware the setup:
- Graphic Card: NVIDIA GeForce RTX 4060 Ti with 8Gb VRAM 
- CPU: AMD Ryzen 5 5500, 3.60 GHz
- RAM: 32.0 GB, speed of 2400 MT/s 


For each image I gave it a score based on some on a set of subjective criteria designed to assess visual quality and consistency across different samplers. Each anomaly observed in the generated images deducted points from the total score, resulting in a binary scale (1 = acceptable, 0 = flawed). And for each image I recorded how much it took to generate them. Average normalized time means that I have eliminated the biggest 4 times from the series, that contained the loading of the model and / or parsing of the prompt for the first time. 



