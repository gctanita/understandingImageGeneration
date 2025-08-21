CFG variation - part 11
Images have been generated with seed 17482950637, and prompt **A cat made out of ice playing with a fireball, Ultrarealistic, hyper realistic, 8k, high definition**


Number of steps: 20
Sampler: ddim
Width: 512
Height: 512


When I created this prompt I expected the full cat to be made out of ice. The icyest cat is the one provided by CFG 1. Then the cat's icyness drops up to CFG 10 and at CFG 14 dissapears alltogether. I would label the image produced by CFG 14 as a hallucination as the image is as far from realistic as one can get. 



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