# Sampler data - Theory vs Experimental Data

First of all a couple of words about the table. Due to big quantity of data, I took the ChatGpt shorcut, and extracted with it's help the theory part: if it's deterministic, the speed, number of steps and for what each sampler is best used for. For the experimental data, I took the generated pictures and scores and did the math for them. 

The scoring of the pictures was done using the criteria discribed here: https://github.com/gctanita/understandingImageGeneration/blob/master/Samplers/scoring_criteria.md for each picture. I tried to have consistency over the scoring, however since it is subjective and had to be done over a bigger spawn of time (because there were a lot of pictures to be graded - 1280 pictures to be more exact), let's just say my inner QA is not that happy, however I still believe that even with this variance in the data, it can still give us some insights. We have 2 areas that we can analyze here: Score and Time.

## SCORE in relation to Steps
### Score 0
I am going to highlight here the outliers. First of all we have those that scored 0 - basically they produced noise. Our candidates are:
- DPMPP_2M_CFG_PP	- recommended steps => 20–50
- DPMPP_2S_ANCESTRAL_CFG_PP	- recommended steps => 25–50
- GRADIENT_ESTIMATION_CFG_PP	- recommended steps => 50–100
- RES_MULTISTEP_ANCESTRAL_CFG_PP	- recommended steps => 25–45
- RES_MULTISTEP_CFG_PP	- recommended steps => 20–40

So:
- For DPMPP_2M_CFG_PP and RES_MULTISTEP_CFG_PP even though our experiment was at 20 steps, and 20 is the lower boundry of the interval, I would have expected to at least get some decently usable pictures. 
- For DPMPP_2S_ANCESTRAL_CFG_PP and RES_MULTISTEP_ANCESTRAL_CFG_PP ok, 20 was a bit low for them, but the pictures should have at least hinted at the forms.
- For GRADIENT_ESTIMATION_CFG_PP, ok 50-100 is really far away... 

### Score 25% to 40%
The next group of samplers, scored in the range of 25%-45% - leaving me with the impression that in order to score higher, they would have needed more steps.
- RES_MULTISTEP_ANCESTRAL	=> steps: 25–45	 => score: 26.45%
- DDPM	=> steps: 250–1000+	 => score: 31.52%

So:
- another outlier is DDPM that has a crazy amount of steps recommended, and for that sum, I feel it did a decent job at just 20 steps... 
- RES_MULTISTEP_ANCESTRAL was below the recomended number of steps, so perhaps it would have generated better pictures at higher steps


### Score 40% to 60%
- DPM_FAST	=> steps: 10–25	 => score: 41.67%
- DPM_ADAPTIVE	=> steps: 20–40	 => score: 45.11%
- IPNDM_V	=> steps: 20–40	 => score: 49.82%
- LMS	=> steps: 30–50	 => score: 59.06%

So:
- the main outlier here is DPM_FAST that should have performed quite well, given the fact that 20 is within the upper part of the iterval
- for DPM_ADAPTIVE and IPNDM_V 20 steps is in the interval even if it is the lower part of it, would have expected better
- LMS - ok, fair enough, it's probably would have needed more steps, but still reaching a score of almost 60% I'd say it's decent


### Score 60% to 80%
In this interval there are 21 samplers, so I will only take the outliers here, instead of going through all of them:

- First on my list is LCM



EULER_CFG_PP
EULER_ANCESTRAL_CFG_PP
DPMPP_3M_SDE
DPMPP_3M_SDE_GPU
LCM
SA_SOLVER
UNI_PC_BH2
DPM_2_ANCESTRAL
DPMPP_SDE
EULER_ANCESTRAL
HEUN
DPMPP_SDE_GPU
RES_MULTISTEP
DPMPP_2S_ANCESTRAL
IPNDM
SEEDS_2
DPMPP_2M
DPMPP_2M_SDE_GPU
DEIS
DPMPP_2M_SDE
UNI_PC




|	Sampler name	|	Deterministic	|	Speed	|	Steps	|	Best for	|		|	AVG time	|	AVG time normalized	|	AVG score	|	AVG score %	|	Total score	|	Total Score %	|
|	---------------------	|	---------------------	|	---------------------	|	---------------------	|	---------------------	|	---------------------	|	---------------------	|	---------------------	|	---------------------	|	---------------------	|	---------------------	|	---------------------	|
|	DDIM	|	YES	|	FAST	|	25–50	|	fast, deterministic image generation with consistent structure, making it ideal for img2img tasks, style transfers, and reproducible results across runs	|		|	134.41	|	125.88	|	14.03	|	81.34%	|	449	|	81.34%	|
|	DDPM	|	NO	|	SLOW	|	250–1000+	|	high-fidelity, natural-looking image generation in research, benchmarking, or scenarios that prioritize detail and smooth gradients over speed	|		|	130.59	|	126.02	|	5.44	|	31.52%	|	174	|	31.52%	|
|	DEIS	|	YES	|	VERY FAST	|	15–30	|	fast, deterministic image generation with sharp structure and minimal steps, making it ideal for real-time rendering, previews, and low-latency applications	|		|	131.39	|	126.70	|	13.78	|	79.89%	|	441	|	79.89%	|
|	DPM_2	|	YES	|	MODERATE	|	20–50	|	high-quality images with added creative variation, making it ideal for fantasy scenes, artistic compositions, and concept art where controlled randomness enhances visual richness.	|		|	246.05	|	242.49	|	14.03	|	81.34%	|	449	|	81.34%	|
|	DPM_2_ANCESTRAL	|	NO	|	FAST	|	25–50	|	expressive and detailed images with a touch of randomness, making it ideal for fantasy scenes, stylized portraits, and other creative visuals where variety and richness are desired	|		|	246.11	|	242.64	|	13.56	|	78.62%	|	434	|	78.62%	|
|	DPM_ADAPTIVE	|	YES	|	FAST	|	20–40	|	generating high-quality images with dynamic step allocation, making it ideal for situations requiring a balance between speed and detail, such as general-purpose prompts, previews, and adaptive rendering.	|		|	241.71	|	235.24	|	7.78	|	45.11%	|	249	|	45.11%	|
|	DPM_FAST	|	YES	|	VERY FAST	|	10–25	|	generation with acceptable quality, making it ideal for real-time previews, iterative testing, and low-latency applications where speed is more important than fine detail.	|		|	128.61	|	125.53	|	7.19	|	41.67%	|	230	|	41.67%	|
|	DPMPP_2M	|	YES	|	MODERATE	|	20–50	|	generating photorealistic images with excellent structure and fine detail, ideal for portraits and architecture.	|		|	131.12	|	125.87	|	13.72	|	79.53%	|	439	|	79.53%	|
|	DPMPP_2M_CFG_PP	|	YES	|	MODERATE	|	20–50	|	high-precision image generation with strong prompt adherence, ideal for complex scenes with high CFG values.	|		|	133.14	|	127.61	|	0.00	|	0.00%	|	0	|	0.00%	|
|	DPMPP_2M_SDE	|	YES	|	MODERATE	|	20–50	|	stable, detailed outputs with smooth gradients, ideal for soft lighting and natural scenery.	|		|	129.68	|	126.46	|	13.78	|	79.89%	|	441	|	79.89%	|
|	DPMPP_2M_SDE_GPU	|	YES	|	FAST	|	20–50	|	fast, high-quality image generation on GPU, suitable for production environments needing both speed and fidelity.	|		|	133.73	|	126.47	|	13.72	|	79.53%	|	439	|	79.53%	|
|	DPMPP_2S_ANCESTRAL	|	NO	|	FAST	|	25–50	|	expressive and varied outputs, making it ideal for fantasy art, concept design, and creative variation.	|		|	247.34	|	243.33	|	13.69	|	79.35%	|	438	|	79.35%	|
|	DPMPP_2S_ANCESTRAL_CFG_PP	|	NO	|	FAST	|	25–50	|	high-variation, prompt-adherent outputs in stylized or chaotic scenes, useful in concept art and imaginative prompts.	|		|	255.74	|	244.84	|	0.00	|	0.00%	|	0	|	0.00%	|
|	DPMPP_3M_SDE	|	YES	|	SLOW	|	30–60	|	ultra-high-quality, detailed renders with smooth transitions, ideal for professional-level illustration and realism.	|		|	130.51	|	126.67	|	12.00	|	69.57%	|	384	|	69.57%	|
|	DPMPP_3M_SDE_GPU	|	YES	|	MODERATE	|	30–60	|	generating premium quality images efficiently on GPU, ideal for batch processing and high-end projects.	|		|	130.21	|	126.18	|	12.25	|	71.01%	|	392	|	71.01%	|
|	DPMPP_SDE	|	YES	|	MODERATE	|	20–50	|	general high-fidelity tasks with smooth denoising, suitable for natural scenes and consistent compositions.	|		|	253.51	|	248.01	|	13.56	|	78.62%	|	434	|	78.62%	|
|	DPMPP_SDE_GPU	|	YES	|	FAST	|	20–50	|	producing clean, realistic images quickly on GPU, ideal for pipelines that require efficiency and visual consistency.	|		|	248.74	|	243.71	|	13.66	|	79.17%	|	437	|	79.17%	|
|	ER_SDE	|	YES	|	FAST	|	20–40	|	fast and stable image generation with good balance between realism and variation, ideal for iterative creative workflows.	|		|	129.72	|	126.02	|	13.84	|	80.25%	|	443	|	80.25%	|
|	EULER	|	YES	|	FAST	|	20–40	|	clean and fast image generation with strong structure, great for portraits, buildings, and prompt-faithful outputs.	|		|	132.70	|	125.61	|	14.13	|	81.88%	|	452	|	81.88%	|
|	EULER_ANCESTRAL	|	NO	|	FAST	|	20–40	|	producing more creative and slightly chaotic results, excellent for concept art and fantasy themes.	|		|	128.14	|	125.33	|	13.56	|	78.62%	|	434	|	78.62%	|
|	EULER_ANCESTRAL_CFG_PP	|	NO	|	FAST	|	20–40	|	varied and expressive scenes while maintaining prompt fidelity, ideal for imaginative storytelling visuals.	|		|	127.78	|	125.41	|	11.75	|	68.12%	|	376	|	68.12%	|
|	EULER_CFG_PP	|	YES	|	FAST	|	20–40	|	producing sharp, prompt-consistent images with strong CFG guidance, great for structured compositions.	|		|	127.82	|	125.35	|	10.50	|	60.87%	|	336	|	60.87%	|
|	GRADIENT_ESTIMATION	|	YES	|	SLOW	|	50–100	|	experimental or fine-control environments for precise gradient-based sampling.	|		|	129.90	|	125.75	|	14.03	|	81.34%	|	449	|	81.34%	|
|	GRADIENT_ESTIMATION_CFG_PP	|	YES	|	SLOW	|	50–100	|	finely tuned, prompt-adherent outputs in research or precision-demanding applications.	|		|	130.63	|	126.35	|	0.00	|	0.00%	|	0	|	0.00%	|
|	HEUN	|	YES	|	FAST	|	20–40	|	stable image generation with good quality and predictable behavior, suitable for general-purpose use.	|		|	245.10	|	242.16	|	13.59	|	78.80%	|	435	|	78.80%	|
|	HEUNPP2	|	YES	|	FAST	|	20–40	|	slightly more expressive, yet stable outputs, ideal for moderate creativity and realism balance.	|		|	356.50	|	353.20	|	13.91	|	80.62%	|	445	|	80.62%	|
|	IPNDM	|	YES	|	MODERATE	|	20–40	|	efficient and robust sampling with good image fidelity, great for structured and deterministic outputs.	|		|	129.35	|	125.81	|	13.69	|	79.35%	|	438	|	79.35%	|
|	IPNDM_V	|	YES	|	MODERATE	|	20–40	|	variation-tolerant tasks needing stability, such as dynamic compositions with consistent output patterns.	|		|	133.81	|	126.73	|	8.59	|	49.82%	|	275	|	49.82%	|
|	LCM	|	NO	|	VERY FAST	|	4–12	|	ultra-fast generation with few steps, ideal for real-time previews, mobile apps, or rapid concept iteration.	|		|	130.56	|	126.60	|	13.00	|	75.36%	|	416	|	75.36%	|
|	LMS	|	YES	|	MODERATE	|	30–50	|	structured, clean images with smooth color transitions, often used in traditional Stable Diffusion pipelines.	|		|	128.45	|	125.50	|	10.19	|	59.06%	|	326	|	59.06%	|
|	RES_MULTISTEP	|	YES	|	MODERATE	|	20–40	|	structured and consistent outputs using residual sampling, ideal for detailed scenes with high fidelity.	|		|	132.44	|	127.22	|	13.66	|	79.17%	|	437	|	79.17%	|
|	RES_MULTISTEP_ANCESTRAL	|	NO	|	MODERATE	|	25–45	|	adding controlled randomness and texture to high-detail images, great for environmental or fantasy art.	|		|	130.40	|	125.90	|	4.56	|	26.45%	|	146	|	26.45%	|
|	RES_MULTISTEP_ANCESTRAL_CFG_PP	|	NO	|	MODERATE	|	25–45	|	prompt-faithful yet expressive images in artistic or stylized outputs.	|		|	131.36	|	125.78	|	0.00	|	0.00%	|	0	|	0.00%	|
|	RES_MULTISTEP_CFG_PP	|	YES	|	MODERATE	|	20–40	|	highly accurate and structured results where strong CFG guidance is important.	|		|	132.52	|	125.87	|	0.00	|	0.00%	|	0	|	0.00%	|
|	SA_SOLVER	|	NO	|	FAST	|	20–35	|	fast and expressive sampling with controlled chaos, perfect for creative experimentation.	|		|	138.18	|	126.21	|	13.19	|	76.45%	|	422	|	76.45%	|
|	SA_SOLVER_PECE	|	NO	|	FAST	|	20–35	|	structured outputs with slightly smoother transitions, suitable for balanced creative scenes.	|		|	244.62	|	238.78	|	13.91	|	80.62%	|	445	|	80.62%	|
|	SEEDS_2	|	NO	|	MODERATE	|	25–45	|	blending characteristics of two images or styles using two seeds, ideal for hybrid concept generation.	|		|	247.58	|	242.78	|	13.69	|	79.35%	|	438	|	79.35%	|
|	SEEDS_3	|	NO	|	MODERATE	|	25–45	|	creative fusion of three seed variations, great for artistic morphing or ideation through seed interpolation.	|		|	369.14	|	360.73	|	13.84	|	80.25%	|	443	|	80.25%	|
|	UNI_PC	|	YES	|	VERY FAST	|	15–30	|	fast, high-quality deterministic generation at low step counts, ideal for real-time workflows and previews.	|		|	130.89	|	125.89	|	13.78	|	79.89%	|	441	|	79.89%	|
|	UNI_PC_BH2	|	YES	|	VERY FAST	|	15–30	|	high-precision deterministic outputs with improved smoothness and speed, great for low-latency, consistent renders.	|		|	130.44	|	125.90	|	13.25	|	76.81%	|	424	|	76.81%	|
																								
																								
