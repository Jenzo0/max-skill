# 🧠 AI/ML & Data Science Capabilities

> Load this module for ML/AI, data science, LLM ops, or training tasks.
> Load trigger: Code / Architect / DevOps mode with AI/ML-related request.

## Core Frameworks
- **Training**: PyTorch (Lightning, FSDP, DDP), TensorFlow/Keras, JAX (Flax, Haiku)
- **ML Pipeline**: scikit-learn, XGBoost, LightGBM, CatBoost
- **NLP**: Transformers (HuggingFace), spaCy, NLTK, LangChain, LlamaIndex
- **Computer Vision**: OpenCV, Detectron2, YOLO, SAM, CLIP, Stable Diffusion
- **Audio**: Whisper, pyannote, torchaudio, funasr

## LLM Operations
- **Inference**: vLLM, TGI, llama.cpp (GGUF), Ollama, OpenRouter, Together
- **Quantization**: 4-bit (NF4, GPTQ), 8-bit (FP8, INT8), GGUF quantization (Q2-Q8, IQ)
- **Fine-tuning**: LoRA, QLoRA, DoRA, ORPO, DPO — HuggingFace TRL, Axolotl, Unsloth
- **Evaluation**: lm-eval-harness, OpenAI Evals, AlpacaEval, MT-Bench
- **RAG**: ChromaDB, Qdrant, Weaviate, Pinecone, Haystack, RAPTOR

## Data Processing
- **Structured**: pandas, polars, DuckDB, SQL-based ETL
- **Unstructured**: BeautifulSoup, PyMuPDF, Unstructured.io, tika
- **Streaming**: Kafka, Spark, Flink (batch + stream processing)
- **Feature Stores**: Feast, Tecton (feature engineering + serving)

## Model Serving
- **REST API**: FastAPI + Pydantic model schemas + batching
- **Serverless**: AWS SageMaker, GCP Vertex AI, Modal, Replicate
- **Batching**: Celery + Redis, Ray Serve, Argo Workflows
- **Monitoring**: Prometheus metrics, custom health checks, drift detection

## MLOps
- **Experiment Tracking**: Weights & Biases, MLflow, Neptune, Comet
- **Orchestration**: Airflow, Prefect, Dagster, Metaflow
- **CI/CD for ML**: DVC (data versioning), CML, GitHub Actions for model training
- **Model Registry**: MLflow Model Registry, HuggingFace Hub, S3 model store
- **Feature Pipelines**: Automated ETL + feature computation + validation

## Best Practices
- Pin random seeds for reproducibility (torch, numpy, python random)
- Log hyperparameters, metrics, and model artifacts per run
- Use gradient accumulation for large batch sizes on limited GPU memory
- Monitor for data drift (Evidently, WhyLogs, NannyML) in production
- Separate training, validation, and test sets — never tune on test data
- Start with a simple baseline before adding complexity
