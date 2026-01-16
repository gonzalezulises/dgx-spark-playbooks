
<p align="center">
  <img src="src/images/dgx-spark-banner.png" alt="NVIDIA DGX Spark"/>
</p>

# DGX Spark Playbooks

Collection of step-by-step playbooks for setting up AI/ML workloads on NVIDIA DGX Spark devices with Blackwell architecture.

> **Fork Note**: This is a fork of NVIDIA's official DGX Spark playbooks repository. See [Cerebro DS Analysis](docs/CEREBRO-DS-ANALYSIS.md) for custom documentation and integration notes with the Cerebro DS RAG system.

## About

These playbooks provide detailed instructions for:
- Installing and configuring popular AI frameworks
- Running inference with optimized models
- Setting up development environments
- Connecting and managing your DGX Spark device

Each playbook includes prerequisites, step-by-step instructions, troubleshooting guidance, and example code.

## Custom Documentation

| Document | Description |
|----------|-------------|
| [Cerebro DS Analysis](docs/CEREBRO-DS-ANALYSIS.md) | Comparison of NVIDIA RAG vs Cerebro DS, playbook compatibility analysis, and architectural decisions |

## Playbook Compatibility (Single DGX Spark)

| Status | Count | Description |
|--------|-------|-------------|
| ✅ | 30 | Executable with single DGX Spark |
| ⚠️ | 12 | Require API keys/tokens |
| ❌ | 3 | Require 2+ DGX Sparks |

See [full compatibility analysis](docs/CEREBRO-DS-ANALYSIS.md#análisis-de-compatibilidad-33-playbooks) for details.

## Available Playbooks

### NVIDIA

- [Comfy UI](nvidia/comfy-ui/)
- [Set Up Local Network Access](nvidia/connect-to-your-spark/)
- [Connect Two Sparks](nvidia/connect-two-sparks/) ❌ *Requires 2 Sparks*
- [CUDA-X Data Science](nvidia/cuda-x-data-science/)
- [DGX Dashboard](nvidia/dgx-dashboard/)
- [FLUX.1 Dreambooth LoRA Fine-tuning](nvidia/flux-finetuning/) ⚠️ *Requires HF Token*
- [Install and Use Isaac Sim and Isaac Lab](nvidia/isaac/)
- [Optimized JAX](nvidia/jax/)
- [Live VLM WebUI](nvidia/live-vlm-webui/)
- [LLaMA Factory](nvidia/llama-factory/) ⚠️ *Requires HF Token*
- [Build and Deploy a Multi-Agent Chatbot](nvidia/multi-agent-chatbot/) ⚠️ *Requires API Keys*
- [Multi-modal Inference](nvidia/multi-modal-inference/)
- [NCCL for Two Sparks](nvidia/nccl/) ❌ *Requires 2 Sparks*
- [Fine-tune with NeMo](nvidia/nemo-fine-tune/) ⚠️ *Requires HF Token*
- [Nemotron-3-Nano with llama.cpp](nvidia/nemotron/)
- [NIM on Spark](nvidia/nim-llm/) ⚠️ *Requires NGC API Key*
- [NVFP4 Quantization](nvidia/nvfp4-quantization/)
- [Ollama](nvidia/ollama/)
- [Open WebUI with Ollama](nvidia/open-webui/)
- [Portfolio Optimization](nvidia/portfolio-optimization/)
- [Fine-tune with Pytorch](nvidia/pytorch-fine-tune/) ⚠️ *Requires HF Token*
- [RAG Application in AI Workbench](nvidia/rag-ai-workbench/) ⚠️ *Requires NGC + Tavily Keys*
- [SGLang for Inference](nvidia/sglang/) ⚠️ *Requires HF Token*
- [Single-cell RNA Sequencing](nvidia/single-cell/)
- [Speculative Decoding](nvidia/speculative-decoding/)
- [Set up Tailscale on Your Spark](nvidia/tailscale/)
- [TRT LLM for Inference](nvidia/trt-llm/) ⚠️ *Requires NGC API Key*
- [Text to Knowledge Graph](nvidia/txt2kg/) ⚠️ *Requires API Keys*
- [Unsloth on DGX Spark](nvidia/unsloth/) ⚠️ *Requires HF Token*
- [Vibe Coding in VS Code](nvidia/vibe-coding/)
- [vLLM for Inference](nvidia/vllm/)
- [VS Code](nvidia/vscode/)
- [Build a Video Search and Summarization (VSS) Agent](nvidia/vss/)

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
