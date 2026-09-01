# Co-founder & CTO @ [Compresr](https://compresr.ai) · Y Combinator W26

**Building context-compression infrastructure for LLMs** | MSc Data Science @ EPFL, minor in Cyber Security

First author at **EMNLP 2025 Findings** · co-author in **Nature Communications** · [ousso11.github.io](https://ousso11.github.io)

I work on making language models behave under tight context budgets — the research at [EPFL's dlab](https://dlab.epfl.ch), and now the systems that put it into production: a multi-tenant API, an open-source Go proxy, GPU serving on EKS, and the benchmarks we use to decide whether a change is real.

---

### 🚀 What I'm Building

**[Context Gateway](https://github.com/Compresr-ai/Context-Gateway)** — ![Stars](https://img.shields.io/github/stars/Compresr-ai/Context-Gateway?style=flat-square&color=yellow) ![Go](https://img.shields.io/badge/-Go-00ADD8?style=flat-square&logo=go&logoColor=white) ![License](https://img.shields.io/badge/license-Apache%202.0-blue?style=flat-square)

A proxy between your coding agent and its LLM that keeps the context window small. It summarises **in a background worker** and intercepts the agent's own compaction request — so compacting returns something that already exists instead of stalling your session. Compression is reversible: tool outputs become references, and a phantom `expand_context` tool lets the model pull the original back.

*8 LLM backends · works with Claude Code, Codex, Cursor, OpenCode, OpenClaw · 47K lines of Go, 1K+ tests · single binary, 5 platforms.*

**[Compresr SDKs](https://pypi.org/project/compresr/)** — ![PyPI](https://img.shields.io/pypi/v/compresr?style=flat-square) ![npm](https://img.shields.io/npm/v/compresr?style=flat-square)

Python and TypeScript clients for the compression API. Sync, async, batch and streaming. Integrations for LangChain, LangGraph, LlamaIndex, LiteLLM and Hermes — every peer dependency optional, so it never touches your pinned `openai` version.

```bash
pip install compresr        # Python
npm install @compresr/sdk   # TypeScript
```

---

### 📄 Publications

**[GRAD: Generative Retrieval-Aligned Demonstration Sampler](https://aclanthology.org/2025.findings-emnlp.1047/)** — *first author (equal contribution)*, **Findings of EMNLP 2025**  
Rather than retrieving few-shot examples from a database, train an LLM with **GRPO** to write one per question. Beats RAG baselines on GSM8K, MATH and ARC with shorter demonstrations *and* shorter answers. [`code`](https://github.com/charafkamel/GRAD-demonstration-sampler)

**[Cmprsr: Abstractive Token-Level Question-Agnostic Prompt Compressor](https://arxiv.org/abs/2511.12281)** — *co-author*, under review at **ACL 2026**  
Compression that doesn't need the question up front, so one compressed prompt serves whatever gets asked next. Beats LLMLingua-2 at matched token budgets.

**[Generative approaches to kinetic parameter inference in metabolic networks](https://www.nature.com/articles/s41467-026-72184-3)** — *co-author*, **Nature Communications** 2026  
GAN latent spaces in place of expensive sampling-based parameter estimation.

---

### 🔍 Engineering & Research Journal

Write-ups of bugs and measurement failures worth remembering — at [ousso11.github.io/journal](https://ousso11.github.io/journal/):

- **[The GPU that said yes and ran on CPU](https://ousso11.github.io/journal/onnx-silent-cpu-fallback/)** — onnxruntime reported CUDA available while every session ran on CPU. Nothing raised; production was just slow for weeks.
- **[The autoscaling study that crowned the wrong winner](https://ousso11.github.io/journal/score-the-decision-not-the-launch/)** — we measured instance *availability* instead of the scaling *decision*, showing a 33× gap in reaction time as 7×.
- **[The cheaper agent that wasn't](https://ousso11.github.io/journal/cache-token-mispricing/)** — prompt-cache tokens priced at zero understated cost up to 47%, and the headline finding didn't survive correct accounting.
- **[`max_tokens=20` produced 200 tokens](https://ousso11.github.io/journal/bind-tools-drops-kwargs/)** — only when tools were attached, because `bind_tools()` strips a prior `bind()`.

---

### **Programming Languages**
![Python](https://img.shields.io/badge/-Python-3776AB?style=flat-square&logo=python&logoColor=white)  ![Go](https://img.shields.io/badge/-Go-00ADD8?style=flat-square&logo=go&logoColor=white)  ![TypeScript](https://img.shields.io/badge/-TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)  ![SQL](https://img.shields.io/badge/-SQL-4479A1?style=flat-square&logo=postgresql&logoColor=white)  ![C++](https://img.shields.io/badge/-C++-00599C?style=flat-square&logo=cplusplus&logoColor=white)  ![Bash](https://img.shields.io/badge/-Bash-4EAA25?style=flat-square&logo=gnubash&logoColor=white)

### **AI/ML Frameworks & Libraries**
**Core ML:** PyTorch • Scikit-learn  
**LLM Ecosystem:** HuggingFace 🤗 • LangChain 🦜 • LangGraph • LlamaIndex 🦙 • LiteLLM • MCP  
**Training & Fine-tuning:** TRL • PEFT • LoRA • GRPO • PPO • DPO • Quantization (FP8)  
**Serving:** vLLM • SageMaker • GPU autoscaling  
**Graph ML:** TorchGeometric • NetworkX  
**Computer Vision:** OpenCV • TorchVision

### **Backend & Infrastructure**
**Backend:** FastAPI • PostgreSQL (row-level security) • Redis • Stripe • REST/SSE streaming • Next.js • React  
**Cloud:** AWS (EKS, ECS Fargate, SageMaker, ElastiCache, ECR, ALB, CloudWatch) • Terraform • Docker • Kubernetes • Karpenter  
**Practices:** pytest / Vitest / Playwright • CI/CD (GitHub Actions) • Sentry • Prometheus • SBOM & container security • **SOC 2 Type I**

### **Specializations**
**Efficient LLMs:** prompt compression • long-context evaluation • KV/context management • agent harnesses  
**Reinforcement Learning:** GRPO • PPO • DPO • reward design  
**Multimodal & Graphs:** scene graphs • semantic graphs • graph matching • cross-modal retrieval  
**Security:** SSRF & tenant isolation • supply-chain attestation (cosign, SBOM, OpenVEX) • adversarial ML

---

### 📊 Selected Numbers

| | |
|---|---|
| Context Gateway | **637 ★**, 47K lines of Go, 1K+ tests, 12 releases |
| Production impact | substantial cost and latency reductions, no quality regression |
| Evaluation | **12 long-context suites** + a 200-task agent benchmark |
| GPU autoscaling | custom CloudWatch metric, beats the AWS built-ins |

---

<p align="left">
  <a href="https://ousso11.github.io"><img src="https://img.shields.io/badge/-Website-181717?style=flat-square&logo=github&logoColor=white" alt="Website"/></a>
  <a href="https://www.linkedin.com/in/oussama-gabouj-775235194"><img src="https://img.shields.io/badge/-LinkedIn-0A66C2?style=flat-square&logo=linkedin&logoColor=white" alt="LinkedIn"/></a>
  <a href="https://scholar.google.com/citations?user=HGKyjnAAAAAJ&hl=fr"><img src="https://img.shields.io/badge/-Google%20Scholar-4285F4?style=flat-square&logo=googlescholar&logoColor=white" alt="Google Scholar"/></a>
  <a href="https://orcid.org/0009-0001-2404-082X"><img src="https://img.shields.io/badge/-ORCID-A6CE39?style=flat-square&logo=orcid&logoColor=white" alt="ORCID"/></a>
  <a href="https://compresr.ai"><img src="https://img.shields.io/badge/-Compresr-000000?style=flat-square" alt="Compresr"/></a>
</p>
