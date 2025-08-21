Steps variation - part 7
Images have been generated with seed 9823746521, and prompt **A beautiful flower,  Ultrarealistic, hyper realistic, 8k, high definition**


CFG: 3
Sampler: ddim
Width: 512
Height: 512


Each step generated adds extra sharpness, however this costs time and computation power. So the question is how much is enough? One step takes about 10 seconds (on these settings, and on my setup), and about 16 seconds for 2 steps to about 140 seconds for 20 steps. In this series I can't see an obvious improvement for pictures once the steps increase above 15 steps. The orientation of the flowers changed from 15 steps upward. Image at 5 steps is a flower with less petals, but very blury overall. At 10 steps the flower is almost at the final version with a slight blur.


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