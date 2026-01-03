Task-02: Image Generation with Stable Diffusion
Overview
Use pre-trained Stable Diffusion model to generate images from text prompts.

Objective
Generate high-quality images from textual descriptions using state-of-the-art diffusion models.

Implementation Details
Model
Model: Stable Diffusion v1.5

Provider: RunwayML

Resolution: 512×512 pixels

Inference Steps: 30

Guidance Scale: 7.5

Prompts Used
"A futuristic city with flying cars at sunset"

"An astronaut riding a horse on Mars"

"A cat wearing a wizard hat, fantasy art"

"Cyberpunk street market at night"

"Peaceful lake in a fantasy forest"

Technical Setup
Platform: Google Colab

GPU: NVIDIA T4

Memory: ~8GB VRAM

Libraries: Diffusers, Transformers, PyTorch

Mixed Precision: FP16 enabled

Project Structure
text
Task-02-Image-Generation/
├── code/
│   └── stable_diffusion_generation.ipynb
├── outputs/
│   ├── images/
│   │   ├── image_1.png
│   │   ├── image_2.png
│   │   ├── image_3.png
│   │   ├── image_4.png
│   │   └── image_5.png
│   ├── all_images.png
│   └── prompts.txt
├── report/
│   └── Task-02-Report.pdf
└── README.md
Setup & Installation
Requirements
bash
pip install diffusers transformers accelerate torch pillow
Run in Google Colab
Open Google Colab with GPU

Copy the provided code

Run all cells

Images will generate automatically

Usage
Basic Generation
python
from diffusers import StableDiffusionPipeline

pipe = StableDiffusionPipeline.from_pretrained("runwayml/stable-diffusion-v1-5")
image = pipe("Your prompt here").images[0]
image.save("output.png")
Parameters
num_inference_steps: 20-50 (higher = better quality)

guidance_scale: 7.5 (controls prompt adherence)

height/width: 512 (standard resolution)

negative_prompt: Improve quality by specifying what to avoid

Generated Images
https://all_images.png

Image 1: Futuristic city with flying cars at sunset
Image 2: Astronaut riding horse on Mars
Image 3: Cat wearing wizard hat
Image 4: Cyberpunk street market
Image 5: Fantasy forest lake

Results
✅ Generated 5 high-quality images from text prompts

✅ Each image generated in ~30 seconds

✅ Images match prompt descriptions well

✅ Demonstrated text-to-image generation capability

Performance Metrics
Generation Time: ~2.5 minutes total

Image Quality: 512×512 resolution

Memory Usage: ~7.5GB VRAM

Model Loading: ~1 minute

Files Generated
image_1.png to image_5.png - Individual images

all_images.png - Grid of all images

prompts.txt - List of prompts used

Dependencies
diffusers 0.16+

transformers 4.30+

torch 2.0+

accelerate 0.20+

pillow 9.5+

References
Stable Diffusion Paper

Hugging Face Diffusers

RunwayML Stable Diffusion
