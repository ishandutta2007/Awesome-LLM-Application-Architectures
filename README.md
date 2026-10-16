# Awesome-LLM-Application-Architectures

## Top LLM Application Architectures Ecosystem



**Curated List of SaaS Products & Open-Source GitHub Projects**  

*Focused on Model Serving, Inference Optimization & Production RAG Systems*  

**Last updated: March 2026**



This repository tracks notable **SaaS platforms** and **open-source projects** for **LLM Application Architectures**. These tools provide the serving infrastructure, orchestration layers, and scaling mechanisms needed to deploy production-grade LLM applications—from RAG pipelines and agent systems to high-throughput inference APIs.



**Examples** include Databricks Model Serving, AWS SageMaker, Azure ML, Google Vertex AI, BentoML, Seldon, Triton Inference Server, Ray Serve, KServe, and Modal (the category leaders).



**Open-source emphasis**: This section is heavily expanded with every major active project for self-hosting, Kubernetes-native serving, and transparent inference orchestration—ideal for ML engineers, platform teams, and researchers building vendor-neutral LLM infrastructure.



Contributions welcome! Open a PR to add/update entries. Keep descriptions factual and link to official sites.



## Table of Contents

- [SaaS/Hosted Platforms](#saas-hosted-platforms)

- [Open-Source GitHub Projects](#open-source-github-projects)

- [How to Contribute](#how-to-contribute)

- [Disclaimer](#disclaimer)



## SaaS/Hosted Platforms



- **[Databricks Model Serving](https://www.databricks.com/product/model-serving)**  

  Unified serving layer for ML models and LLMs with auto-scaling, GPU optimization, and native MLflow integration within the Databricks Lakehouse platform.



- **[AWS SageMaker](https://aws.amazon.com/sagemaker/)**  

  Fully managed ML platform with real-time inference endpoints, serverless inference, and asynchronous batch transform; supports Triton, vLLM, and custom containers.



- **[Azure ML](https://azure.microsoft.com/en-us/products/machine-learning/)**  

  Microsoft's managed ML platform with managed online endpoints, batch inference, and integration with Azure OpenAI Service for enterprise LLM deployments.



- **[Google Vertex AI](https://cloud.google.com/vertex-ai)**  

  Google's end-to-end ML platform with Model Garden for open models, prediction endpoints, and Vertex AI Agent Builder for orchestrating LLM applications.



- **[BentoML](https://www.bentoml.com/)**  

  Open-source model serving framework (with hosted BentoCloud) offering adaptive batching, multi-model composition, and scale-to-zero for cost-efficient inference.



- **[Modal](https://modal.com/)**  

  Serverless GPU platform with Python-native infrastructure-as-code; sub-second cold starts and second-level billing ideal for bursty LLM inference workloads.



## Open-Source GitHub Projects



- **[Ray Serve](https://github.com/ray-project/ray)**  

  **The dominant framework for distributed LLM serving** — builds on Ray to orchestrate multi-model pipelines, heterogeneous GPU workloads, and autoscaling inference services. Powers Anyscale Endpoints and integrates natively with vLLM, SGLang, and Transformers .



- **[KServe](https://github.com/kserve/kserve)**  

  Kubernetes-native model serving platform (formerly KFServing) under the Kubeflow ecosystem. Provides canary deployments, A/B testing, payload logging, and auto-scaling via Knative/KEDA. Apache 2.0 licensed with no commercial restrictions .



- **[Triton Inference Server](https://github.com/triton-inference-server/server)**  

  NVIDIA's high-performance inference server supporting TensorFlow, PyTorch, ONNX, TensorRT, and tree models via FIL backend. Multi-framework serving in a single deployment with dynamic batching and GPU optimization .



- **[Seldon Core](https://github.com/SeldonIO/seldon-core)**  

  Kubernetes-based model deployment with pipeline DAGs, drift detection, and canary rollouts. **Critical version note**: v1.x is BUSL-1.1 (restricted for commercial hosting); v2.x is Apache 2.0 licensed and safe for production use .



- **[BentoML](https://github.com/bentoml/BentoML)**  

  Python-first serving framework with Runner abstraction for custom inference logic, adaptive batching, and multi-model pipelines. Faster cold starts than KServe for serverless deployments .



- **[RayLLM](https://github.com/ray-project/ray-llm)**  

  **LLM serving solution built on Ray Serve** — pre-configured open-source models with continuous batching, quantization, scale-to-zero autoscaling, and OpenAI-compatible REST API. Supports multi-GPU and multi-node deployments out of the box .



- **[vLLM](https://github.com/vllm-project/vllm)**  

  **Production-default LLM inference engine** with PagedAttention for memory-efficient KV cache management. Continuous batching, prefix caching, and disaggregated prefill/decode support (0.6+). Red Hat is the largest corporate contributor .



- **[SGLang](https://github.com/sgl-project/sglang)**  

  **Fastest inference engine for chat, agents, and RAG workloads** — RadixAttention for KV cache reuse across related requests (6.4x throughput vs baseline, 3.7x lower latency than vLLM on chat). Native disaggregated inference support .



- **[Dify](https://github.com/langgenius/dify)**  

  **Most-starred open-source LLM platform** (142K+ stars) — combines orchestration, prompt management, evaluation, and deployment for production LLM apps. Modified Apache 2.0 with commercial restrictions on multi-tenant SaaS .



- **[NVIDIA Dynamo](https://github.com/ai-dynamo/dynamo)**  

  Production-grade disaggregated inference framework from NVIDIA (GTC 2025). Native prefill/decode separation with RDMA/NVLink KV cache transfer; supports vLLM, SGLang, and TensorRT-LLM backends at data center scale .



- **[Mooncake](https://github.com/kvcache-ai/Mooncake)**  

  **Distributed KV cache store for agentic workloads** — vLLM integration achieves 3.8x higher throughput, 46x lower TTFT, and 8.6x lower end-to-end latency on realistic agent traces with 94.2% cache hit rates .



### Additional Strong Open-Source Options



- **[LitServe](https://github.com/bhimrazy/LitServe)** — Build custom inference servers in pure Python for agents, RAG, and multi-model pipelines. 2x faster than FastAPI, supports batching and streaming .

- **[Wingman](https://github.com/adrianliechti/wingman)** — Self-hosted inference hub aggregating OpenAI, Anthropic, Ollama, and MCP servers behind a unified API with built-in RAG and agent support .

- **[TensorRT-LLM](https://github.com/NVIDIA/TensorRT-LLM)** — Maximum NVIDIA performance for latency-critical workloads; requires 1-2 weeks setup but delivers best throughput on Blackwell (B200, GB200) .

- **[llama.cpp](https://github.com/ggerganov/llama.cpp)** — CPU/edge/mobile inference with Metal support for Apple Silicon; best for on-prem or low-cost infrastructure .

- **[MLflow](https://github.com/mlflow/mlflow)** — Model registry and experiment tracking; Apache 2.0 licensed, integrates with serving frameworks .

- **[Alibi Detect](https://github.com/SeldonIO/alibi-detect)** — Drift and outlier detection that integrates natively with Seldon and KServe for production monitoring .

- **[Feast](https://github.com/feast-dev/feast)** — Open-source feature store; co-located Redis/DynamoDB achieves sub-10ms retrieval for fraud detection and real-time ML .



**Frameworks for building custom systems**: Combine **vLLM** or **SGLang** for inference, **Ray Serve** or **KServe** for orchestration, **Mooncake** for distributed KV caching in agentic workloads, and **Alibi Detect** for drift monitoring. For RAG pipelines, layer in **Dify** or **Flowise** for visual orchestration with **Feast** for feature management. For enterprise Kubernetes, **KServe + Triton + vLLM** provides a fully open, production-grade stack .



## How to Contribute



1. Fork the repo.

2. Add/edit entries in `README.md` (follow existing format).

3. Include: name, link, 1–2 sentence description, and whether it's SaaS or open-source.

4. Submit PR with a short explanation.



Star the repo if you find it useful!



## Disclaimer



- This is a **community-curated** list — not exhaustive and not an endorsement.

- **License awareness is critical**: Seldon Core v1.x uses BUSL-1.1 (restricts commercial hosting); v2.x is Apache 2.0. BentoML, Ray, and MLflow have "open core" models where enterprise features require commercial licenses .

- LLM serving infrastructure requires GPU capacity planning, KV cache management, and proper autoscaling configuration for production workloads.

- Self-hosted solutions require Kubernetes operational expertise and regular security updates.



---



**Made for ML engineers, platform architects, AI infrastructure teams, and open-source enthusiasts.**  

Let's make LLM serving more open, scalable, and vendor-neutral.
