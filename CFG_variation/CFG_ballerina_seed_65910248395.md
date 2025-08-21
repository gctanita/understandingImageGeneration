CFG variation - part 3
Images have been generated with seed 65910248395, and prompt **A beautiful ballerina dancing on a stage with a dress made out of real fire. Ballerina's full body should be visible. Ultrarealistic, hyper realistic, 8k, high definition, realistic flames**


Number of steps: 20
Sampler: ddim
Width: 512
Height: 512


Having used the same seed number I would have expected for the ballerina to have the same orientation of her hands, feet, body and dress. For CFG 10 the amount of contrast is a bit too rich, and as usual CFG 14 has way too much contrast rendering the photo unusable. The structure of the dress is similar from CFG 3 to CFG 14, having CFG 1 and 2 with a difftrent pisition of the hands and slightly different dress. 


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