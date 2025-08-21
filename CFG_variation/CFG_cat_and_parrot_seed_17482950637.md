CFG variation - part 5
Images have been generated with seed 17482950637, and prompt **A blue fischer parrot dancing on top of a cat's head. Exactly 4 monarch butterfilies flying around the parrot. In front of the cat there are 5 balls, with planet patterns. The balls are in a puddle. Ultrarealistic, hyper realistic, 8k, high definition**


Number of steps: 20
Sampler: ddim
Width: 512
Height: 512


These sets of images are pretty good, however to me CFG 1 picture seems to be the most realistic one. If only the butterflies had been a bit more integrated in the picture. The parrot still doesn't have the right breed, and the anatomy issues are present starting from CFG 3 to CFG 14. For CFG1 and CFG 2 the parrot at least is anatomicallty correct. The amount of contrast begins to be a bit too rich starting from CFG 8 to unusable from CFG 10 and 14. The cats are realistic and correct. And i am really happy that the model actually put 4 butterflies and the 5 planets asked in the prompt. Uell, excepting for CFG 14 that only has 3 butterflies. 


Qwen Image Template from ComfyUI
- Diffusion Model: 
  - qwen_image_fp8_e4m3fn.safetensors- Qwen image distill: 
  - qwen_image_distill_full_fp8_e4m3fn.safetensors
  - qwen_image_distill_full_bf16.safetensors
- CLIP: 
  - qwen_2.5_vl_7b_fp8_scaled.safetensors
- VAE: 
  - qwen_image_vae.safetensors
- LORA: 
  - Qwen-Image-Lightning-8steps-V1.0.safetensors