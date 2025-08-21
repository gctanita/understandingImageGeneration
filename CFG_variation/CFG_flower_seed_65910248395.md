CFG variation - part 9
Images have been generated with seed 65910248395, and prompt **A beautiful flower,  Ultrarealistic, hyper realistic, 8k, high definition**

Number of steps: 20
Sampler: ddim
Width: 512
Height: 512


All the flowers generated with this seed present the flower in the center of the flower anomaly. CFG 10 and CFG 14 seem to be unreal due to the structure of the petals and the high amount of contrast. If we are to ignore the anomaly the rest of the flowers seem real and well made. 


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