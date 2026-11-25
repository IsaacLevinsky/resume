# Isaac Levinsky

**AI Inference Engineer** | GPU performance, model serving and numerical validation

Tampa Bay, FL | Remote (US) | Available now, full-time or contract W-2 | No client commitments

[admin@mcmlv1.com](mailto:admin@mcmlv1.com) | [linkedin.com/in/isaaclevinsky](https://www.linkedin.com/in/isaaclevinsky/) | [github.com/IsaacLevinsky](https://github.com/IsaacLevinsky)

Public reports: [mcmlv1.com/inference-120b](https://mcmlv1.com/inference-120b) | [mcmlv1.com/h100-serving-engines](https://mcmlv1.com/h100-serving-engines)

**Resume (PDF): [Isaac_Levinsky_Resume.pdf](Isaac_Levinsky_Resume.pdf)**

## Profile

Build AI systems end to end, from first design to production, often solo: a GPT-OSS-120B runtime for a two-GPU workstation with 24 GB of GPU memory, then the same model on an H100 across vLLM, SGLang and TensorRT-LLM.

## Experience

### AI Inference Engineer (Independent)
MCMLV1 LLC | January 2026 – Present | Remote

- **Workstation runtime.** Built a GPT-OSS-120B runtime (65 GB mixture-of-experts) across a 16 GB GP100, an 8 GB RTX 4000, CPU and system RAM. Against tuned llama.cpp and ik_llama.cpp on the same workstation, it won all 18 speed comparisons at six prompt lengths (336–65,280 tokens): prompt reading up to 32% faster, answer generation 15–25% faster and complete answers 6–18% sooner than the best rival.
- **Numerical validation.** Matched all 2,113 held-out reference next-token choices from the original weights in FP32/FP64; ik_llama.cpp missed 47 and llama.cpp 53. Built per-phase profilers and GPU bandwidth microbenchmarks to separate speed gains from output changes.
- **Custom GPU kernels.** Built GPT-OSS-20B runtimes with their own GPU kernels. RTX 3060: decode 23–27% faster than a matched llama.cpp CUDA build through 8K context, about 58x lower mean KL from an FP64 reference; previously deployed behind MerlinChat. GP100: 200.6 vs 74.7 tokens/s single-conversation generation; it serves MerlinChat today.
- **Cloud serving cost.** Built a Rust benchmark harness and budget-capped runner to compare vLLM, SGLang and TensorRT-LLM serving GPT-OSS-120B on one H100. FP8 KV cache cut cost per output token up to 37% on vLLM ($0.72 to $0.45 per million) by fitting 64 users instead of 32 in the KV pool, and about 35% on SGLang (16 to 32 users), with no detectable MLPerf v6.0 accuracy change (resolution about 3 points).
- **Repeatability.** Under a 24-client load, one temperature-0 request sent 1,000 times gave 3 distinct 512-token outputs on SGLang and 82 on vLLM at defaults (110 in batch-invariant mode). In vLLM batch-invariant mode, switching from FlashAttention 3 to Triton attention made 200 of 200 outputs match the solo run; three other single changes left 14 distinct in 200 each.
- **GPU profiling.** In Nsight Systems, a warmed-up vLLM server at 16 users had eight idle gaps totaling 5.95 seconds in a 12-second capture, each ending in a GPU module load: consistent with just-in-time kernel compilation at batch sizes not seen in warm-up.
- **Upstream contribution.** Traced a calibration gap (SGLang 12 of 18 vs 17 of 18 for TensorRT-LLM) to answers cut off near 5,000 tokens by SGLang’s 5,209-token KV pool, and submitted SGLang PR #52026 (open; addresses issue #50443), which warns when the KV pool lowers an explicit output limit: [github.com/sgl-project/sglang/pull/52026](https://github.com/sgl-project/sglang/pull/52026)
- **Quantization.** Quantized Google’s BF16 Gemma 4 26B-A4B into a 15.4 GB 4-bit file for the GP100: mean KL divergence 0.025 vs 0.156 for Google’s QAT Q4_0 release on llama.cpp, at 117 vs 58 tokens/s in single-chat generation.
- **Apple Silicon.** Built a Rust/Metal runtime and a 13.1 GB mixed-precision Gemma 4 26B-A4B model on an Apple M5. Prompt processing was 20–35% faster than mlx_lm across tested lengths from 1K to 64K.
- **Mobile inference.** Wrote a dependency-free Rust runtime with ARM64 SDOT assembly for 8-bit Qwen3-0.6B. On a midrange Android phone, reduced time to first text on a 359-token prompt from 21.7 to 2.15 seconds while keeping optimizations bit-identical to a frozen reference.
- **Serving and distribution.** Ran a systemd-managed GPT-OSS-120B streaming API with rollback and build-and-test checks for CodeLoop and a job-matching tool in November 2026. Shipped 15 Android apps on Google Play and software through the Amazon Appstore, Microsoft Store and Mac App Store.

### Independent Software Engineer
Self-directed systems and ML projects | 2021 – 2025 | Remote

- **GPU data processing.** Built a C++/CUDA engine for data cleaning and deduplication. It processed about 901,000 rows per second on a measured workload, with GPU results checked against a CPU implementation.

## Technical skills

- **Languages and hardware.** Rust, C/C++, Python, CUDA, Metal, ARM64 NEON/SDOT
- **Inference and measurement.** vLLM, SGLang, TensorRT-LLM, Nsight Systems, MLPerf Inference v6.0 accuracy method, KV caching, prefill/decode profiling, FP64 references, quantization
- **Deployment.** Linux, Docker, Kubernetes, Helm, systemd, HAProxy, Prometheus, Grafana, DCGM

## Education

- Doctorate, Clinical Psychology, Florida Institute of Technology
- Master of Science, Psychology, Florida Institute of Technology
- Bachelor of Arts, Psychology, University of Delaware
