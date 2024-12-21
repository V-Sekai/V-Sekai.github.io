# Draft: Character Concept Art Creation

## The Context

V-Sekai aims to provide a versatile platform for creating and experiencing virtual worlds. Character creation is a crucial aspect of this process, and concept art plays a vital role in visualizing and refining character designs before 3D modeling. This proposal focuses on integrating Easy Diffusion and TRELLIS to streamline this workflow.

## The Problem Statement

Generating high-quality, 3D-ready concept art often requires significant artistic skill and time. While AI art generators like Stable Diffusion, particularly with the FLUX model, can expedite this process, setting it up and ensuring the generated art is compatible with 3D modeling tools like TRELLIS requires technical expertise and careful optimization.

## Describe how your proposal will work with code, pseudo-code, mock-ups, or diagrams

This proposal outlines a workflow using Easy Diffusion for generating concept art optimized for TRELLIS, leveraging AI to accelerate character creation in V-Sekai.

### 1. Easy Diffusion Setup

Easy Diffusion provides a user-friendly interface for Stable Diffusion. We will use it with the FLUX model for generating character concepts.

- Install Easy Diffusion.
- Download the FLUX model and necessary LoRAs (CharacterDesign-FluxV2, Flux DetailerV2).
- Configure Easy Diffusion with the FLUX model and LoRAs.

[concept_prompt.json](attachments/concept_prompt.json)

### 2. Optimized Prompting in Easy Diffusion

**Settings:**

- Set the width and height to 1024 pixels.

### 3. TRELLIS Setup and Execution

TRELLIS will be used for generating 3D models from the generated concept art.

- Install Docker Desktop.
- Install WSL2 with a compatible Linux distribution (e.g., Ubuntu).
- Configure Docker Desktop to utilize the WSL2 backend.
- Ensure GPU access is enabled within WSL2.
- Execute TRELLIS within WSL2 using the following command in Powershell:

```powershell
docker run -it -p 7860:7860 --gpus all registry.hf.space/jeffreyxiang-trellis:latest python app.py
```

### 4. Iterative Refinement

The process emphasizes iterative refinement of the prompt based on TRELLIS conversion results. This cyclical process ensures the generation of 3D-ready concept art.

### Workflow

1.  **Define Core Concept:** Establish the character's essential characteristics.
2.  **Craft Optimized Prompt:** Create a concise, TRELLIS-friendly prompt using the provided structure and Easy Diffusion.
3.  **Generate and Evaluate:** Produce images and assess their 3D conversion suitability in TRELLIS.
4.  **Iterate and Refine:** Adjust the prompt based on the evaluation.
5.  **3D Conversion:** Utilize TRELLIS to generate 3D models.

## The Benefits

- **Efficient 3D Workflow:** Streamlines 3D model creation from AI-generated art.
- **User-Friendly Interface:** Easy Diffusion simplifies AI art generation.
- **Reduced Manual Intervention:** Minimizes 3D modeling cleanup.
- **Faster Iteration:** Accelerates character design exploration in 3D.
- **Standardized Output:** Maintains consistency in character presentation.
- **Accessibility:** Empowers users with varying artistic skills to contribute.

## The Downsides

- **FLUX.1 Style:** Inherits the distinctive style of the FLUX.1 model.
- **TRELLIS Limitations:** Complex elements may still require manual 3D refinement.
- **WSL2 Setup:** Requires users to install and configure WSL2.

## The Road Not Taken

- **Manual creation of concept art:** Offers greater control but is time-consuming.
- **Using alternative AI models:** Other models may not be as compatible with TRELLIS or as user-friendly.
- **Native Windows TRELLIS:** Not readily available, requiring WSL2 for now.

## The Infrequent Use Case

For highly specific or complex concept art, manual creation or a combination of AI generation and human artistry may be necessary. Users without dedicated GPUs might experience limitations with TRELLIS.

## Why is it in Core and done by us?

This aligns with V-Sekai's goal of democratizing virtual world creation by streamlining character creation and empowering users.

## Status

Status: Draft

## Decision Makers

- V-Sekai development team
- fire

## Tags

- V-Sekai
- AI Art Generation
- Character Design
- FLUX.1
- TRELLIS
- Easy Diffusion
- 3D Modeling

## Further Reading

1.  [V-Sekai · GitHub](https://github.com/v-sekai)
2.  [V-Sekai/v-sekai-game](https://github.com/v-sekai/v-sekai-game)
3.  [flux.1 schnell - Civitai](https://civitai.com/models/618692?modelVersionId=699279)
4.  [TRELLIS - Hugging Face](https://huggingface.co/spaces/JeffreyXiang/TRELLIS)
5.  [Character Design Sheet Helper - Civitai](https://civitai.com/models/100435)
6.  [TOOL_logoscale - GitHub](https://github.com/V-Sekai-fire/TOOL_logoscale/tree/main?tab=readme-ov-file)
7.  [Flux Detailer V2 - Civitai](https://civitai.com/models/685874/detailer-flux)
8.  [Easy Diffusion](https://easydiffusion.github.io/)
9.  [Windows Subsystem for Linux Documentation](https://docs.microsoft.com/en-us/windows/wsl/)