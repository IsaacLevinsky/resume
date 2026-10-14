# Isaac Levinsky

**Software Engineer | Rust, AI Systems, GPU Performance & Cloud Infrastructure**

I build AI systems, shared Rust engines, GPU inference software, cloud services, developer tools, and commercial mobile and desktop products. I own architecture, implementation, testing, deployment, and production operation, choosing local, cloud, or hybrid systems to fit the problem.

## Hiring

**[Download my current two-page resume (PDF)](Isaac_Levinsky_Software_Engineer_Rust_AI_GPU_Resume.pdf)**

Greater Tampa Bay Area, FL | Remote US | Full-time W-2 or contract

[ilevinsky36@gmail.com](mailto:ilevinsky36@gmail.com) | 386-576-6616 | [github.com/IsaacLevinsky](https://github.com/IsaacLevinsky) | [mcmlv1.com](https://mcmlv1.com)

## GPU inference engineering

Develop proprietary GPU inference software focused on improving model-serving speed and efficiency. Experience includes **CUDA and GPU kernel work**, hardware-aware optimization, benchmarking, and numerical validation across NVIDIA GPUs, with ongoing work on Apple Silicon.

Evaluate performance through controlled comparisons and CPU/GPU validation, then connect inference work to production software and deployment.

**MerlinChat**, the sales and support chatbot on [mcmlv1.com](https://mcmlv1.com), demonstrates production AI infrastructure using self-hosted models and HAProxy routing across GPU workstations.

Implementation details and detailed research material remain private. Selected technical details can be discussed under NDA.

## Rust systems

### Shared engines across native platforms

Build product logic once in Rust and embed it through FFI bindings in native Kotlin/C# Android shells, Swift macOS interfaces, and Windows/Linux desktop applications. One shared core owns product behavior, so fixes can be carried across platforms.

**QR Code Link Me** uses a shared Rust core behind Windows and macOS interfaces. **DocEngine** powers MCMLV1 Viewer. Platform work includes Rust FFI/UniFFI, native Android, .NET, Swift, and Tauri.

### CodeLoop — autonomous AI engineering system

Active development: shared Rust core with a Swift macOS interface and a Tauri frontend for Windows and Linux.

- Generates, builds, and analyzes software programs, with built-in data-science analysis and visualization.
- Runs local inference through MLX on Apple Silicon, including self-quantized models, and llama.cpp on Windows/Linux.
- Can route larger-model work to LAN-hosted GPU workstation endpoints; supports offline and air-gapped operation.

### LookingGlass — zero-dependency workspace engine

Compiled Rust workspace analysis in a single binary: project classification, language detection, dependency/reference graphing, and automated audit reports.

- Processed **3,441 files in approximately 47 ms** in a measured local run.
- Powers RustMind's corpus export, with **zero false positives in the evaluated corpus-export checks across 30+ repositories**.

### Orion — GPU data processing

Built C++/CUDA software for data cleaning and deduplication, with CPU/GPU cross-validation. A measured workload processed **1.15M rows in 1.276 seconds**, approximately **901,000 rows/sec**.

## AI / ML

### RustMind — training systems in Rust and Burn

Designed the model architecture, byte-level BPE tokenizer, corpus-processing pipeline, train/validation design, and GPU training path in Rust using Burn.

- Explored a **21M→125M parameter ladder**, including generative training at 125M and a 72M encoder-decoder; trained a 21M encoder and integrated it into shipped software.
- Investigated generation collapse alongside validation-split and templated-data problems, then redesigned corpus processing around document-aware chunks and explicit train/validation separation.
- Used **Rust generics over CUDA and CPU backends**, carrying a shared codebase from GPU training to CPU inference.
- Investigated FP16/BF16 instability on Pascal GPUs and established hardware-aware training and CPU/GPU validation practices.

The Rust/Burn training stack is separate from the public Python/PyTorch pipeline below.

### RustMind Mini Embed Base — public ML pipeline

**[Source and proof reports](https://github.com/IsaacLevinsky/rustmind-mini-embed-base)** — MIT

Built and trained an approximately 21M-parameter encoder using Python, PyTorch, and Hugging Face. The published pipeline covers tokenizer training, masked-language-model pretraining, direct ONNX export, INT8 quantization, and local embedding/search demonstrations.

Published runnable source, a reproducible CPU-only proof run, and a base checkpoint. Built a filtered corpus pipeline and separated corpus and training requirements to simplify installation and packaging.

### Private inference assistant — Rust gateway and Android client

Built a private LLM chat system with a Rust gateway on a GPU workstation and a Kotlin/Jetpack Compose Android client over a Rust core handling streaming and on-device history.

- **WireGuard-only transport**, with no public endpoint and inference bound to localhost.
- Retrieval over a **SQLite FTS5/BM25 knowledge cache**.
- Prompts ordered for **llama.cpp prefix-cache reuse** during long conversations.

### Bosun and model evaluation

Built model routing across **8B–120B tiers using llama-swap**. Ran and evaluated **100+ open-source LLMs** across local and self-hosted environments. Earlier on-device Android LLM work used LiteRT-LM and measured sub-two-second responses in the tested setup.

### Production on-device AI

Shipped **LiteRT inference using Moonshine in Private Dictation**, alongside Whisper-based dictation, multilingual translation, and ML Kit OCR/text-recognition workflows running on user devices. The Moonshine dictation deployment is distinct from the earlier Android LLM response measurement.

## Shipped products

Founded **MCMLV1 LLC — Professional Software Solutions** in January 2026. Own architecture, implementation, testing, release, and production operation across native applications, shared software engines, web services, and AI infrastructure.

- **[15 Android apps on Google Play](https://play.google.com/store/apps/developer?id=MCMLV1+LLC)** and **[4 on Amazon Appstore](https://www.amazon.com/s?i=mobile-apps&rh=p_4%3AMCMLV1%2BLLC&search-type=ss)**.
- **[Talk Together: In-Person Offline AI Translation](https://galaxystore.samsung.com/detail/org.mcmlv1.talktogether.samsung)** on Samsung Galaxy Store.
- **[QR Code Link Me](https://apps.microsoft.com/detail/9ngvp6bj0dvl?hl=en-US&gl=US)** on Microsoft Store, plus macOS software.
- **[Private Dictation: Offline AI](https://play.google.com/store/apps/details?id=org.mcmlv1.voicetotext)** recorded **3.27K device acquisitions and 936 active installs in six months**.
- **[QR Code Generator Offline](https://play.google.com/store/apps/details?id=org.mcmlv1.qrcodegenerator)** recorded **1.28K acquisitions and 381 active installs**.

Adoption figures are the recorded snapshots carried in the current resume, rather than live store statistics.

Built estimating and invoicing applications with signatures, photo capture, templates, SQLite/WAL storage, and ZIP backup/restore, plus document/PDF-processing and audit-journaling utilities. Offline-first product work emphasizes on-device processing and no ads, accounts, or tracking.

## Cloud / infrastructure

Deployed web tools, chatbot demonstrations, and Stripe-enabled product infrastructure on **Cloudflare Pages, Tunnel, and R2**, owning integration, deployment, and maintenance. Operated Linux services and HAProxy routing for self-hosted inference.

**Languages:** Rust, Python, C++/CUDA, TypeScript/JavaScript, C#, Kotlin, Swift, SQL, Bash, Go

**Infrastructure and services:** Docker, Linux/systemd, HAProxy, Cloudflare Pages/Tunnel/R2, Google Cloud Storage, Firebase, AWS, WireGuard, Stripe, SQLite/WAL, FTS5/BM25, Git

**AI and data tooling:** PyTorch, Hugging Face, ONNX/ONNX Runtime, Burn, LiteRT/LiteRT-LM, MLX, CUDA, llama.cpp/llama-swap, RAG, embeddings, MCP/tool calling, LangChain/LangGraph, ML Kit, Whisper, Moonshine

## About / availability

Independent software engineering and R&D from January 2021 through December 2025 established the Rust, CUDA, Android, and ML foundations later commercialized through MCMLV1 LLC.

**Education:** University of Delaware | Bachelor of Arts

**Languages:** English — native | French — professional working proficiency.

**Availability:** Remote US | Full-time W-2 or contract | Async-preferred

I work best with end-to-end ownership, clear objectives, and measurable outcomes: design, build, test, measure, and iterate.

**Company verification:** [MCMLV1 LLC — Florida Division of Corporations (Sunbiz)](https://search.sunbiz.org/Inquiry/CorporationSearch/SearchResultDetail?inquirytype=EntityName&directionType=Initial&searchNameOrder=MCMLV1%20L260000333020&aggregateId=flal-l26000033302-8d84d1c8-c45b-4a36-a250-98ad0f189713&searchTerm=mcmlv1&listNameOrder=MCMLV1%20L260000333020)
