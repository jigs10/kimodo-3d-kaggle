# Kimodo 3D Human Motion Generation on Kaggle

Generate human motion from text prompts using NVIDIA's Kimodo and visualize the result with Soma Viser.

## What This Notebook Does

1. Configures temporary storage and Hugging Face caches.
2. Clones the Kimodo repository.
3. Installs build and Python dependencies.
4. Installs Kimodo in editable mode.
5. Authenticates with Hugging Face.
6. Verifies PyTorch, CUDA, and GPU availability.
7. Generates a human motion sequence from a text prompt.
8. Converts the generated NPZ file to BVH.

## Requirements

- A Kaggle notebook with internet access enabled.
- A GPU runtime, such as a T4.
- A Hugging Face account.
- Access accepted for `meta-llama/Meta-Llama-3-8B-Instruct`.
- A Hugging Face access when prompted by `huggingface_hub.login()`.

## Generated Motion

The default prompt is:

> A person doing frontflip.

The generated files are saved in:

```text
/kaggle/working/kimodo_outputs/
```

The default output files are:

```text
frontflip.npz
frontflip.bvh
```

To generate a different motion, update the prompt and output name in the generation cell. If you change the generated filename, update the input and output paths in the conversion and copy cells as well.

## Viewing the Motion

The generated BVH file can be downloaded from Kaggle and opened in a desktop BVH viewer such as Blender or BVHView.

## Notes

- Model downloads and caches are stored under `/tmp/kimodo_runtime/`.
- Final generated outputs are stored under `/kaggle/working/kimodo_outputs/`.
- The text encoder is configured to run on the CPU to reduce GPU memory usage.
- GPU `0` is reserved for Kimodo through `CUDA_VISIBLE_DEVICES=0`.
