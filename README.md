# NeuralTune

> A lightweight framework for pretraining, fine-tuning, evaluating, and serving Large Language Models (LLMs).

NeuralTune is a framework designed to simplify working with modern Large Language Models. It provides an efficient and flexible environment for training, adapting, and deploying transformer-based models while remaining easy to understand and customize.

Whether you're experimenting with a research project, building an AI assistant, or fine-tuning models for domain-specific tasks, NeuralTune offers an intuitive workflow with support for today's most popular open-source LLMs.

---

## ✨ Features

- 🚀 Fine-tune pretrained LLMs on custom datasets
- 📚 Pretrain language models from scratch
- 🤖 Chat with models through an interactive CLI
- 📊 Evaluate models on benchmark tasks
- ⚡ Fast inference with optimized execution
- 💾 Low-memory training with 4-bit and 8-bit quantization
- 🎯 Parameter-efficient fine-tuning using LoRA and QLoRA
- 🔥 Flash Attention support
- 🖥️ Multi-GPU training with FSDP
- 📦 Hugging Face model compatibility
- 🔧 Modular architecture for research and customization

---

# Supported Models

NeuralTune supports many popular open-source language models, including:

- Llama 3
- Llama 3.1
- Llama 3.2
- Phi-2
- Phi-3
- Phi-4
- Gemma
- Gemma 2
- CodeGemma
- Code Llama
- Qwen 2.5
- Qwen Coder
- Mistral
- Mixtral
- Falcon
- TinyLlama

Additional Hugging Face compatible models can be integrated with minimal configuration.

---

# Installation

Clone the repository

```bash
git clone https://github.com/honu5/NeuralTune.git

cd NeuralTune
```

Install dependencies

```bash
pip install -r requirements.txt
```

or install the package

```bash
pip install neuraltune
```

---

# Quick Start

Load a pretrained model

```python
from neuraltune import LLM

llm = LLM.load("microsoft/phi-2")

response = llm.generate(
    "Explain machine learning in simple terms."
)

print(response)
```

---

# Workflows

NeuralTune provides a unified command-line interface for common LLM workflows.

## Chat

```bash
neuraltune chat microsoft/phi-2
```

---

## Fine-tune

Fine-tune a pretrained model using your own dataset.

```bash
neuraltune finetune microsoft/phi-2 \
    --data JSON \
    --data.json_path dataset.json \
    --out_dir output/model
```

---

## Pretrain

Train a language model from scratch.

```bash
neuraltune pretrain meta-llama/Llama-3.2-1B \
    --data TextFiles \
    --data.train_data_path ./dataset \
    --out_dir output/pretrained
```

---

## Evaluate

Evaluate model performance on benchmark datasets.

```bash
neuraltune evaluate microsoft/phi-2 \
    --tasks truthfulqa,mmlu
```

---

## Serve

Launch a local inference server.

```bash
neuraltune serve output/model
```

After launching the server:

```python
import requests

response = requests.post(
    "http://localhost:8000/predict",
    json={
        "prompt":"Tell me a joke."
    }
)

print(response.json())
```

---

# Fine-Tuning

NeuralTune supports several parameter-efficient fine-tuning techniques.

- LoRA
- QLoRA
- Adapters
- Full Fine-tuning

Example

```bash
neuraltune finetune meta-llama/Llama-3.2-3B \
    --strategy qlora \
    --epochs 3 \
    --batch_size 4
```

---

# Quantization

Reduce GPU memory requirements using:

- FP16
- BF16
- FP8
- INT8
- 4-bit Quantization

These methods allow larger models to run on consumer GPUs while maintaining strong performance.

---

# Performance Optimizations

NeuralTune includes support for modern optimization techniques:

- Flash Attention
- Fully Sharded Data Parallel (FSDP)
- Mixed Precision Training
- Gradient Checkpointing
- CUDA Acceleration
- Multi-GPU Training

---

# Project Structure

```
NeuralTune/

├── configs/
├── datasets/
├── examples/
├── models/
├── scripts/
├── tutorials/
├── neuraltune/
├── tests/
├── requirements.txt
└── README.md
```

---

# Example Projects

NeuralTune can be used for:

- Chatbots
- Question Answering
- Code Generation
- Text Summarization
- Document Search
- AI Assistants
- Translation
- Sentiment Analysis
- Instruction Tuning
- Domain-Specific Language Models

---

# Requirements

- Python 3.10+
- PyTorch
- CUDA 12+
- Transformers
- Datasets
- Hugging Face Hub
- Flash Attention (optional)

# Roadmap

- [x] LLM inference
- [x] Fine-tuning
- [x] Quantization
- [x] LoRA / QLoRA
- [x] Model evaluation
- [ ] Distributed inference
- [ ] Web interface
- [ ] REST API improvements
- [ ] Additional model support

---

# License

This project is released under the Apache 2.0 License.

See the LICENSE file for more information.

---

## Acknowledgements

NeuralTune builds upon the open-source AI ecosystem, including:

- PyTorch
- Hugging Face
- Transformers
- Lightning Fabric
- Flash Attention
- bitsandbytes


---

## Repository

```text
https://github.com/honu5/NeuralTune
```
