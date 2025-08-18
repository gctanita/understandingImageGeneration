# What does LoRA mean?

## 1. Definition
**LoRA** stands for **Low-Rank Adaptation**.  
It’s a parameter-efficient fine-tuning technique that lets you adapt a **large model** (like a VLM) to new tasks or domains **without retraining all of its parameters**.  



## 2. How it works
- Instead of updating the entire huge model (billions of parameters), LoRA adds **small trainable matrices** (low-rank adapters) into the model’s layers.  
- During fine-tuning:
  - The **base model stays frozen** (unchanged).  
  - Only the **small adapter parameters** are trained.  
- At inference time, the outputs from the base model and the adapters are **combined**, giving you the effect of a fine-tuned model.  

This means much lower compute, memory, and storage requirements.



## 3. Why LoRA is useful in VLMs
- VLMs (like CLIP, LLaVA, Stable Diffusion with text encoders, GPT-4V-style models) are **very large**, making full fine-tuning expensive.  
- LoRA allows:
  - **Domain adaptation**: e.g., adapting a VLM to medical images, satellite imagery, or art styles.  
  - **Personalization**: fine-tuning on a small dataset (e.g., product catalog, specific object types).  
  - **Fast prototyping**: train small adapters for many tasks without retraining the whole model.  



## 4. Example in VLMs
- You have a pretrained VLM (e.g., **CLIP + LLaMA** in LLaVA).  
- You want it to work better on **X-ray scans**.  
- Instead of retraining the full image encoder + language model, you train **LoRA adapters** on a small dataset of X-ray + text pairs.  
- The result: the VLM learns the new domain while still retaining its general vision-language abilities.

---

**In short:**  
**LoRA = Low-Rank Adaptation**, a method to fine-tune VLMs efficiently by training small adapter layers instead of updating the whole model.  
It makes customizing large VLMs practical, fast, and lightweight.
