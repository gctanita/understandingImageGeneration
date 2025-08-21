CFG variation - part 8
Images have been generated with seed 17482950637, and prompt **A beautiful flower,  Ultrarealistic, hyper realistic, 8k, high definition**

Number of steps: 20
Sampler: ddim
Width: 512
Height: 512


The flowers from CFG 3 to CFG 10 seem a bit more realistic, but they have in the center of the flower anoter flower bud. while CFG 1, 2 and 14 do not have this anomaly the amount of contrast and petal form makes them feel a bit unreal. 


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