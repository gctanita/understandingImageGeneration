# A Journey to Test and Understand Image Generation

I embark on this journey with a trusty Graphics Card to explore the world of image generation. 

So, let's start with the beggining, and specify the setup:
- Graphic Card: NVIDIA GeForce RTX 4060 Ti with 8Gb VRAM 
- CPU: AMD Ryzen 5 5500, 3.60 GHz
- RAM: 32.0 GB, speed of 2400 MT/s 

First VLM setup: Qwen Image Template from ComfyUI
- Diffusion Model: 
  - [qwen_image_fp8_e4m3fn.safetensors](https://huggingface.co/Comfy-Org/Qwen-Image_ComfyUI/resolve/main/split_files/diffusion_models/qwen_image_fp8_e4m3fn.safetensors)
  - A diffusion model is a generative model that learns to transform random noise into structured data (like images or audio) by reversing a noise-adding process through iterative denoising steps.
- Qwen image distill: 
  - [qwen_image_distill_full_fp8_e4m3fn.safetensors](https://huggingface.co/Comfy-Org/Qwen-Image_ComfyUI/resolve/main/non_official/diffusion_models/qwen_image_distill_full_fp8_e4m3fn.safetensors)
  - [qwen_image_distill_full_bf16.safetensors](https://huggingface.co/Comfy-Org/Qwen-Image_ComfyUI/resolve/main/non_official/diffusion_models/qwen_image_distill_full_bf16.safetensors)
  - Image distill means training a smaller vision encoder (student) to imitate a larger, more powerful model’s (teacher’s) image representations, so the VLM can keep strong multimodal abilities while being lighter and faster.
- CLIP: 
  - [qwen_2.5_vl_7b_fp8_scaled.safetensors](https://huggingface.co/Comfy-Org/Qwen-Image_ComfyUI/resolve/main/split_files/text_encoders/qwen_2.5_vl_7b_fp8_scaled.safetensors)
  - CLIP = Contrastive Language–Image Pre-training, a model that aligns images and text by mapping them into the same embedding space. It’s the backbone of many VLMs because it gives them the ability to understand and connect visual data with language.
- VAE: 
  - [qwen_image_vae.safetensors](https://huggingface.co/Comfy-Org/Qwen-Image_ComfyUI/resolve/main/split_files/vae/qwen_image_vae.safetensors)
  - VAE = Variational Autoencoder, a model that compresses images into a latent representation and reconstructs them back. In VLMs, it’s used to efficiently bridge the gap between image pixels and language embeddings, enabling multimodal alignment and faster processing.
- LORA: 
  - [Qwen-Image-Lightning-8steps-V1.0.safetensors](https://huggingface.co/lightx2v/Qwen-Image-Lightning/resolve/main/Qwen-Image-Lightning-8steps-V1.0.safetensors)
  - LoRA = Low-Rank Adaptation, a method to fine-tune VLMs efficiently by training small adapter layers instead of updating the whole model. It makes customizing large VLMs practical, fast, and lightweight.

  



