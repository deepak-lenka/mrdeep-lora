---
license: other
license_name: flux-1-dev-non-commercial-license
license_link: https://huggingface.co/black-forest-labs/FLUX.1-dev/blob/main/LICENSE.md
---

# FLUX Training Project

This project is designed to train a FLUX model using the LoRA (Low-Rank Adaptation) technique. It utilizes the FLUX.1-dev model from Black Forest Labs and is configured for fine-tuning on custom datasets.

## Project Configuration

The project uses a configuration file (`config.yaml`) to define the training process. Here are the key details:

### Model
- Base model: black-forest-labs/FLUX.1-dev
- Quantization: Enabled
- FLUX model: Yes

### Network
- Type: LoRA (Low-Rank Adaptation)
- Linear dimensions: 16
- Linear alpha: 16

### Dataset
- Input folder: `input_images`
- Caption extension: .txt
- Resolution: 512, 768, 1024
- Cache latents to disk: Enabled
- Caption dropout rate: 5%

### Training
- Batch size: 1
- Learning rate: 0.0004
- Steps: 1000
- Optimizer: AdamW (8-bit)
- Dtype: bfloat16
- Gradient checkpointing: Enabled
- Text encoder training: Disabled
- U-Net training: Enabled

### Sampling
- Guidance scale: 4
- Dimensions: 1024x1024
- Sampler: FlowMatch
- Steps: 20
- Sample frequency: Every 250 steps

### Miscellaneous
- Trigger word: TOK
- Output folder: `output`

## License

This project uses the FLUX.1-dev model, which is subject to the FLUX-1-dev-non-commercial-license. Please refer to the [license file](https://huggingface.co/black-forest-labs/FLUX.1-dev/blob/main/LICENSE.md) for more details.

## Usage

1. Prepare your dataset in the `input_images` folder with corresponding `.txt` caption files.
2. Ensure you have the required dependencies installed (FLUX, PyTorch, etc.).
3. Run the training script (not provided in the given configuration) with the `config.yaml` file.

## Notes

- The project is configured to use CUDA for GPU acceleration.
- EMA (Exponential Moving Average) is enabled with a decay of 0.99.
- The training process will save checkpoints every 1001 steps, keeping only the most recent save.

## Disclaimer

This README is based on the provided configuration file. Ensure all necessary components and scripts are in place before running the training process.
