# 🧠 AI/ML & Data Science Capabilities

> Load trigger: Code/Architect/DevOps mode with AI/ML-related request.

## Core Frameworks

| Domain | Tools |
|---|---|
| Training | PyTorch (Lightning, FSDP, DDP), JAX (Flax, Haiku), TensorFlow/Keras |
| ML Pipeline | scikit-learn, XGBoost, LightGBM, CatBoost |
| NLP | Transformers (HuggingFace), spaCy, LangChain, LlamaIndex |
| Computer Vision | OpenCV, YOLO, SAM, CLIP, Stable Diffusion, Detectron2 |
| Audio | Whisper, pyannote, torchaudio, funasr |

## LLM Operations

| Task | Tools |
|---|---|
| Inference | vLLM, TGI, llama.cpp (GGUF), Ollama, OpenRouter, Together |
| Quantization | NF4, GPTQ, FP8, INT8, GGUF Q2-Q8, IQ |
| Fine-tuning | LoRA, QLoRA, DoRA, ORPO, DPO via HF TRL, Axolotl, Unsloth |
| Evaluation | lm-eval-harness, AlpacaEval, MT-Bench, OpenAI Evals |
| RAG | ChromaDB, Qdrant, Weaviate, Pinecone, Haystack |

## MLOps

| Concern | Tools |
|---|---|
| Experiment tracking | Weights & Biases, MLflow, Neptune, Comet |
| Pipeline orchestration | Airflow, Prefect, Dagster, Metaflow |
| Data versioning | DVC, LakeFS, Quilt |
| Model registry | MLflow Registry, HuggingFace Hub, S3 |
| Monitoring | Evidently, WhyLogs, NannyML (drift detection) |

## Best Practices

- Pin random seeds for reproducibility (`torch`, `numpy`, `random`)
- Log hyperparameters, metrics, artifacts per run
- Use gradient accumulation for large batch sizes on limited GPU memory
- Monitor for data drift in production
- Separate training, validation, test sets — tune on validation, evaluate on test once
- Start with a simple baseline before adding complexity
