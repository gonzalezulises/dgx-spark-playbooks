
<p align="center">
  <img src="src/images/dgx-spark-banner.png" alt="NVIDIA DGX Spark"/>
</p>

# DGX Spark Playbooks

Collection of step-by-step playbooks for setting up AI/ML workloads on NVIDIA DGX Spark devices with Blackwell architecture.

> **Fork Note**: This is a fork of NVIDIA's official DGX Spark playbooks repository. See custom documentation below for learning paths and integration with Cerebro DS RAG system.

## About

These playbooks provide detailed instructions for:
- Installing and configuring popular AI frameworks
- Running inference with optimized models
- Setting up development environments
- Connecting and managing your DGX Spark device

Each playbook includes prerequisites, step-by-step instructions, troubleshooting guidance, and example code.

## 📚 Custom Documentation

| Document | Description |
|----------|-------------|
| [🎯 Learning Path](docs/LEARNING-PATH.md) | **Optimal learning order for all 33 playbooks** - 6 progressive levels, specialization tracks, time estimates |
| [📋 Mi Plan de Aprendizaje](docs/MI-PLAN-APRENDIZAJE.md) | **Personal progress tracker** - Dashboard, checkpoints, weekly goals, learning diary |
| [📊 Cerebro DS Analysis](docs/CEREBRO-DS-ANALYSIS.md) | Comparison of NVIDIA RAG vs Cerebro DS, compatibility analysis, architectural decisions |

## 🗺️ Learning Path Overview

```
NIVEL 6: Multi-Node        ← Connect Two Sparks, NCCL, Distributed
    ↑
NIVEL 5: Especialización   ← Isaac, FLUX, Multi-modal, Data Science
    ↑
NIVEL 4: Fine-Tuning       ← NeMo, Unsloth, LLaMA Factory
    ↑
NIVEL 3: RAG & Agentes     ← RAG Workbench, txt2kg, Multi-Agent
    ↑
NIVEL 2: Inferencia        ← Ollama, vLLM, TRT-LLM, NIM, SGLang
    ↑
NIVEL 1: Fundamentos       ← Setup, Dashboard, VS Code, Tailscale
```

**Duración Total**: 40-50 horas | **Tracks**: RAG, MLOps, Creative, Data Science, Robotics

👉 [Ver plan completo](docs/LEARNING-PATH.md) | 📋 [Seguimiento personal](docs/MI-PLAN-APRENDIZAJE.md)

## Playbook Compatibility (Single DGX Spark)

| Status | Count | Description |
|--------|-------|-------------|
| ✅ | 30 | Executable with single DGX Spark |
| ⚠️ | 12 | Require API keys/tokens |
| ❌ | 3 | Require 2+ DGX Sparks |

See [full compatibility analysis](docs/CEREBRO-DS-ANALYSIS.md#análisis-de-compatibilidad-33-playbooks) for details.

## Available Playbooks

### NVIDIA

#### Level 1: Fundamentals
- [Set Up Local Network Access](nvidia/connect-to-your-spark/)
- [DGX Dashboard](nvidia/dgx-dashboard/)
- [VS Code](nvidia/vscode/)
- [Set up Tailscale on Your Spark](nvidia/tailscale/)
- [Vibe Coding in VS Code](nvidia/vibe-coding/)

#### Level 2: Inference
- [Ollama](nvidia/ollama/) ⭐ *Start here*
- [Open WebUI with Ollama](nvidia/open-webui/)
- [vLLM for Inference](nvidia/vllm/)
- [TRT LLM for Inference](nvidia/trt-llm/) ⚠️ *Requires NGC API Key*
- [NIM on Spark](nvidia/nim-llm/) ⚠️ *Requires NGC API Key*
- [SGLang for Inference](nvidia/sglang/) ⚠️ *Requires HF Token*
- [Nemotron-3-Nano with llama.cpp](nvidia/nemotron/)
- [Speculative Decoding](nvidia/speculative-decoding/)
- [NVFP4 Quantization](nvidia/nvfp4-quantization/)

#### Level 3: RAG & Agents
- [RAG Application in AI Workbench](nvidia/rag-ai-workbench/) ⚠️ *Requires NGC + Tavily Keys*
- [Text to Knowledge Graph](nvidia/txt2kg/) ⚠️ *Requires API Keys*
- [Build and Deploy a Multi-Agent Chatbot](nvidia/multi-agent-chatbot/) ⚠️ *Requires API Keys*

#### Level 4: Fine-Tuning
- [Fine-tune with Pytorch](nvidia/pytorch-fine-tune/) ⚠️ *Requires HF Token*
- [Unsloth on DGX Spark](nvidia/unsloth/) ⚠️ *Requires HF Token*
- [LLaMA Factory](nvidia/llama-factory/) ⚠️ *Requires HF Token*
- [Fine-tune with NeMo](nvidia/nemo-fine-tune/) ⚠️ *Requires HF Token*

#### Level 5: Specialization

**Track A - Image Generation:**
- [Comfy UI](nvidia/comfy-ui/)
- [FLUX.1 Dreambooth LoRA Fine-tuning](nvidia/flux-finetuning/) ⚠️ *Requires HF Token*

**Track B - Multi-modal:**
- [Multi-modal Inference](nvidia/multi-modal-inference/)
- [Live VLM WebUI](nvidia/live-vlm-webui/)
- [Build a Video Search and Summarization (VSS) Agent](nvidia/vss/)

**Track C - Robotics:**
- [Install and Use Isaac Sim and Isaac Lab](nvidia/isaac/)

**Track D - Data Science:**
- [CUDA-X Data Science](nvidia/cuda-x-data-science/)
- [Portfolio Optimization](nvidia/portfolio-optimization/)
- [Single-cell RNA Sequencing](nvidia/single-cell/)

**Track E - Optimization:**
- [Optimized JAX](nvidia/jax/)

#### Level 6: Multi-Node
- [Connect Two Sparks](nvidia/connect-two-sparks/) ❌ *Requires 2 Sparks*
- [NCCL for Two Sparks](nvidia/nccl/) ❌ *Requires 2 Sparks*

## Required API Keys

| Key | URL | Used By |
|-----|-----|---------|
| NGC API Key | [ngc.nvidia.com/setup/api-key](https://ngc.nvidia.com/setup/api-key) | NIM, TRT-LLM, RAG Workbench |
| HuggingFace Token | [huggingface.co/settings/tokens](https://huggingface.co/settings/tokens) | Fine-tuning playbooks |
| Tavily API Key | [tavily.com](https://tavily.com/) | RAG AI Workbench |

## Resources

- **Documentation**: https://www.nvidia.com/en-us/products/workstations/dgx-spark/
- **Developer Forum**: https://forums.developer.nvidia.com/c/accelerated-computing/dgx-spark-gb10
- **Terms of Service**: https://assets.ngc.nvidia.com/products/api-catalog/legal/NVIDIA%20API%20Trial%20Terms%20of%20Service.pdf

## Related Projects

- [Cerebro DS](https://github.com/gonzalezulises/cerebro-ds) - Data Science RAG system built on DGX Spark

## License

See:
- [LICENSE](LICENSE) for licensing information.
- [LICENSE-3rd-party](LICENSE-3rd-party) for third-party licensing information.
