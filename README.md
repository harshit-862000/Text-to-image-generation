## Image Generation Parameters

This section describes how the image generation process is configured using parameter settings.

### Parameter Configuration

A configuration dictionary is created to control how the diffusion model generates images. One important parameter used is **num_inference_steps**.

**num_inference_steps** determines how many denoising iterations the diffusion model performs while generating an image.

Diffusion models begin with random noise and gradually refine it into a meaningful image. During each step, a small amount of noise is removed until a final image is produced.

Increasing the number of inference steps usually improves image quality because the model has more opportunities to refine the image. However, it also increases the time required to generate the image.

Typical ranges used in diffusion models:

| Inference Steps | Result |
|----------------|--------|
| 20–30 | Faster generation but lower quality |
| 50 | Balanced speed and quality |
| 100+ | Higher quality images but slower generation |

### Image Generation Workflow

After defining the parameters, the image generation function is executed.

The function takes three inputs:

- **Pipeline (pipe)** – The diffusion model pipeline responsible for running the image generation process.
- **Prompt** – A text description that guides the model to generate the desired image.
- **Parameters** – Configuration settings that control how the generation process runs.

The function passes the prompt and parameters to the diffusion pipeline. The model then performs the denoising process over the specified number of inference steps and produces the final generated image.

This parameter-driven approach makes the system flexible, allowing image generation settings to be adjusted easily without modifying the core implementation.
