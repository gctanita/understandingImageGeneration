# Image Parameters 

When generating images you will have to set up some image parameters. Let's go through the most common ones and what they mean.

## Steps
The steps parameter controls how many refinement passes the diffusion model makes when turning noise into an image. More steps = higher quality but slower. Fewer steps = faster but often lower quality.

### How it affects generation
- **More steps**:
  - Image goes through finer, more gradual refinements.
  - Usually results in higher detail and fidelity.
  - But generation takes longer.
- **Fewer steps**:
  - The model denoises in bigger jumps.
  - Much faster.
  - But may lead to blurry, less accurate, or artifact-heavy images.

## CFG
The CFG = Classifier-Free Guidance (sometimes called “guidance scale”) parameter controls how strongly the image generation process follows your text prompt.
- **Low CFG** = looser, more creative images.
- **Medium CFG** = balanced, realistic results.
- **High CFG** = very literal, but can distort realism.

### How it works
- During generation, the model considers two versions of the denoising process at each step:
  - **Unconditional path** → generates an image without the text prompt (just from noise).
  - **Conditional path** → generates an image guided by your text prompt.
- The CFG scale decides how much weight to give to the conditional path vs. the unconditional path.

### Effect of CFG values
- Low CFG (1–3):
  - The model doesn’t stick strongly to your prompt.
  - Images may be more “creative” or abstract, sometimes unrelated.
- Medium CFG (6–8):
  - Good balance — the image follows your prompt while still looking natural.
  - Most default settings use this range.
- High CFG (12+):
  - The model follows the prompt very strictly.
  - But images can look unnatural, over-saturated, distorted, or less photorealistic.

At least this is the theory. Based on model and number of steps, these intervals might be very different. Unfortunatley you can only see through experimentation what the sweet spot is for you.

## Sampler 
The sampler parameter decides the algorithmic path the diffusion model takes to transform noise into an image.
- A sampler is the algorithm used to perform the denoising process in a diffusion model.
- Remember: image generation starts with random noise and removes it step by step, guided by your text prompt.
- The sampler controls how noise is removed across the steps — the “path” the model takes from noise → final image.
So different samplers = different balance of speed, sharpness, realism, and creativity.

### How it affects generation
- Using the same prompt & CFG, different samplers can create noticeably different images.
- Some are better at photorealism (like DPM++ 2M Karras).
- Some are better for creative/artistic looks (like Euler a).
- Faster samplers (like DDIM) are useful for previews.

## Seed
- A seed is the **starting point** for the random noise that kicks off the diffusion process.
- Since image generation begins with random noise that gets denoised step by step, the seed determines the exact initial noise pattern.
- That noise pattern strongly influences the final image.

### Why it matters
- **Same seed + same prompt + same settings** → will always give you the same image (deterministic).
- **Different seeds** → different variations of the image, even if the prompt is identical.
This makes the seed like a “random variation ID” for image generation.

## Width and Height 
Width and Height define the resolution of the output image in pixels.

### How they affect generation
- **Aspect ratio**:
  - Controls whether the image is square, landscape, or portrait.
  - Important for fitting the subject (e.g., portraits vs. wide scenery).
- **Detail & quality**:
  - Larger dimensions = more room for fine details.
  - Smaller dimensions = faster generation but less detail.
- **Compute cost**:
  - Bigger images require more VRAM and longer processing time.
  - Doubling both width and height increases pixel count by 4× (so compute scales fast).