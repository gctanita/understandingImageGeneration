CFG variation - part 1
Images have been generated with seed 9823746521, and prompt **A beautiful ballerina dancing on a stage with a dress made out of real fire. Ballerina's full body should be visible. Ultrarealistic, hyper realistic, 8k, high definition, realistic flames**


Number of steps: 20
Sampler: ddim
Width: 512
Height: 512


For CFG 1 we can see that there are 2 small anomalies: the hair is on fire, and so is one of the feet. From CFG 2 to CFG 8 they look fairly ok. CFG 10 is starting to have a bit too much contrast for my taste, and CFG 14 has so much contrast it makes the generated image unusable. 
Having used the same seed I would have expected for the ballerina to mentain her position with her feet, hands and body orientation, however as we can all see this is not the case. From CFG 2 to 3 the orientation of the body changed, and from CFG 6 to 8 the mosition of the hands changed. 


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