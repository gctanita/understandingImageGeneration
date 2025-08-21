CFG variation - part 12
Images have been generated with seed 65910248395, and prompt **A cat made out of ice playing with a fireball, Ultrarealistic, hyper realistic, 8k, high definition**


Number of steps: 20
Sampler: ddim
Width: 512
Height: 512


When I created this prompt I was hoping to see a full cat made out of ice, not just the body of the cat. The body of the cat becomes less icy as the CFG increases. I would have expected the contrary. At CFG 14 the cat is just blue, with no ice present on it's body and the fireball has... cooled down into a more solid form. Again the CFG 14 provides the picture with too much contrast. The cats from CFG 1 to 4 have the ice more refined, more close to the natural form of the cat body. The chunkyness of the ice increases from CFG 6 to CFG 10, and at CFG 14 dissapears altogether. 


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

