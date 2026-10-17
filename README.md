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

- [Sector Overview & Market Dynamics](#sector-overview--market-dynamics)

- [SaaS/Hosted Platforms](#saas-hosted-platforms)

- [Open-Source GitHub Projects](#open-source-github-projects)

- [How to Contribute](#how-to-contribute)

- [Disclaimer](#disclaimer)



## Sector Overview & Market Dynamics



**Estimated market size** — The MLOps / model-serving segment covered by this list was valued at **~$3.0B in 2025** and is forecast to grow to **~$16.6B by 2030 (40.5% CAGR)** ([Grand View Research](https://www.grandviewresearch.com/industry-analysis/mlops-market-report)); with the adjacent AI inference-as-a-service and LLMOps layers, analysts put the broader serving market in the **tens of billions by the early 2030s**, and Bloomberg has estimated inference alone could become a **~$487B/yr market** as it outpaces training spend.

**Fragmentation** — **Moderately fragmented overall, with winner-take-all dynamics at the top**: the tooling/DevTool layer is crowded and standards-free (a dozen competing open engines — vLLM, SGLang, TensorRT-LLM, Triton, Ray Serve — with no single winner), but the hosted layer is highly concentrated — three hyperscalers (AWS, Azure, Google Cloud) take the majority of platform spend, and a handful of frontier-model APIs absorb most token revenue. Expect open fragmentation below, oligopoly above.



## SaaS/Hosted Platforms



Hosted LLM/ML model-serving platforms compared side by side, **sorted by company size (largest first)**. **Prices below are the specific publicly listed starting rates (verified October 2026, in USD)** — final cost varies with region, instance type, and usage.



| Product | Description | Company Size (revenue / valuation) | Starting Price | Free Tier / Trial |
|---|---|---|---|---|
| **[AWS SageMaker AI](https://aws.amazon.com/sagemaker/)** | Fully managed ML platform with real-time inference endpoints, serverless inference, and asynchronous batch transform; supports Triton, vLLM, and custom containers. | **Hyperscaler** — AWS segment revenue **$128.7B (FY2025, +20% YoY)**; parent Amazon total revenue $638B+ | Real-time endpoint **ml.m5.large at $0.115 per instance-hour** (us-east-1); Serverless Inference billed per inference duration + data processed | **Free tier for the first 2 months**: **125 hrs/month** of ml.m5.xlarge real-time endpoints **or** **150,000 seconds/month** of Serverless Inference |
| **[Azure ML](https://azure.microsoft.com/en-us/products/machine-learning/)** | Microsoft's managed ML platform with managed online endpoints, batch inference, and integration with Azure OpenAI Service for enterprise LLM deployments. | **Hyperscaler** — Azure & other cloud services **$75B+ revenue (FY2025)**; Microsoft total revenue $281.7B | GPU endpoint VM **NC4as T4 v3 at $383.98/month (~$0.53/hr)**; no extra Azure ML platform fee — the VM is the serving cost | **$200 Azure credit for 30 days** for new accounts (spendable on ML endpoints); the Azure ML service is free but endpoint compute is always billable |
| **[Google Vertex AI](https://cloud.google.com/vertex-ai)** | Google's end-to-end ML platform with Model Garden for open models, prediction endpoints, and Vertex AI Agent Builder for orchestrating LLM applications. | **Hyperscaler** — Google Cloud segment revenue **$58.7B (2025)**, exiting 2025 at a **$70B+ annual run-rate** | LLM inference **Gemini 2.5 Flash-Lite from $0.10 per 1M input tokens + $0.40 per 1M output tokens** (Flash: $0.30 / $2.50 per 1M tokens) | **$300 Google Cloud credit for 90 days** for new customers (applies to Vertex AI endpoints and LLM inference; some managed third-party models excluded) |
| **[Databricks Model Serving](https://www.databricks.com/product/model-serving)** | Unified serving layer for ML models and LLMs with auto-scaling, GPU optimization, and native MLflow integration within the Databricks Lakehouse platform. | Private, late-stage — **$4.8B+ revenue run-rate (Q3 2025, +55% YoY)**; **$134B valuation** (Series L, Dec 2025) | Serverless endpoints from **$0.070 per DBU** (rate includes the cloud instance cost); GPU endpoints from **10.48 DBU/hr per NVIDIA T4 GPU** | **14-day free trial with up to $400 in compute credits**; plus a free **Serverless Edition** workspace for personal use (daily limits, **no GPUs**) |
| **[Modal](https://modal.com/)** | Serverless GPU platform with Python-native infrastructure-as-code; sub-second cold starts and per-second billing ideal for bursty LLM inference workloads. | Growth-stage startup — **$1B+ annualized revenue run-rate**; **$15.75B valuation** (Series D, $750M raised; $1.2B+ total funding) | Per-second GPU billing from **$0.000164/sec (~$0.59/hr) for NVIDIA T4**; **L4 from $0.000222/sec (~$0.80/hr)** | **Free Starter plan**: **$30 in compute credits every month**, 3 seats, 100 containers, 10 concurrent GPUs, 1 TiB/month free egress |
| **[BentoML / BentoCloud](https://www.bentoml.com/)** | Open-source model serving framework (with hosted BentoCloud, acquired by Modular in Feb 2026) offering adaptive batching, multi-model composition, and scale-to-zero. | Small startup — **~$9M total funding**, ~19 employees; acquired by **Modular** (Feb 2026, terms undisclosed) | BentoCloud managed cluster **from $35,000/year** (12-month contract, AWS Marketplace); self-hosted open-source framework **$0** | **Free forever**: unlimited self-hosted serving on your own hardware (Apache 2.0, no licence cost, no endpoint caps); **no free cloud tier** — BentoCloud requires a paid contract |



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
# Awesome-LLM-Application-Architectures

