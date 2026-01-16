# Plan de Aprendizaje: DGX Spark Playbooks

> Ruta de aprendizaje óptima para dominar los 33 laboratorios de DGX Spark
> 
> **Autor**: Ulises González - Rizo.ma  
> **Fecha**: 2026-01-16  
> **Duración Total Estimada**: 40-50 horas

---

## Filosofía del Plan

Este plan está diseñado siguiendo principios pedagógicos:

1. **Fundamentos Primero**: Dominar la infraestructura antes de las aplicaciones
2. **Complejidad Progresiva**: De lo simple a lo complejo
3. **Dependencias Respetadas**: Cada lab prepara para el siguiente
4. **Práctica Inmediata**: Cada concepto se aplica antes de avanzar
5. **Consolidación**: Labs relacionados se agrupan para reforzar aprendizaje

---

## Mapa Visual del Curriculum

```
                            ┌─────────────────────────────────────────┐
                            │         NIVEL 6: MULTI-NODE             │
                            │    Connect Two Sparks → NCCL → Dist     │
                            └─────────────────────────────────────────┘
                                              ▲
                            ┌─────────────────────────────────────────┐
                            │      NIVEL 5: ESPECIALIZACIÓN           │
                            │  Isaac Sim │ Diffusion │ Bioinformtic  │
                            └─────────────────────────────────────────┘
                                              ▲
                            ┌─────────────────────────────────────────┐
                            │        NIVEL 4: FINE-TUNING             │
                            │  NeMo → Unsloth → LLaMA Factory → FLUX  │
                            └─────────────────────────────────────────┘
                                              ▲
                            ┌─────────────────────────────────────────┐
                            │      NIVEL 3: RAG & AGENTES             │
                            │   RAG Workbench → txt2kg → Multi-Agent  │
                            └─────────────────────────────────────────┘
                                              ▲
                            ┌─────────────────────────────────────────┐
                            │       NIVEL 2: INFERENCIA               │
                            │  Ollama → vLLM → TRT-LLM → NIM → SGLang │
                            └─────────────────────────────────────────┘
                                              ▲
                            ┌─────────────────────────────────────────┐
                            │       NIVEL 1: FUNDAMENTOS              │
                            │  Setup → Dashboard → VS Code → Tailscale│
                            └─────────────────────────────────────────┘
```

---

## NIVEL 1: Fundamentos de Infraestructura
> **Objetivo**: Dominar el acceso, monitoreo y desarrollo remoto en DGX Spark  
> **Duración**: 3-4 horas  
> **Prerequisitos**: Ninguno

### Lab 1.1: Connect to Your Spark
| Aspecto | Detalle |
|---------|---------|
| **Tiempo** | 30 min |
| **Objetivo** | Configurar acceso de red local al DGX Spark |
| **Aprenderás** | Networking básico, SSH, configuración IP |
| **Entregable** | Acceso SSH funcional desde tu máquina local |

```bash
# Verificación de éxito
ssh usuario@dgx-spark.local
nvidia-smi  # Debe mostrar la GPU
```

### Lab 1.2: DGX Dashboard
| Aspecto | Detalle |
|---------|---------|
| **Tiempo** | 30 min |
| **Objetivo** | Monitorear recursos del sistema en tiempo real |
| **Aprenderás** | Métricas GPU/CPU/RAM, utilización, temperatura |
| **Entregable** | Dashboard accesible vía web browser |

**Por qué es importante**: Necesitas monitorear recursos antes de ejecutar cargas pesadas.

### Lab 1.3: VS Code Remote
| Aspecto | Detalle |
|---------|---------|
| **Tiempo** | 30 min |
| **Objetivo** | Desarrollo remoto con VS Code |
| **Aprenderás** | Remote-SSH extension, workspace remoto |
| **Entregable** | VS Code conectado al DGX Spark |

**Por qué es importante**: Ambiente de desarrollo cómodo para el resto de los labs.

### Lab 1.4: Tailscale VPN
| Aspecto | Detalle |
|---------|---------|
| **Tiempo** | 30 min |
| **Objetivo** | Acceso remoto seguro desde cualquier lugar |
| **Aprenderás** | VPN mesh, configuración Tailscale |
| **Entregable** | Acceso al DGX desde fuera de la red local |

**Por qué es importante**: Flexibilidad para trabajar desde cualquier ubicación.

### Lab 1.5: Vibe Coding
| Aspecto | Detalle |
|---------|---------|
| **Tiempo** | 30 min |
| **Objetivo** | Coding asistido por AI en VS Code |
| **Aprenderás** | GitHub Copilot / AI assistants en VS Code |
| **Entregable** | AI coding assistant funcional |

### 📊 Checkpoint Nivel 1
```
□ Puedo acceder al DGX via SSH
□ Puedo monitorear GPU/CPU/RAM en dashboard
□ Tengo VS Code conectado remotamente
□ Puedo acceder desde fuera de mi red (Tailscale)
□ Tengo AI coding assistant configurado
```

---

## NIVEL 2: Inferencia de Modelos
> **Objetivo**: Dominar diferentes backends de inferencia LLM  
> **Duración**: 6-8 horas  
> **Prerequisitos**: Nivel 1 completado

### Lab 2.1: Ollama ⭐ (Punto de Partida)
| Aspecto | Detalle |
|---------|---------|
| **Tiempo** | 30 min |
| **Objetivo** | Inferencia LLM simple y rápida |
| **Aprenderás** | Gestión de modelos, API REST, streaming |
| **Entregable** | Ollama sirviendo modelos localmente |

```bash
# Verificación de éxito
ollama run llama3.2
curl http://localhost:11434/api/generate -d '{"model":"llama3.2","prompt":"Hello"}'
```

**Por qué primero**: Es el más simple y sirve como baseline de comparación.

### Lab 2.2: Open WebUI
| Aspecto | Detalle |
|---------|---------|
| **Tiempo** | 30 min |
| **Objetivo** | UI web completa para Ollama |
| **Aprenderás** | Docker, UI chat, gestión de conversaciones |
| **Entregable** | ChatGPT-like interface para tus modelos |

**Dependencia**: Requiere Lab 2.1 (Ollama)

### Lab 2.3: vLLM
| Aspecto | Detalle |
|---------|---------|
| **Tiempo** | 45 min |
| **Objetivo** | Inferencia de alto throughput |
| **Aprenderás** | PagedAttention, batching, OpenAI-compatible API |
| **Entregable** | vLLM sirviendo con mejor throughput que Ollama |

**Comparación con Ollama**:
| Métrica | Ollama | vLLM |
|---------|--------|------|
| Setup | ⭐⭐⭐⭐⭐ | ⭐⭐⭐ |
| Throughput | ⭐⭐⭐ | ⭐⭐⭐⭐⭐ |
| Memoria | ⭐⭐⭐ | ⭐⭐⭐⭐ |

### Lab 2.4: TensorRT-LLM ⚠️
| Aspecto | Detalle |
|---------|---------|
| **Tiempo** | 60 min |
| **Requisito** | NGC API Key |
| **Objetivo** | Inferencia optimizada con TensorRT |
| **Aprenderás** | Compilación de modelos, optimización GPU |
| **Entregable** | Modelo compilado con TRT corriendo |

**Por qué después de vLLM**: TRT-LLM requiere compilación previa, más complejo.

### Lab 2.5: NIM on Spark ⚠️
| Aspecto | Detalle |
|---------|---------|
| **Tiempo** | 45 min |
| **Requisito** | NGC API Key |
| **Objetivo** | NVIDIA Inference Microservices |
| **Aprenderás** | Contenedores NIM, deployment enterprise |
| **Entregable** | NIM container sirviendo Llama 3.1 8B |

### Lab 2.6: SGLang ⚠️
| Aspecto | Detalle |
|---------|---------|
| **Tiempo** | 45 min |
| **Requisito** | HuggingFace Token |
| **Objetivo** | Structured Generation Language |
| **Aprenderás** | Generación estructurada, JSON schemas |
| **Entregable** | SGLang sirviendo con outputs estructurados |

### Lab 2.7: Nemotron
| Aspecto | Detalle |
|---------|---------|
| **Tiempo** | 30 min |
| **Objetivo** | Modelo NVIDIA optimizado con llama.cpp |
| **Aprenderás** | llama.cpp, modelos GGUF |
| **Entregable** | Nemotron-3-Nano corriendo localmente |

### Lab 2.8: Speculative Decoding
| Aspecto | Detalle |
|---------|---------|
| **Tiempo** | 45 min |
| **Objetivo** | Acelerar inferencia con draft models |
| **Aprenderás** | Draft/target model pattern, speedup |
| **Entregable** | Inferencia 2-3x más rápida |

### Lab 2.9: NVFP4 Quantization
| Aspecto | Detalle |
|---------|---------|
| **Tiempo** | 45 min |
| **Objetivo** | Cuantización a 4-bit con NVIDIA |
| **Aprenderás** | Quantization, trade-offs calidad/velocidad |
| **Entregable** | Modelo cuantizado corriendo eficientemente |

### 📊 Checkpoint Nivel 2
```
□ Entiendo las diferencias entre backends de inferencia
□ Puedo elegir el backend correcto según el caso de uso
□ Sé cuándo usar Ollama vs vLLM vs TRT-LLM
□ Puedo optimizar inferencia con quantization
□ Entiendo speculative decoding
```

### Tabla Comparativa (Resultado del Nivel 2)

| Backend | Setup | Throughput | Latencia | Memoria | Caso de Uso |
|---------|-------|------------|----------|---------|-------------|
| Ollama | ⭐⭐⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐ | Desarrollo, prototipado |
| vLLM | ⭐⭐⭐ | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | Producción, alto tráfico |
| TRT-LLM | ⭐⭐ | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐⭐ | Máximo rendimiento |
| NIM | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | Enterprise, soporte NVIDIA |
| SGLang | ⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐ | Outputs estructurados |

---

## NIVEL 3: RAG y Sistemas Agentic
> **Objetivo**: Construir sistemas RAG y agentes inteligentes  
> **Duración**: 6-8 horas  
> **Prerequisitos**: Nivel 2 completado (al menos Ollama + vLLM)

### Lab 3.1: RAG Application in AI Workbench ⚠️
| Aspecto | Detalle |
|---------|---------|
| **Tiempo** | 60 min |
| **Requisito** | NGC + Tavily API Keys |
| **Objetivo** | Entender RAG agentic de NVIDIA |
| **Aprenderás** | Route-Evaluate-Iterate pattern, web search |
| **Entregable** | RAG funcional con AI Workbench |

**Conceptos clave a dominar**:
```
┌─────────────────────────────────────────────────┐
│                 AGENTIC RAG FLOW                │
├─────────────────────────────────────────────────┤
│  Query → Router → [RAG | Web Search] → LLM     │
│                         ↓                       │
│              Evaluator (hallucination check)    │
│                         ↓                       │
│              [Pass → Response | Fail → Retry]   │
└─────────────────────────────────────────────────┘
```

### Lab 3.2: Text to Knowledge Graph ⚠️
| Aspecto | Detalle |
|---------|---------|
| **Tiempo** | 60 min |
| **Requisito** | API Keys varios |
| **Objetivo** | Construir knowledge graphs desde texto |
| **Aprenderás** | Entity extraction, relationship mapping, Neo4j |
| **Entregable** | Knowledge graph navegable |

**Por qué es importante**: Habilita hybrid retrieval (vector + graph) para Cerebro DS.

### Lab 3.3: Multi-Agent Chatbot ⚠️
| Aspecto | Detalle |
|---------|---------|
| **Tiempo** | 90 min |
| **Requisito** | NGC/OpenAI Keys |
| **Objetivo** | Sistema multi-agente completo |
| **Aprenderás** | Agent orchestration, tool use, memory |
| **Entregable** | Chatbot con múltiples agentes especializados |

**Arquitectura Multi-Agente**:
```
┌──────────────────────────────────────────────────┐
│                 ORCHESTRATOR                      │
├──────────────────────────────────────────────────┤
│  ┌─────────┐  ┌─────────┐  ┌─────────┐          │
│  │ Agent 1 │  │ Agent 2 │  │ Agent 3 │          │
│  │ Search  │  │ Code    │  │ Data    │          │
│  └────┬────┘  └────┬────┘  └────┬────┘          │
│       │            │            │                │
│       └────────────┴────────────┘                │
│                    ↓                             │
│              Shared Memory                       │
└──────────────────────────────────────────────────┘
```

### 📊 Checkpoint Nivel 3
```
□ Entiendo el patrón Route-Evaluate-Iterate
□ Puedo construir knowledge graphs desde documentos
□ Sé orquestar múltiples agentes
□ Entiendo cuándo usar RAG vs Knowledge Graph vs Hybrid
□ Puedo implementar detección de alucinaciones
```

---

## NIVEL 4: Fine-Tuning de Modelos
> **Objetivo**: Personalizar modelos para casos de uso específicos  
> **Duración**: 8-10 horas  
> **Prerequisitos**: Nivel 2 completado, HuggingFace Token

### Lab 4.1: Fine-tune with PyTorch ⚠️
| Aspecto | Detalle |
|---------|---------|
| **Tiempo** | 90 min |
| **Requisito** | HuggingFace Token |
| **Objetivo** | Fine-tuning básico con PyTorch nativo |
| **Aprenderás** | Training loop, datasets, checkpointing |
| **Entregable** | Modelo fine-tuned con PyTorch |

**Por qué primero**: Entender los fundamentos antes de usar frameworks.

### Lab 4.2: Unsloth ⚠️
| Aspecto | Detalle |
|---------|---------|
| **Tiempo** | 60 min |
| **Requisito** | HuggingFace Token |
| **Objetivo** | Fine-tuning 2x más rápido con menos memoria |
| **Aprenderás** | Unsloth optimizations, LoRA eficiente |
| **Entregable** | Fine-tuning rápido y eficiente |

### Lab 4.3: LLaMA Factory ⚠️
| Aspecto | Detalle |
|---------|---------|
| **Tiempo** | 90 min |
| **Requisito** | HuggingFace Token |
| **Objetivo** | Fine-tuning con UI y múltiples métodos |
| **Aprenderás** | LoRA, QLoRA, full fine-tuning, DPO, RLHF |
| **Entregable** | Modelo entrenado con LLaMA Factory |

**Métodos de Fine-Tuning**:
```
┌─────────────────────────────────────────────────────┐
│              FINE-TUNING METHODS                    │
├─────────────────────────────────────────────────────┤
│  Full Fine-tuning    │ Actualiza todos los params  │
│  LoRA                │ Low-Rank Adaptation         │
│  QLoRA               │ LoRA + Quantization         │
│  DPO                 │ Direct Preference Opt       │
│  RLHF                │ Reinforcement Learning HF   │
└─────────────────────────────────────────────────────┘
```

### Lab 4.4: Fine-tune with NeMo ⚠️
| Aspecto | Detalle |
|---------|---------|
| **Tiempo** | 120 min |
| **Requisito** | HuggingFace Token |
| **Objetivo** | Fine-tuning enterprise con NeMo AutoModel |
| **Aprenderás** | NeMo framework, recipes, distributed training |
| **Entregable** | Modelo fine-tuned con NeMo |

**Modelos soportados por lab**:

| Lab | Modelos | Tamaño Máximo |
|-----|---------|---------------|
| PyTorch | Cualquiera | ~8B (memoria) |
| Unsloth | Llama, Mistral | ~70B (QLoRA) |
| LLaMA Factory | 100+ modelos | ~70B |
| NeMo | Llama, Qwen, etc. | ~70B |

### 📊 Checkpoint Nivel 4
```
□ Entiendo la diferencia entre LoRA, QLoRA, full fine-tuning
□ Puedo elegir el método correcto según recursos/objetivo
□ Sé preparar datasets para fine-tuning
□ Puedo evaluar modelos fine-tuned
□ Entiendo trade-offs de cada framework
```

---

## NIVEL 5: Aplicaciones Especializadas
> **Objetivo**: Dominar casos de uso avanzados y específicos  
> **Duración**: 10-12 horas  
> **Prerequisitos**: Niveles 1-3 completados

### Track A: Generación de Imágenes

#### Lab 5A.1: Comfy UI
| Aspecto | Detalle |
|---------|---------|
| **Tiempo** | 45 min |
| **Objetivo** | UI node-based para generación de imágenes |
| **Aprenderás** | Workflows visuales, pipelines de difusión |
| **Entregable** | Comfy UI funcional con workflows |

#### Lab 5A.2: FLUX.1 Dreambooth LoRA ⚠️
| Aspecto | Detalle |
|---------|---------|
| **Tiempo** | 2-3 hrs |
| **Requisito** | HuggingFace Token, acceso FLUX.1-dev |
| **Objetivo** | Fine-tuning de modelos de difusión |
| **Aprenderás** | Dreambooth, LoRA para imágenes, multi-concept |
| **Entregable** | Modelo FLUX personalizado |

### Track B: Multi-Modal

#### Lab 5B.1: Multi-modal Inference
| Aspecto | Detalle |
|---------|---------|
| **Tiempo** | 60 min |
| **Objetivo** | Inferencia con modelos vision-language |
| **Aprenderás** | VLMs, image understanding, visual QA |
| **Entregable** | Modelo multi-modal sirviendo |

#### Lab 5B.2: Live VLM WebUI
| Aspecto | Detalle |
|---------|---------|
| **Tiempo** | 60 min |
| **Objetivo** | UI para modelos vision-language en tiempo real |
| **Aprenderás** | Streaming video, real-time inference |
| **Entregable** | VLM procesando video/webcam en vivo |

#### Lab 5B.3: Video Search & Summarization (VSS)
| Aspecto | Detalle |
|---------|---------|
| **Tiempo** | 90 min |
| **Objetivo** | Búsqueda y resumen de video |
| **Aprenderás** | Video embeddings, temporal search |
| **Entregable** | Sistema VSS funcional |

### Track C: Robótica y Simulación

#### Lab 5C.1: Isaac Sim
| Aspecto | Detalle |
|---------|---------|
| **Tiempo** | 60 min |
| **Objetivo** | Simulación robótica fotorealista |
| **Aprenderás** | Omniverse, physics simulation |
| **Entregable** | Isaac Sim corriendo simulaciones |

#### Lab 5C.2: Isaac Lab
| Aspecto | Detalle |
|---------|---------|
| **Tiempo** | 90 min |
| **Objetivo** | RL para robótica |
| **Aprenderás** | Reinforcement learning, locomotion |
| **Entregable** | Agente RL entrenado en simulación |

### Track D: Data Science & Ciencia

#### Lab 5D.1: CUDA-X Data Science
| Aspecto | Detalle |
|---------|---------|
| **Tiempo** | 60 min |
| **Objetivo** | Data science acelerado por GPU |
| **Aprenderás** | cuDF, cuML, cuGraph, RAPIDS |
| **Entregable** | Pipeline de datos GPU-accelerated |

#### Lab 5D.2: Portfolio Optimization
| Aspecto | Detalle |
|---------|---------|
| **Tiempo** | 60 min |
| **Objetivo** | Optimización financiera con GPU |
| **Aprenderás** | Finanzas cuantitativas, optimization |
| **Entregable** | Optimizer de portfolio funcional |

#### Lab 5D.3: Single-cell RNA Sequencing
| Aspecto | Detalle |
|---------|---------|
| **Tiempo** | 90 min |
| **Objetivo** | Análisis de secuenciación celular |
| **Aprenderás** | Bioinformática, scRNA-seq analysis |
| **Entregable** | Pipeline de análisis celular |

### Track E: Optimización Avanzada

#### Lab 5E.1: Optimized JAX
| Aspecto | Detalle |
|---------|---------|
| **Tiempo** | 60 min |
| **Objetivo** | JAX optimizado para DGX Spark |
| **Aprenderás** | JAX, XLA compilation, JIT |
| **Entregable** | JAX corriendo con optimizaciones |

### 📊 Checkpoint Nivel 5
```
□ Completé al menos 2 tracks completos
□ Puedo elegir herramientas según el dominio
□ Entiendo las capacidades multi-modales
□ Sé cuándo usar GPU-acceleration para data science
```

---

## NIVEL 6: Multi-Node y Distribuido
> **Objetivo**: Escalar a múltiples DGX Sparks  
> **Duración**: 4-6 horas  
> **Prerequisitos**: Todos los niveles anteriores + 2 DGX Sparks

### Lab 6.1: Connect Two Sparks ❌
| Aspecto | Detalle |
|---------|---------|
| **Tiempo** | 60 min |
| **Requisito** | 2 DGX Spark + cable QSFP |
| **Objetivo** | Conectar dos sistemas via 200GbE |
| **Aprenderás** | Networking multi-node, SSH keys |
| **Entregable** | Dos Sparks comunicándose |

### Lab 6.2: NCCL for Two Sparks ❌
| Aspecto | Detalle |
|---------|---------|
| **Tiempo** | 60 min |
| **Requisito** | Lab 6.1 completado |
| **Objetivo** | Comunicación GPU-GPU entre nodos |
| **Aprenderás** | NCCL, MPI, collective operations |
| **Entregable** | NCCL tests pasando entre nodos |

### Lab 6.3: Distributed Training
| Aspecto | Detalle |
|---------|---------|
| **Tiempo** | 120 min |
| **Objetivo** | Entrenamiento distribuido multi-node |
| **Aprenderás** | Data/Model parallelism, DeepSpeed |
| **Entregable** | Training job distribuido funcionando |

### 📊 Checkpoint Nivel 6
```
□ Puedo conectar múltiples DGX Sparks
□ Entiendo NCCL y comunicación GPU-GPU
□ Puedo ejecutar training distribuido
□ Sé cuándo escalar horizontalmente
```

---

## Rutas de Especialización Recomendadas

### 🎯 Ruta: RAG & Agentes (Cerebro DS)
```
Nivel 1 (completo)
    ↓
Nivel 2: Ollama → vLLM → NIM
    ↓
Nivel 3: RAG Workbench → txt2kg → Multi-Agent
    ↓
Nivel 4: NeMo (para fine-tuning especializado)
    ↓
Nivel 5D: CUDA-X Data Science
```
**Duración**: ~25 horas

### 🎯 Ruta: MLOps & Producción
```
Nivel 1 (completo)
    ↓
Nivel 2: Ollama → vLLM → TRT-LLM → NIM
    ↓
Nivel 4: NeMo → Unsloth
    ↓
Nivel 5E: JAX Optimized
    ↓
Nivel 6 (si tienes 2 Sparks)
```
**Duración**: ~30 horas

### 🎯 Ruta: Generación Creativa
```
Nivel 1 (completo)
    ↓
Nivel 2: Ollama → vLLM
    ↓
Nivel 5A: Comfy UI → FLUX Fine-tuning
    ↓
Nivel 5B: Multi-modal → Live VLM → VSS
```
**Duración**: ~20 horas

### 🎯 Ruta: Data Science
```
Nivel 1 (completo)
    ↓
Nivel 2: Ollama
    ↓
Nivel 5D: CUDA-X → Portfolio → Single-cell
    ↓
Nivel 3: RAG Workbench → txt2kg
```
**Duración**: ~20 horas

### 🎯 Ruta: Robótica
```
Nivel 1 (completo)
    ↓
Nivel 2: Ollama → vLLM
    ↓
Nivel 5C: Isaac Sim → Isaac Lab
    ↓
Nivel 5B: Multi-modal → Live VLM
```
**Duración**: ~15 horas

---

## Calendario Sugerido

### Opción A: Intensivo (2 semanas, 4h/día)
```
Semana 1:
├── Día 1-2: Nivel 1 (Fundamentos)
├── Día 3-5: Nivel 2 (Inferencia)
├── Día 6-7: Nivel 3 (RAG & Agentes)

Semana 2:
├── Día 8-10: Nivel 4 (Fine-tuning)
├── Día 11-14: Nivel 5 (Especialización - elegir track)
```

### Opción B: Regular (4 semanas, 2h/día)
```
Semana 1: Nivel 1 + Nivel 2 (Ollama, vLLM)
Semana 2: Nivel 2 (TRT-LLM, NIM, SGLang) + Nivel 3
Semana 3: Nivel 4 (Fine-tuning)
Semana 4: Nivel 5 (Track elegido)
```

### Opción C: Relajado (8 semanas, 1h/día)
```
Semana 1-2: Nivel 1
Semana 3-4: Nivel 2
Semana 5: Nivel 3
Semana 6-7: Nivel 4
Semana 8: Nivel 5
```

---

## Métricas de Progreso

### Por Nivel
| Nivel | Labs | Horas | % Acumulado |
|-------|------|-------|-------------|
| 1 | 5 | 3-4h | 8% |
| 2 | 9 | 6-8h | 25% |
| 3 | 3 | 6-8h | 42% |
| 4 | 4 | 8-10h | 63% |
| 5 | 11 | 10-12h | 92% |
| 6 | 3 | 4-6h | 100% |

### Tracking Personal
```markdown
## Mi Progreso

### Nivel 1: Fundamentos
- [ ] 1.1 Connect to Your Spark
- [ ] 1.2 DGX Dashboard
- [ ] 1.3 VS Code Remote
- [ ] 1.4 Tailscale VPN
- [ ] 1.5 Vibe Coding

### Nivel 2: Inferencia
- [ ] 2.1 Ollama
- [ ] 2.2 Open WebUI
- [ ] 2.3 vLLM
- [ ] 2.4 TensorRT-LLM
- [ ] 2.5 NIM on Spark
- [ ] 2.6 SGLang
- [ ] 2.7 Nemotron
- [ ] 2.8 Speculative Decoding
- [ ] 2.9 NVFP4 Quantization

### Nivel 3: RAG & Agentes
- [ ] 3.1 RAG AI Workbench
- [ ] 3.2 Text to Knowledge Graph
- [ ] 3.3 Multi-Agent Chatbot

### Nivel 4: Fine-Tuning
- [ ] 4.1 PyTorch Fine-tune
- [ ] 4.2 Unsloth
- [ ] 4.3 LLaMA Factory
- [ ] 4.4 NeMo Fine-tune

### Nivel 5: Especialización
Track elegido: ________________
- [ ] Lab 5.X.1
- [ ] Lab 5.X.2
- [ ] Lab 5.X.3

### Nivel 6: Multi-Node (Opcional)
- [ ] 6.1 Connect Two Sparks
- [ ] 6.2 NCCL
- [ ] 6.3 Distributed Training
```

---

## Recursos Adicionales

### Documentación Oficial
- [DGX Spark User Guide](https://docs.nvidia.com/dgx/dgx-spark/)
- [NVIDIA Developer Forums](https://forums.developer.nvidia.com/c/accelerated-computing/dgx-spark-gb10)
- [NGC Catalog](https://catalog.ngc.nvidia.com/)

### Comunidad
- [NVIDIA Developer Discord](https://discord.gg/nvidia)
- [r/LocalLLaMA](https://reddit.com/r/LocalLLaMA)

### Cursos Complementarios
- [NVIDIA Deep Learning Institute](https://www.nvidia.com/en-us/training/)
- [Hugging Face Course](https://huggingface.co/course)

---

## Changelog

| Fecha | Cambio |
|-------|--------|
| 2026-01-16 | Plan de aprendizaje inicial |

---

*Plan diseñado para maximizar el aprendizaje progresivo y la retención de conocimientos en DGX Spark*
