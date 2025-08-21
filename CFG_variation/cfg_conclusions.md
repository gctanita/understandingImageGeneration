# Conclusion on CFG Experiments

After running multiple prompts with different seeds and comparing outputs across CFG values (1 through 14), several consistent patterns emerged for Qwen Image VLM:

- **CFG 1–2**
  - Images tend to look more natural and less exaggerated.
  - However, anomalies often appear (anatomy mistakes, misplaced elements, odd textures).
  - These images sometimes lack the intended intensity of detail.

- **CFG 3–8**
  - This range consistently provides the most balanced results.
  - Poses, structures, and elements are usually stable, while still showing variety in textures and details.
  - The prompts are respected reasonably well, with fewer hallucinations.

- **CFG 10**
  - Contrast becomes noticeably stronger.
  - Some images remain usable, but saturation and detail sharpness often go beyond realism.
  - Elements of the scene may start to distort (burning stages, extra anatomical features, etc.).

- **CFG 14**
  - Almost every set showed images that were oversaturated, overly contrasted, and often unusable.
  - Anatomical and structural correctness breaks down more frequently.
  - Instead of enhancing realism, this CFG level introduces artifacts and “hallucinations.”

- **Seed Stability**
  - Same seed does not guarantee identical positioning of body parts, objects, or orientation across CFG values.
  - Lower seeds sometimes produced larger differences (body orientation changes, missing objects).
  - Some seeds were more consistent (maintaining pose, structure) but only with minor cosmetic differences.