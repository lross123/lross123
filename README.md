# Luke Ross
**Quantitative Researcher & Low-Latency Developer**

Specialising in institutional-grade risk and pricing infrastructure. My work bridges quantitative research and systems engineering—from simulating non-linear stochastic dynamics to eliminating micro-architectural bottlenecks in the C++20 hot path.

---

## Technical Projects & Research

### 1. [Kernel-Bypass Trading Engine](https://github.com/lross123/Kernel-Bypass-Trading-Engine)
**Stack:** `C++20`, `DPDK`, `AVX-512`, `Linux (HugePages, isolcpus)`

A deterministic, kernel-bypass trading sandbox achieving **~780ns** empirical software latency (including network ingestion overhead).
* **L1-Resident Order Book:** Implemented a zero-allocation local L2 book using unrolled shifting loops (eliminating function-call overhead) and an O(1) Robin Hood backwards-shifting hash map to prevent latency spikes from tombstone compaction.
* **Micro-Architecture Optimisations:** Eliminated SIMD Store-to-Load Forwarding stalls via direct scalar broadcasting (`_mm512_set1_pd`), and utilised non-temporal stores (`_mm_stream_si128`) to prevent L1 cache pollution on telemetry writes.
* **Compute & Memory:** Vectorised Black-Scholes Greeks evaluation using AVX-512 FMA intrinsics, with strict numerical bounding to mitigate 0DTE expiry boundaries. Systematically minimised TLB misses via NUMA-aware, thread-pinned 1GB HugePage Arena Allocators.

### 2. [Deep Hedging under Rough Volatility (Rough Bergomi)](https://github.com/lross123/Deep-Hedging)
**Stack:** `Python`, `JAX (XLA)`, `Equinox`, `PyTorch`

A differentiable simulator for derivatives hedging in non-Markovian environments, focusing on rough volatility regimes (Hurst parameter $H < 0.1$).
* **Implementation:** Architected a hardware-accelerated JAX/XLA engine processing 200,000+ parallel Monte Carlo paths with massive throughput efficiency.
* **Optimisation:** Leveraged stochastic calculus and auto-differentiation to minimise 95% CVaR across complex, non-linear derivative portfolios.

---

## Professional Experience

**Quantitative Data Scientist** @ JWA CNC Precision *(Dec 2025 - Present)*
* **Stochastic Modelling:** Developed a multidimensional volatility forecasting engine using Ornstein-Uhlenbeck processes to model mean-reversion across LME commodity spot prices, automating systematic pricing risk for an industrial portfolio.
* **Signal Extraction:** Architected robust data ingestion pipelines to sanitise 50,000+ daily multi-modal market data points. Fine-tuned localised LLMs (Llama-3 QLoRA) to extract quantitative pricing signals from unstructured, OTC RFQ data.

**Quantitative Researcher** @ QUT (Queensland University of Technology) *(Feb 2025 - Jun 2025)*
* **Stochastic Simulation:** Architected spatiotemporal PDE models (Reaction-Diffusion) to simulate non-linear dynamics, generating 200k+ synthetic trajectories via high-performance Monte Carlo methods.
* **Numerical Optimisation:** Solved inverse problems using Finite Difference Methods (FDM) for parameter estimation, coupling measurement error models with strict mechanistic constraints.
* **Statistical Validation:** Co-engineered and stress-tested stochastic solvers alongside Oxford University researchers, ensuring rigorous model identifiability and out-of-sample statistical robustness.

---

## Core Stack & Tooling

* **Mathematics:** Stochastic Calculus (Itô, SDEs), Spatiotemporal PDEs, Rough Volatility, Convex Optimisation.
* **Systems Engineering:** C++20/23, DPDK (Kernel Bypass), Lock-free IPC, AVX-512 Intrinsics, Cache Topology.
* **Quant & Data:** JAX, XLA, KDB+/q, SQL.
* **Infrastructure:** Bazel, CMake, Docker, Linux Performance Tooling (Perf, GDB).

---
[LinkedIn](https://www.linkedin.com/in/lukeross18/) | [Portfolio](https://lukemorganross.com) | [Email](mailto:luke.ross200121@gmail.com)
