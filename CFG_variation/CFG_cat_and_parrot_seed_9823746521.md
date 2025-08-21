CFG variation - part 4
Images have been generated with seed 9823746521, and prompt **A blue fischer parrot dancing on top of a cat's head. Exactly 4 monarch butterfilies flying around the parrot. In front of the cat there are 5 balls, with planet patterns. The balls are in a puddle. Ultrarealistic, hyper realistic, 8k, high definition**


Number of steps: 20
Sampler: ddim
Width: 512
Height: 512


The cat from CFG 1 is diffrent from all the other cats. The parrot is indeed blue, but it is not a Blue fischer agapornis parrot in any of the images. As CFG increases so does the amount of contrast, making CFG yet again a winner of an unusable picture. From the point of view of the butterflies, the CFG 1 appears to be the most natural representation of them. In the rest of the images they seem a bit unnatural. However I am pleased that it managed to count both the butterfilies and the balls. Regarding the 3 legged parrot... uhh... I will not go into the lack of knowledge in the field of bird anatomy... CFG 14 did a good job with the parrot, but that's it's only saving grace.


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