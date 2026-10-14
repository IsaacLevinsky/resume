# Isaac Levinsky

**Software Engineer | Rust, AI Systems, GPU Performance & Cloud Infrastructure**

ilevinsky36@gmail.com | 386-576-6616 | [github.com/IsaacLevinsky](https://github.com/IsaacLevinsky) | [mcmlv1.com](https://mcmlv1.com)

Greater Tampa Bay Area, FL | Remote US | Full-time W-2 or contract

**[Download the two-page resume (PDF)](Isaac_Levinsky_Software_Engineer_Rust_AI_GPU_Resume.pdf)**

## Summary

Software engineer building AI systems, shared Rust engines, GPU inference software, cloud services, developer tools, and commercial mobile and desktop products. Owns architecture, implementation, testing, deployment, and production operation. Experience spans model training and evaluation, AI agents, GPU performance engineering, and shipped production software, with measured inference improvements and FP64 numerical validation.

## Technical skills

**Languages:** Rust, Python, C++/CUDA, TypeScript/JavaScript, C#, Kotlin, Swift, SQL, Bash, Go

**Cloud & infrastructure:** Docker, Linux, HAProxy, Cloudflare Pages/Tunnel/R2, Google Cloud Storage, Firebase, AWS, Stripe

**AI & data:** PyTorch, Hugging Face, ONNX/ONNX Runtime, Burn, LiteRT, MLX, CUDA, llama.cpp, RAG, embeddings, MCP/tool calling, LangChain/LangGraph, SQLite/WAL, FTS5/BM25

**Applications:** Native Android, .NET, Swift, Tauri, React; cross-platform release and deployment

## Experience

### Founder & Software Engineer

**MCMLV1 LLC — Professional Software Solutions**

Jan 2026–Present | Greater Tampa Bay Area | Remote

Own architecture, implementation, testing, release, and production operation across AI infrastructure, web services, native applications, and shared software engines.

#### Production systems, cloud services & commercial software

- **Production AI infrastructure:** Built and operated MerlinChat, a sales/support chatbot using HAProxy to route concurrent users across multiple GPU workstations running local LLMs.
- **Model evaluation:** Ran and evaluated 100+ open-source LLMs across local and self-hosted inference environments, spanning model tiers from 8B through 120B-class systems.
- **Cloud services & payments:** Deployed web tools, AI chatbot demonstrations, and Stripe-enabled product infrastructure on Cloudflare Pages, Tunnel, and R2; owned integration, deployment, and maintenance.
- **Commercial releases:** Shipped [15 Android apps on Google Play](https://play.google.com/store/apps/developer?id=MCMLV1+LLC) and [4 on Amazon Appstore](https://www.amazon.com/s?i=mobile-apps&rh=p_4%3AMCMLV1%2BLLC&search-type=ss), [Talk Together on Samsung Galaxy Store](https://galaxystore.samsung.com/detail/org.mcmlv1.talktogether.samsung), [QR Code Link Me on Microsoft Store](https://apps.microsoft.com/detail/9ngvp6bj0dvl?hl=en-US&gl=US), and macOS software.
- **Product adoption:** [Private Dictation: Offline AI](https://play.google.com/store/apps/details?id=org.mcmlv1.voicetotext) recorded 3.27K device acquisitions and 936 active installs in six months; [QR Code Generator Offline](https://play.google.com/store/apps/details?id=org.mcmlv1.qrcodegenerator) recorded 1.28K acquisitions and 381 active installs.
- **Cross-platform engineering:** Built shared Rust engines embedded in native Kotlin/C# Android shells and Swift macOS interfaces; developed Windows and Linux desktop applications on the same shared-core architecture.

#### GPU inference performance & numerical validation

- **Measured inference gains:** Built a custom gpt-oss-20b inference engine on RTX 3060 12 GB; achieved 127.3 vs 92.8 tokens/sec (+37.2%) at ~1k context against GPU-optimized llama.cpp b11609, and 2,898 vs 2,442 tokens/sec (+18.7%) for prompt processing.
- **Controlled evaluation:** Used the same GPU, model weights, and token inputs; generation measured 64 teacher-forced decisions, with medians of five rounds after warm-up. Matched-document evaluation also covered ~4k and ~8k contexts.
- **Numerical fidelity:** In a separate 32-prompt CPU FP64 reference suite, achieved 2,046/2,048 top-1 matches and 57.6× lower mean KL divergence than a pinned llama.cpp baseline.
- **Hardware breadth:** Developed custom inference software for Pascal GP100 and Ampere RTX 3060 GPUs; current work includes custom inference on a MacBook Pro M5 with 32 GB memory.

### Independent Software Engineer

**Self-Directed Engineering Projects | Self-employed**

Jan 2021–Dec 2025 | Tampa, FL | Remote

Engineering and R&D in systems software, machine learning, GPU computing, and Android development; established foundations later commercialized through MCMLV1 LLC.

- **Model training systems:** Designed and implemented RustMind using Rust and Burn, covering model architecture, byte-level BPE tokenization, corpus processing, train/validation design, and GPU training.
- **ML debugging:** Investigated model capacity across a parameter ladder; diagnosed generation collapse associated with validation and data-pipeline problems, then redesigned corpus processing around document-aware chunks and explicit data splits.
- **Developer tooling:** Built LookingGlass, a zero-dependency Rust workspace-analysis engine for project classification, language detection, dependency/reference graphing, and automated audits; processed 3,441 files in ~47 ms in a measured local run.
- **GPU data processing:** Built Orion (C++/CUDA) for data cleaning and deduplication at ~901,000 rows/sec on a measured workload, with CPU/GPU cross-validation.
- **Numerical reliability:** Investigated precision-related instability on Pascal GPUs and developed hardware-aware training and inference workflows; established CPU/GPU validation practices for subsequent products.

## Selected projects

### CodeLoop — Autonomous AI Engineering System

Active development | Rust, Swift, Tauri, MLX, llama.cpp

- **Agentic software generation:** Built an autonomous coding system that generates, builds, and analyzes complete software programs, with built-in data-science analysis and visualization; shared Rust core with a Swift macOS interface and a Tauri frontend for Windows and Linux.
- **Model serving:** Runs local inference through MLX on Apple Silicon, including self-quantized models, and llama.cpp on Windows/Linux; can route larger-model work to LAN-hosted GPU workstation endpoints.

### RustMind Mini Embed Base — Public ML Pipeline

[github.com/IsaacLevinsky/rustmind-mini-embed-base](https://github.com/IsaacLevinsky/rustmind-mini-embed-base)

- **Training & deployment:** Built and trained a ~21M-parameter encoder with Python, PyTorch, and Hugging Face; implemented tokenizer training, masked-language-model pretraining, ONNX export, INT8 quantization, and local embedding/search demonstrations.
- **Reproducibility:** Published runnable source and proof reports; built a filtered corpus pipeline and separated corpus/training requirements, using direct ONNX export to simplify installation and packaging.

### Native Applications & Offline Product Engineering

- **On-device AI:** Shipped production LiteRT inference in Private Dictation using Moonshine, alongside Whisper-based dictation, multilingual translation, and ML Kit OCR/text-recognition workflows running entirely on user devices.
- **Business software:** Built estimating and invoicing applications with signatures, photo capture, templates, SQLite/WAL storage, and ZIP backup/restore; shipped document, PDF-processing, and audit-journaling utilities.

## Education

University of Delaware | Bachelor of Arts
