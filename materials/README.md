# Efficient LLM / MLLM Inference — Recommended Reading

This reading list accompanies the **ECCV 2026 tutorial "[Efficient MLLM Inference via Approximate and Exact Computing]([https://einfer-mllm.github.io/Tutorial-ECCV-26](https://einfer-mllm.github.io/Tutorial-ECCV-26/))."** It is a starting point for anyone who wants to prepare before the session, or simply get oriented in the area. No specialization is assumed beyond a basic familiarity with deep learning.

Multimodal large language models (MLLMs) - models that jointly handle text, images, audio, and video - are powerful but expensive to run. The papers below cover the main ways the community makes them cheaper and faster to serve, grouped into the three themes that mirror the tutorial:

1. **Model Compression**: making the model itself smaller (quantization, pruning, distillation).
2. **Token Efficiency:** cutting redundant computation (speculative decoding, visual/video token compression).
3. **System-Level Designs**: serving the model efficiently on real hardware *without changing its outputs* (attention kernels, memory management, disaggregated serving).

The list was compiled by the tutorial speakers and is meant as a curated entry point, not an exhaustive survey. Each entry links to the paper and, where available, the code.

---



## 1. Model Compression



### Quantization


| Paper Title                                                                              | Paper                                     | GitHub                                                  |
| ---------------------------------------------------------------------------------------- | ----------------------------------------- | ------------------------------------------------------- |
| GPTQ: Accurate Post-Training Quantization for Generative Pre-trained Transformers        | [Paper](https://arxiv.org/abs/2210.17323) | [GitHub](https://github.com/IST-DASLab/gptq)            |
| SmoothQuant: Accurate and Efficient Post-Training Quantization for Large Language Models | [Paper](https://arxiv.org/abs/2211.10438) | [GitHub](https://github.com/mit-han-lab/smoothquant)    |
| AWQ: Activation-aware Weight Quantization for LLM Compression and Acceleration           | [Paper](https://arxiv.org/abs/2306.00978) | [GitHub](https://github.com/mit-han-lab/llm-awq)        |
| SpinQuant: LLM Quantization with Learned Rotations                                       | [Paper](https://arxiv.org/abs/2405.16406) | [GitHub](https://github.com/facebookresearch/SpinQuant) |
| GPTVQ: The Blessing of Dimensionality for LLM Quantization                               | [Paper](https://arxiv.org/abs/2402.15319) | [GitHub](https://github.com/Qualcomm-AI-research/gptvq) |




### Pruning


| Paper Title                                                                    | Paper                                     | GitHub                                                  |
| ------------------------------------------------------------------------------ | ----------------------------------------- | ------------------------------------------------------- |
| SparseGPT: Massive Language Models Can Be Accurately Pruned in One-Shot        | [Paper](https://arxiv.org/abs/2301.00774) | [GitHub](https://github.com/IST-DASLab/sparsegpt)       |
| A Simple and Effective Pruning Approach for Large Language Models (Wanda)      | [Paper](https://arxiv.org/abs/2306.11695) | [GitHub](https://github.com/locuslab/wanda)             |
| Sheared LLaMA: Accelerating Language Model Pre-training via Structured Pruning | [Paper](https://arxiv.org/abs/2310.06694) | [GitHub](https://github.com/princeton-nlp/LLM-Shearing) |




### Knowledge Distillation


| Paper Title                                              | Paper                                     | GitHub                                                         |
| -------------------------------------------------------- | ----------------------------------------- | -------------------------------------------------------------- |
| MiniLLM: Knowledge Distillation of Large Language Models | [Paper](https://arxiv.org/abs/2306.08543) | [GitHub](https://github.com/microsoft/LMOps/tree/main/minillm) |


---



## 2. Token Efficiency



### Speculative Decoding


| Paper Title                                                                                              | Paper                                     | GitHub                                              |
| -------------------------------------------------------------------------------------------------------- | ----------------------------------------- | --------------------------------------------------- |
| Fast Inference from Transformers via Speculative Decoding                                                | [Paper](https://arxiv.org/abs/2211.17192) | N/A                                                 |
| Medusa: Simple LLM Inference Acceleration Framework with Multiple Decoding Heads                         | [Paper](https://arxiv.org/abs/2401.10774) | [GitHub](https://github.com/FasterDecoding/Medusa)  |
| MagicDec: Breaking the Latency-Throughput Tradeoff for Long Context Generation with Speculative Decoding | [Paper](https://arxiv.org/abs/2408.11049) | [GitHub](https://github.com/Infini-AI-Lab/MagicDec) |




### Visual / Multimodal Token Compression


| Paper Title                                                                                                               | Paper                                     | GitHub                                                |
| ------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------- | ----------------------------------------------------- |
| An Image is Worth 1/2 Tokens After Layer 2: Plug-and-Play Inference Acceleration for Large Vision-Language Models (FastV) | [Paper](https://arxiv.org/abs/2403.06764) | [GitHub](https://github.com/pkunlp-icler/FastV)       |
| PyramidDrop: Accelerating Your Large Vision-Language Models via Pyramid Visual Redundancy Reduction                       | [Paper](https://arxiv.org/abs/2410.17247) | [GitHub](https://github.com/Cooperx521/PyramidDrop)   |
| VisionZip: Longer is Better but Not Necessary in Vision Language Models                                                   | [Paper](https://arxiv.org/abs/2412.04467) | [GitHub](https://github.com/dvlab-research/VisionZip) |




### Video Token Compression


| Paper Title                                                                                       | Paper                                     | GitHub                                            |
| ------------------------------------------------------------------------------------------------- | ----------------------------------------- | ------------------------------------------------- |
| PruneVid: Visual Token Pruning for Efficient Video Large Language Models                          | [Paper](https://arxiv.org/abs/2412.16117) | [GitHub](https://github.com/Visual-AI/PruneVid)   |
| LongVU: Spatiotemporal Adaptive Compression for Long Video-Language Understanding                 | [Paper](https://arxiv.org/abs/2410.17434) | [GitHub](https://github.com/Vision-CAIR/LongVU)   |
| DyCoke: Dynamic Compression of Tokens for Fast Video Large Language Models                        | [Paper](https://arxiv.org/abs/2411.15024) | [GitHub](https://github.com/KD-TAO/DyCoke)        |
| HoliTom: Holistic Token Merging for Fast Video Large Language Models                              | [Paper](https://arxiv.org/abs/2505.21334) | [GitHub](https://github.com/cokeshao/HoliTom)     |
| LOOK-M: Look-Once Optimization in KV Cache for Efficient Multimodal Long-Context Inference        | [Paper](https://arxiv.org/abs/2406.18139) | [GitHub](https://github.com/SUSTechBruce/LOOK-M)  |
| Video Compression Commander: Plug-and-Play Inference Acceleration for Video Large Language Models | [Paper](https://arxiv.org/abs/2505.14454) | [GitHub](https://github.com/xuyang-liu16/VidCom2) |
| OmniZip: Audio-Guided Dynamic Token Compression for Fast Omnimodal Large Language Models          | [Paper](https://arxiv.org/abs/2511.14582) | [GitHub](https://github.com/KD-TAO/OmniZip)       |
| OmniSIFT: Modality-Asymmetric Token Compression for Efficient Omni-modal Large Language Models    | [Paper](https://arxiv.org/abs/2602.04804) | [GitHub](https://github.com/dingyue772/OmniSIFT)  |




### Survey


| Paper Title                                                                       | Paper                                                                              | GitHub                                                                     |
| --------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- | -------------------------------------------------------------------------- |
| A Survey of Token Compression for Efficient Multimodal Large Language Models      | [Paper](https://arxiv.org/abs/2507.20198)                                          | [GitHub](https://github.com/cokeshao/Awesome-Multimodal-Token-Compression) |
| Towards Efficient Multimodal Large Language Models: A Survey on Token Compression | [Paper](https://www.techrxiv.org/doi/full/10.36227/techrxiv.176823010.07236701/v1) | [GitHub](https://github.com/yaolinli/MLLM-Token-Compression)               |


---



## 3. System-Level Designs

This section merges the compiled reading list with the additional references highlighted in the **System-Level Optimization** talk. The *Notes* column explains, in one line, why each item is relevant.

### Attention Kernels


| Paper Title                                                                      | Venue        | Paper                                     | Code                                                   | Notes                                                                     |
| -------------------------------------------------------------------------------- | ------------ | ----------------------------------------- | ------------------------------------------------------ | ------------------------------------------------------------------------- |
| FlashAttention: Fast and Memory-Efficient Exact Attention with IO-Awareness      | NeurIPS 2022 | [Paper](https://arxiv.org/abs/2205.14135) | [GitHub](https://github.com/Dao-AILab/flash-attention) | IO-aware *exact* attention; a foundational GPU kernel for long sequences. |
| FlashAttention-2: Faster Attention with Better Parallelism and Work Partitioning | 2023         | [Paper](https://arxiv.org/abs/2307.08691) | [GitHub](https://github.com/Dao-AILab/flash-attention) | Better parallelism and work partitioning over FlashAttention.             |




### Serving & Memory Management


| Paper Title                                                                              | Venue                  | Paper                                                             | Code                                                 | Notes                                                                                                 |
| ---------------------------------------------------------------------------------------- | ---------------------- | ----------------------------------------------------------------- | ---------------------------------------------------- | ----------------------------------------------------------------------------------------------------- |
| Orca: A Distributed Serving System for Transformer-Based Generative Models               | OSDI 2022              | [Paper](https://www.usenix.org/conference/osdi22/presentation/yu) | N/A                                                  | Continuous batching — the foundation of modern LLM serving.                                           |
| Efficient Memory Management for Large Language Model Serving with PagedAttention (vLLM)  | SOSP 2023              | [Paper](https://arxiv.org/abs/2309.06180)                         | [GitHub](https://github.com/vllm-project/vllm)       | PagedAttention for efficient KV-cache memory management; a widely used serving engine.                |
| FlexGen: High-Throughput Generative Inference of Large Language Models with a Single GPU | ICML 2023              | [Paper](https://arxiv.org/abs/2303.06865)                         | [GitHub](https://github.com/FMInference/FlexGen)     | High-throughput offloaded inference of large models on a single GPU.                                  |
| SGLang: Efficient Execution of Structured Language Model Programs                        | NeurIPS 2024           | [Paper](https://arxiv.org/abs/2312.07104)                         | [GitHub](https://github.com/sgl-project/sglang)      | RadixAttention and the open-source serving engine the System-Level talk builds on.                    |
| Taming Throughput-Latency Tradeoff in LLM Inference with Sarathi-Serve                   | OSDI 2024              | [Paper](https://arxiv.org/abs/2403.02310)                         | [GitHub](https://github.com/microsoft/sarathi-serve) | Chunked-prefill scheduling to balance throughput and latency.                                         |
| DistServe: Disaggregating Prefill and Decoding for Goodput-Optimized LLM Serving         | OSDI 2024              | [Paper](https://arxiv.org/abs/2401.09670)                         | [GitHub](https://github.com/LLMServe/DistServe)      | Disaggregating prefill and decoding — conceptually close to the talk's stage-level scheduling.        |
| Mooncake: A KVCache-centric Disaggregated Architecture for LLM Serving                   | FAST 2025 (Best Paper) | [Paper](https://arxiv.org/abs/2407.00079)                         | [GitHub](https://github.com/kvcache-ai/Mooncake)     | Production-scale KV-cache-centric disaggregated serving.                                              |
| vLLM-Omni                                                                                | —                      | —                                                                 | [GitHub](https://github.com/vllm-project/vllm-omni)  | Omni-modal serving extension of vLLM.                                                                 |
| SGLang Omni: Serving Multi-Stage Omni Models with Heterogeneous Stage Scheduling         | preprint 2026          | arXiv to follow                                                   | [GitHub](https://github.com/sgl-project/sglang-omni) | Multi-stage omni serving with heterogeneous stage scheduling; core material of the System-Level talk. |




### Representative Omni / Multimodal Models (serving targets & demos)


| Model                                                        | Venue          | Paper                                                                                             | Code                                              | Notes                                                                         |
| ------------------------------------------------------------ | -------------- | ------------------------------------------------------------------------------------------------- | ------------------------------------------------- | ----------------------------------------------------------------------------- |
| Qwen2.5-Omni / Qwen3-Omni Technical Reports                  | 2025           | [Qwen2.5-Omni](https://arxiv.org/abs/2503.20215) · [Qwen3-Omni](https://arxiv.org/abs/2509.17765) | [GitHub](https://github.com/QwenLM/Qwen3-Omni)    | Representative Thinker–Talker omni architectures; also used in the live demo. |
| Moshi: A Speech-Text Foundation Model for Real-Time Dialogue | Kyutai, 2024   | [Paper](https://arxiv.org/abs/2410.00037)                                                         | [GitHub](https://github.com/kyutai-labs/moshi)    | Full-duplex, real-time speech interaction.                                    |
| Higgs Audio                                                  | Boson AI, 2025 | —                                                                                                 | [GitHub](https://github.com/boson-ai/higgs-audio) | Expressive large-scale TTS; day-0 serving support co-launched in SGLang Omni. |
| Qwen2.5-VL Technical Report                                  | 2025           | [Paper](https://arxiv.org/abs/2502.13923)                                                         | [GitHub](https://github.com/QwenLM/Qwen2.5-VL)    | A representative vision-language workload for the ECCV audience.              |


