CFG variation - part 10
Images have been generated with seed 9823746521, and prompt **A cat made out of ice playing with a fireball, Ultrarealistic, hyper realistic, 8k, high definition**


Number of steps: 20
Sampler: ddim
Width: 512
Height: 512


When I created this prompt I was hoping to see a full cat made out of ice, not just the body of the cat. The body of the cat becomes less icy as the CFG increases. I would have expected the contrary. At CFG 14 the cat is just blue, with no ice present on it's body and the fireball has... cooled down into a more solid form. Again the CFG 14 provides the picture with too much contrast. Other than that, the cat body is anatomically correct. The only anomaly is that these cats have a loot of whiskers, but you will see them only if you are paying attention really close. 


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