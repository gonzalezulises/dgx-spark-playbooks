# 📋 Mi Plan de Aprendizaje - DGX Spark

> **Estudiante**: Ulises González  
> **Inicio**: 2026-01-16  
> **Meta**: Dominar los 33 playbooks de DGX Spark  
> **Track Principal**: RAG & Agentes (Cerebro DS)

---

## 📊 Dashboard de Progreso

```
Progreso General: ██░░░░░░░░░░░░░░░░░░ 8% (3/35 labs)

Nivel 1: ████████░░░░░░░░░░░░ 40% (2/5)
Nivel 2: ██░░░░░░░░░░░░░░░░░░ 11% (1/9)
Nivel 3: ░░░░░░░░░░░░░░░░░░░░ 0% (0/3)
Nivel 4: ░░░░░░░░░░░░░░░░░░░░ 0% (0/4)
Nivel 5: ░░░░░░░░░░░░░░░░░░░░ 0% (0/11)
Nivel 6: ░░░░░░░░░░░░░░░░░░░░ N/A (requiere 2 Sparks)
```

| Métrica | Valor |
|---------|-------|
| **Labs Completados** | 3 / 35 |
| **Horas Invertidas** | ~4h |
| **Horas Restantes** | ~40h |
| **Última Actividad** | 2026-01-16 |

---

## 🔑 API Keys (Checklist)

| Key | Obtenida | Fecha | Notas |
|-----|----------|-------|-------|
| [ ] NGC API Key | ❌ | - | [Obtener aquí](https://ngc.nvidia.com/setup/api-key) |
| [ ] HuggingFace Token | ❌ | - | [Obtener aquí](https://huggingface.co/settings/tokens) |
| [ ] Tavily API Key | ❌ | - | [Obtener aquí](https://tavily.com/) |

---

## 🎯 Nivel 1: Fundamentos de Infraestructura

> **Objetivo**: Dominar acceso, monitoreo y desarrollo remoto  
> **Duración Estimada**: 3-4 horas  
> **Estado**: 🟡 En Progreso

### Lab 1.1: Connect to Your Spark
| Campo | Valor |
|-------|-------|
| **Estado** | ✅ Completado |
| **Fecha Inicio** | 2026-01-15 |
| **Fecha Fin** | 2026-01-15 |
| **Tiempo Real** | 30 min |
| **Dificultad** | ⭐ Fácil |

**Verificación**:
```bash
✅ ssh usuario@dgx-spark funciona
✅ nvidia-smi muestra GPU
✅ Acceso desde red local
```

**Notas**:
> SSH configurado correctamente. IP: 192.168.x.x (configurar según tu red)

---

### Lab 1.2: DGX Dashboard
| Campo | Valor |
|-------|-------|
| **Estado** | ✅ Completado |
| **Fecha Inicio** | 2026-01-15 |
| **Fecha Fin** | 2026-01-15 |
| **Tiempo Real** | 20 min |
| **Dificultad** | ⭐ Fácil |

**Verificación**:
```bash
✅ Dashboard accesible via browser
✅ Métricas GPU visibles
✅ Métricas CPU/RAM visibles
```

**Notas**:
> Dashboard útil para monitorear cargas de trabajo. URL: http://dgx-spark:xxxx

---

### Lab 1.3: VS Code Remote
| Campo | Valor |
|-------|-------|
| **Estado** | ⬜ Pendiente |
| **Fecha Inicio** | - |
| **Fecha Fin** | - |
| **Tiempo Real** | - |
| **Dificultad** | - |

**Verificación**:
```bash
⬜ VS Code conectado via Remote-SSH
⬜ Puede editar archivos remotos
⬜ Terminal integrada funciona
```

**Notas**:
> 

---

### Lab 1.4: Tailscale VPN
| Campo | Valor |
|-------|-------|
| **Estado** | ⬜ Pendiente |
| **Fecha Inicio** | - |
| **Fecha Fin** | - |
| **Tiempo Real** | - |
| **Dificultad** | - |

**Verificación**:
```bash
⬜ Tailscale instalado en DGX
⬜ Tailscale instalado en máquina local
⬜ Acceso desde fuera de red local funciona
```

**Notas**:
> 

---

### Lab 1.5: Vibe Coding
| Campo | Valor |
|-------|-------|
| **Estado** | ⬜ Pendiente |
| **Fecha Inicio** | - |
| **Fecha Fin** | - |
| **Tiempo Real** | - |
| **Dificultad** | - |

**Verificación**:
```bash
⬜ AI assistant configurado en VS Code
⬜ Autocompletado funciona
⬜ Chat con AI funciona
```

**Notas**:
> 

---

### 📊 Checkpoint Nivel 1
```
[✓] Puedo acceder al DGX via SSH
[✓] Puedo monitorear GPU/CPU/RAM en dashboard
[ ] Tengo VS Code conectado remotamente
[ ] Puedo acceder desde fuera de mi red (Tailscale)
[ ] Tengo AI coding assistant configurado
```

**Fecha de Completación Nivel 1**: _________________

---

## 🚀 Nivel 2: Inferencia de Modelos

> **Objetivo**: Dominar diferentes backends de inferencia LLM  
> **Duración Estimada**: 6-8 horas  
> **Estado**: 🟡 En Progreso

### Lab 2.1: Ollama ⭐
| Campo | Valor |
|-------|-------|
| **Estado** | ✅ Completado |
| **Fecha Inicio** | 2026-01-15 |
| **Fecha Fin** | 2026-01-15 |
| **Tiempo Real** | 45 min |
| **Dificultad** | ⭐ Fácil |

**Verificación**:
```bash
✅ ollama run funciona
✅ API REST responde en :11434
✅ Modelos descargados: llama3.2, nomic-embed-text
```

**Modelos Instalados**:
| Modelo | Tamaño | Uso |
|--------|--------|-----|
| nomic-embed-text | 274MB | Embeddings para Cerebro DS |
| llama3.2 | 2GB | Chat general |

**Notas**:
> Base del sistema Cerebro DS. Embeddings funcionando correctamente.

---

### Lab 2.2: Open WebUI
| Campo | Valor |
|-------|-------|
| **Estado** | ⬜ Pendiente |
| **Fecha Inicio** | - |
| **Fecha Fin** | - |
| **Tiempo Real** | - |
| **Dificultad** | - |

**Verificación**:
```bash
⬜ Container Docker corriendo
⬜ UI accesible en browser
⬜ Conectado a Ollama
⬜ Chat funciona
```

**Notas**:
> 

---

### Lab 2.3: vLLM
| Campo | Valor |
|-------|-------|
| **Estado** | ⬜ Pendiente |
| **Fecha Inicio** | - |
| **Fecha Fin** | - |
| **Tiempo Real** | - |
| **Dificultad** | - |

**Verificación**:
```bash
⬜ vLLM instalado
⬜ Servidor corriendo
⬜ API OpenAI-compatible funciona
⬜ Benchmark vs Ollama realizado
```

**Benchmark vs Ollama**:
| Métrica | Ollama | vLLM |
|---------|--------|------|
| Tokens/seg | - | - |
| Latencia primer token | - | - |
| Memoria usada | - | - |

**Notas**:
> 

---

### Lab 2.4: TensorRT-LLM ⚠️
| Campo | Valor |
|-------|-------|
| **Estado** | ⬜ Pendiente |
| **Requisito** | NGC API Key |
| **Fecha Inicio** | - |
| **Fecha Fin** | - |
| **Tiempo Real** | - |
| **Dificultad** | - |

**Verificación**:
```bash
⬜ NGC API Key configurada
⬜ Modelo compilado con TRT
⬜ Servidor corriendo
⬜ Benchmark realizado
```

**Notas**:
> 

---

### Lab 2.5: NIM on Spark ⚠️
| Campo | Valor |
|-------|-------|
| **Estado** | ⬜ Pendiente |
| **Requisito** | NGC API Key |
| **Fecha Inicio** | - |
| **Fecha Fin** | - |
| **Tiempo Real** | - |
| **Dificultad** | - |

**Verificación**:
```bash
⬜ NGC login exitoso
⬜ Container NIM descargado
⬜ Llama 3.1 8B sirviendo
⬜ API funciona
```

**Notas**:
> 

---

### Lab 2.6: SGLang ⚠️
| Campo | Valor |
|-------|-------|
| **Estado** | ⬜ Pendiente |
| **Requisito** | HuggingFace Token |
| **Fecha Inicio** | - |
| **Fecha Fin** | - |
| **Tiempo Real** | - |
| **Dificultad** | - |

**Verificación**:
```bash
⬜ SGLang instalado
⬜ Servidor corriendo
⬜ Outputs JSON estructurados funcionan
```

**Notas**:
> 

---

### Lab 2.7: Nemotron
| Campo | Valor |
|-------|-------|
| **Estado** | ⬜ Pendiente |
| **Fecha Inicio** | - |
| **Fecha Fin** | - |
| **Tiempo Real** | - |
| **Dificultad** | - |

**Verificación**:
```bash
⬜ llama.cpp instalado
⬜ Modelo Nemotron descargado
⬜ Inferencia funciona
```

**Notas**:
> 

---

### Lab 2.8: Speculative Decoding
| Campo | Valor |
|-------|-------|
| **Estado** | ⬜ Pendiente |
| **Fecha Inicio** | - |
| **Fecha Fin** | - |
| **Tiempo Real** | - |
| **Dificultad** | - |

**Verificación**:
```bash
⬜ Draft model configurado
⬜ Target model configurado
⬜ Speedup medido: ___x
```

**Notas**:
> 

---

### Lab 2.9: NVFP4 Quantization
| Campo | Valor |
|-------|-------|
| **Estado** | ⬜ Pendiente |
| **Fecha Inicio** | - |
| **Fecha Fin** | - |
| **Tiempo Real** | - |
| **Dificultad** | - |

**Verificación**:
```bash
⬜ Modelo cuantizado a FP4
⬜ Inferencia funciona
⬜ Calidad vs original evaluada
```

**Notas**:
> 

---

### 📊 Checkpoint Nivel 2
```
[ ] Entiendo las diferencias entre backends de inferencia
[ ] Puedo elegir el backend correcto según el caso de uso
[ ] Sé cuándo usar Ollama vs vLLM vs TRT-LLM
[ ] Puedo optimizar inferencia con quantization
[ ] Entiendo speculative decoding
```

**Tabla Comparativa Personal**:
| Backend | Setup | Throughput | Latencia | Mi Preferencia |
|---------|-------|------------|----------|----------------|
| Ollama | ⭐⭐⭐⭐⭐ | - | - | - |
| vLLM | - | - | - | - |
| TRT-LLM | - | - | - | - |
| NIM | - | - | - | - |
| SGLang | - | - | - | - |

**Fecha de Completación Nivel 2**: _________________

---

## 🤖 Nivel 3: RAG y Sistemas Agentic

> **Objetivo**: Construir sistemas RAG y agentes inteligentes  
> **Duración Estimada**: 6-8 horas  
> **Estado**: ⬜ No Iniciado  
> **Prioridad**: 🔴 ALTA (Core de Cerebro DS)

### Lab 3.1: RAG Application in AI Workbench ⚠️
| Campo | Valor |
|-------|-------|
| **Estado** | ⬜ Pendiente |
| **Requisito** | NGC + Tavily API Keys |
| **Fecha Inicio** | - |
| **Fecha Fin** | - |
| **Tiempo Real** | - |
| **Dificultad** | - |

**Verificación**:
```bash
⬜ AI Workbench instalado
⬜ Proyecto RAG clonado
⬜ API keys configuradas
⬜ Chat RAG funciona
⬜ Web search funciona
```

**Conceptos Aprendidos**:
- [ ] Route-Evaluate-Iterate pattern
- [ ] Detección de alucinaciones
- [ ] Web search fallback

**Notas**:
> 

---

### Lab 3.2: Text to Knowledge Graph ⚠️
| Campo | Valor |
|-------|-------|
| **Estado** | ⬜ Pendiente |
| **Requisito** | API Keys varios |
| **Fecha Inicio** | - |
| **Fecha Fin** | - |
| **Tiempo Real** | - |
| **Dificultad** | - |
| **Prioridad** | 🔴 ALTA - Hybrid retrieval para Cerebro DS |

**Verificación**:
```bash
⬜ Entity extraction funciona
⬜ Relationship mapping funciona
⬜ Knowledge graph visualizable
⬜ Queries sobre el graph funcionan
```

**Aplicación a Cerebro DS**:
- [ ] Planificar integración con Qdrant existente
- [ ] Definir schema de entidades para Data Science
- [ ] Probar hybrid retrieval (vector + graph)

**Notas**:
> 

---

### Lab 3.3: Multi-Agent Chatbot ⚠️
| Campo | Valor |
|-------|-------|
| **Estado** | ⬜ Pendiente |
| **Requisito** | NGC/OpenAI Keys |
| **Fecha Inicio** | - |
| **Fecha Fin** | - |
| **Tiempo Real** | - |
| **Dificultad** | - |

**Verificación**:
```bash
⬜ Orchestrator configurado
⬜ Agentes especializados creados
⬜ Tool use funciona
⬜ Memory compartida funciona
```

**Agentes a Implementar para Cerebro DS**:
| Agente | Rol | Estado |
|--------|-----|--------|
| Retriever | Buscar en vector DB | ⬜ |
| GraphExplorer | Navegar knowledge graph | ⬜ |
| Synthesizer | Combinar información | ⬜ |
| Validator | Detectar alucinaciones | ⬜ |

**Notas**:
> 

---

### 📊 Checkpoint Nivel 3
```
[ ] Entiendo el patrón Route-Evaluate-Iterate
[ ] Puedo construir knowledge graphs desde documentos
[ ] Sé orquestar múltiples agentes
[ ] Entiendo cuándo usar RAG vs Knowledge Graph vs Hybrid
[ ] Puedo implementar detección de alucinaciones
```

**Fecha de Completación Nivel 3**: _________________

---

## 🎓 Nivel 4: Fine-Tuning de Modelos

> **Objetivo**: Personalizar modelos para casos de uso específicos  
> **Duración Estimada**: 8-10 horas  
> **Estado**: ⬜ No Iniciado

### Lab 4.1: Fine-tune with PyTorch ⚠️
| Campo | Valor |
|-------|-------|
| **Estado** | ⬜ Pendiente |
| **Requisito** | HuggingFace Token |
| **Fecha Inicio** | - |
| **Fecha Fin** | - |
| **Tiempo Real** | - |
| **Dificultad** | - |

**Verificación**:
```bash
⬜ Dataset preparado
⬜ Training loop funciona
⬜ Checkpoints guardados
⬜ Modelo evaluado
```

**Notas**:
> 

---

### Lab 4.2: Unsloth ⚠️
| Campo | Valor |
|-------|-------|
| **Estado** | ⬜ Pendiente |
| **Requisito** | HuggingFace Token |
| **Fecha Inicio** | - |
| **Fecha Fin** | - |
| **Tiempo Real** | - |
| **Dificultad** | - |

**Verificación**:
```bash
⬜ Unsloth instalado
⬜ LoRA training funciona
⬜ 2x speedup verificado
```

**Notas**:
> 

---

### Lab 4.3: LLaMA Factory ⚠️
| Campo | Valor |
|-------|-------|
| **Estado** | ⬜ Pendiente |
| **Requisito** | HuggingFace Token |
| **Fecha Inicio** | - |
| **Fecha Fin** | - |
| **Tiempo Real** | - |
| **Dificultad** | - |

**Verificación**:
```bash
⬜ UI funciona
⬜ LoRA training completado
⬜ QLoRA training completado
⬜ Modelo exportado
```

**Métodos Probados**:
| Método | Funciona | Tiempo | Calidad |
|--------|----------|--------|---------|
| LoRA | ⬜ | - | - |
| QLoRA | ⬜ | - | - |
| Full FT | ⬜ | - | - |

**Notas**:
> 

---

### Lab 4.4: Fine-tune with NeMo ⚠️
| Campo | Valor |
|-------|-------|
| **Estado** | ⬜ Pendiente |
| **Requisito** | HuggingFace Token |
| **Fecha Inicio** | - |
| **Fecha Fin** | - |
| **Tiempo Real** | - |
| **Dificultad** | - |

**Verificación**:
```bash
⬜ NeMo AutoModel instalado
⬜ Recipe ejecutado
⬜ Checkpoint guardado
⬜ Modelo publicado en HF (opcional)
```

**Notas**:
> 

---

### 📊 Checkpoint Nivel 4
```
[ ] Entiendo la diferencia entre LoRA, QLoRA, full fine-tuning
[ ] Puedo elegir el método correcto según recursos/objetivo
[ ] Sé preparar datasets para fine-tuning
[ ] Puedo evaluar modelos fine-tuned
[ ] Entiendo trade-offs de cada framework
```

**Fecha de Completación Nivel 4**: _________________

---

## 🔬 Nivel 5: Aplicaciones Especializadas

> **Objetivo**: Dominar casos de uso avanzados  
> **Duración Estimada**: 10-12 horas  
> **Track Elegido**: ⬜ Por definir

### Mi Track: _________________

*(Completar según el track elegido)*

#### Lab 5.X.1: _________________
| Campo | Valor |
|-------|-------|
| **Estado** | ⬜ Pendiente |
| **Fecha Inicio** | - |
| **Fecha Fin** | - |

**Notas**:
> 

---

### 📊 Checkpoint Nivel 5
```
[ ] Completé al menos 2 tracks completos
[ ] Puedo elegir herramientas según el dominio
[ ] Entiendo las capacidades del track elegido
```

**Fecha de Completación Nivel 5**: _________________

---

## 🌐 Nivel 6: Multi-Node (Opcional)

> **Estado**: ❌ No disponible (requiere 2 DGX Sparks)

---

## 📝 Diario de Aprendizaje

### Semana 1 (2026-01-15 - 2026-01-21)

**Día 1 (2026-01-15)**:
- ✅ Configuré SSH al DGX Spark
- ✅ Instalé Ollama y modelos base
- ✅ Pipeline de Cerebro DS funcional
- 📝 Aprendí: Qdrant query_points API

**Día 2 (2026-01-16)**:
- ✅ Análisis de playbooks NVIDIA vs Cerebro DS
- ✅ Documentación de decisiones arquitectónicas
- ✅ Plan de aprendizaje creado
- 📝 Aprendí: NVIDIA Agentic RAG usa Route-Evaluate-Iterate

**Día 3 (2026-01-17)**:
- ⬜ 
- 📝 Aprendí: 

**Día 4 (2026-01-18)**:
- ⬜ 
- 📝 Aprendí: 

**Día 5 (2026-01-19)**:
- ⬜ 
- 📝 Aprendí: 

---

### Semana 2 (2026-01-22 - 2026-01-28)

*(Agregar entradas según avances)*

---

## 🎯 Objetivos Semanales

### Semana Actual: 2026-01-15 - 2026-01-21

| Objetivo | Estado | Notas |
|----------|--------|-------|
| Completar Nivel 1 | 🟡 40% | Falta VS Code, Tailscale, Vibe |
| Obtener NGC API Key | ⬜ | - |
| Obtener HF Token | ⬜ | - |
| Instalar Open WebUI | ⬜ | - |

### Próxima Semana: 2026-01-22 - 2026-01-28

| Objetivo | Estado | Notas |
|----------|--------|-------|
| Completar Nivel 2 (labs 2.1-2.5) | ⬜ | - |
| Comparar Ollama vs vLLM | ⬜ | - |
| Probar NIM on Spark | ⬜ | - |

---

## 🏆 Logros Desbloqueados

| Logro | Fecha | Descripción |
|-------|-------|-------------|
| 🥇 Primer Acceso | 2026-01-15 | SSH al DGX Spark funcional |
| 🤖 Primer Modelo | 2026-01-15 | Ollama con Llama 3.2 corriendo |
| 📚 RAG Funcional | 2026-01-16 | Cerebro DS respondiendo queries |
| 📋 Plan Maestro | 2026-01-16 | Learning path documentado |

### Logros Pendientes
- ⬜ 🔧 Infraestructura Completa (Nivel 1)
- ⬜ 🚀 Inference Master (Nivel 2)
- ⬜ 🤖 Agente Constructor (Nivel 3)
- ⬜ 🎓 Fine-Tuner (Nivel 4)
- ⬜ 🔬 Especialista (Nivel 5)
- ⬜ 🌐 Distributed (Nivel 6 - requiere 2 Sparks)

---

## 📊 Estadísticas Finales

*(Completar al terminar)*

| Métrica | Valor |
|---------|-------|
| **Labs Completados** | ___ / 35 |
| **Horas Totales** | ___ h |
| **Fecha Inicio** | 2026-01-15 |
| **Fecha Fin** | __________ |
| **Track Completado** | __________ |
| **Certificación** | N/A |

---

## 🔗 Referencias Rápidas

| Recurso | URL |
|---------|-----|
| Learning Path Completo | [LEARNING-PATH.md](./LEARNING-PATH.md) |
| Análisis Cerebro DS | [CEREBRO-DS-ANALYSIS.md](./CEREBRO-DS-ANALYSIS.md) |
| DGX Spark Docs | [nvidia.com/dgx-spark](https://www.nvidia.com/en-us/products/workstations/dgx-spark/) |
| NGC Catalog | [catalog.ngc.nvidia.com](https://catalog.ngc.nvidia.com/) |
| Cerebro DS Repo | [github.com/gonzalezulises/cerebro-ds](https://github.com/gonzalezulises/cerebro-ds) |

---

*Última actualización: 2026-01-16*
