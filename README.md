# ECCV 2026 Tutorial: Efficient MLLM Inference via Approximate and Exact Computing

This repository hosts the official webpage and shared materials for the ECCV 2026 tutorial **Efficient MLLM Inference via Approximate and Exact Computing**.

**Tutorial webpage:** **[https://einfer-mllm.github.io/Tutorial-ECCV-26](https://einfer-mllm.github.io/Tutorial-ECCV-26/)**

## Talk Materials

- **Exact Computing: System-Level Designs** — [Serving Omni-Modal Models at Scale: Systems Design and Lessons from SGLang Omni (PDF)](materials/SGLang%20Omni.pptx.pdf) — Chenyang Zhao
- **Approximate Computing: Token Efficiency** — [LLaVA-OneVision-2: Understanding the Visual World Across Space and Time (PDF)](materials/llava-ov.pdf) — Bo Li
- **Approximate Computing: Model Compression** — [The Trinity of MLLM Compression — Advanced PTQ, Pruning, and Context Compression (PDF)](materials/sathya-trinity-model-compression-eccv-2026-tutorial.pdf) — Sathya Narayanan Ravi

## Overview

Multimodal large language models have advanced rapidly, but their inference cost remains a major barrier for cloud serving and edge deployment. The cost comes from massive model parameters, long multimodal contexts, attention complexity, and memory-bound execution on modern hardware. This tutorial frames efficient MLLM inference through two complementary lenses: approximated computing, which reduces model and data redundancy while preserving practical utility, and exact computing, which accelerates inference through system and hardware optimization without changing model outputs.

## Organizers

The tutorial is organized by researchers from Westlake University, Google, UC Merced, NVIDIA, University of Wisconsin-Madison, Google DeepMind, Apple, Microsoft AI, and University of Central Florida.

For the full organizer list, affiliations, and homepage links, please see the tutorial webpage.

## Tutorial Information

- **Conference:** ECCV 2026
- **Date:** September 8, 2026
- **Time:** Morning session
- **Location:** Malmö, Sweden
- **Room:** TBD

## Materials

Tutorial materials are available in this repository and will continue to be updated.

- Talk slides: see [Talk Materials](#talk-materials)
- Recommended reading: [Efficient LLM / MLLM Inference](materials/README.md)
- Code and demos: TBD
- Additional resources: TBD

## Contact

For questions about the tutorial or materials, please contact:

- Huan Wang: [wanghuan@westlake.edu.cn](mailto:wanghuan@westlake.edu.cn)
- Keda Tao: [taokeda@westlake.edu.cn](mailto:taokeda@westlake.edu.cn)
- ENCODE LAB: [https://westlake-encode-lab.github.io/](https://westlake-encode-lab.github.io/)
