CFG variation - part 2
Images have been generated with seed 17482950637, and prompt **A beautiful ballerina dancing on a stage with a dress made out of real fire. Ballerina's full body should be visible. Ultrarealistic, hyper realistic, 8k, high definition, realistic flames**


Number of steps: 20
Sampler: ddim
Width: 512
Height: 512


Excepting the last image, with CFG 14 that has an insane amount of contrast, all the other pictures look good. Further more the ballerina has maintained the position of her arms, head, feet and body. However the diffrences between the pictures are very small... hair band isdifferent, the flames slightlty differ, and for CFG 10 the stage is on fire. 


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