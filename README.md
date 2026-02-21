# Luke Ross
**Quantitative Researcher & Developer**

Bridging the gap between non-linear stochastic mathematics and ultra-low-latency execution architecture. My work focuses on building institutional-grade risk and pricing infrastructure, from deriving continuous-time dynamics to optimising the C++20 hot path.

---

## Technical Projects & Research

### 1. [Sub-Microsecond Limit Order Book & Matching Engine](LINK_TO_YOUR_REPO)
**Stack:** `C++20`, `DPDK`, `AVX-512`, `Linux (HugePages, CPU Isolation)`

A deterministic, kernel-bypass matching engine achieving **~780ns** tick-to-trade latency. 
* **Architecture:** Implemented lock-free Single-Producer Single-Consumer (SPSC) ring buffers. Eliminated false sharing via explicit cache-line padding (`alignas(64)`).
* **Memory Management:** Designed custom Arena Allocators backed by 1GB HugePages to systematically minimise TLB misses. 
* **Compute:** Vectorised Black-Scholes Greeks evaluation using AVX-512 Fused Multiply-Add (FMA) intrinsics for maximum instruction throughput.
* *Note: Repository includes rigorous `Google Benchmark` teardowns, `perf` stat analysis, and flame graphs validating L1/L2 cache hit rates.*

### 2. [Deep Hedging under Rough Volatility (Rough Bergomi)](LINK_TO_YOUR_REPO)
**Stack:** `Python`, `JAX (XLA)`, `Equinox`, `PyTorch`

A differentiable physics engine for derivatives hedging in non-Markovian environments, specifically focusing on regimes where the Hurst parameter is H < 0.1.
* **Implementation:** Architected a JAX/XLA-compiled simulator executing 200,000+ parallel Monte Carlo paths at microsecond latencies.
* **Optimisation:** Leveraged hardware-accelerated vectorisation and stochastic calculus to minimise 95% CVaR across complex, non-linear derivative portfolios.

---

## Professional Experience

**Quantitative Data Scientist** @ JWA CNC Precision *(Dec 2025 - Present)*
* **Systematic Risk & Stochastic Modelling:** Developed a volatility forecasting engine using Ornstein-Uhlenbeck processes to model mean-reversion in LME commodity spot prices, managing algorithmic pricing signals for a **£5M+ physical asset portfolio**.
* **Alpha Signal Extraction:** Fine-tuned localised LLMs (Llama-3-8B) via QLoRA on unstructured RFQ data to extract nuanced pricing signals invisible to standard quantitative analysis.
* **High-Throughput ETL:** Built automated, zero-loss data ingestion agents in Python/SQL to sanitise multi-modal market feeds for real-time risk reporting.

**Quantitative Researcher** @ QUT (Queensland University of Technology) *(Feb 2025 - Jun 2025)*
* **Stochastic Simulation:** Architected spatiotemporal PDE models (Reaction-Diffusion) to simulate complex non-linear dynamics, generating 200k+ synthetic trajectories via heavy-compute Monte Carlo methods.
* **Numerical Optimisation:** Solved complex inverse problems using Finite Difference Methods (FDM) for parameter estimation; mathematically coupled measurement error models with strict mechanistic constraints.
* **Statistical Validation:** Co-engineered and stress-tested stochastic solvers alongside Oxford researchers, ensuring rigorous model identifiability and out-of-sample statistical robustness.

---

## Core Stack & Tooling

* **Mathematics:** Stochastic Calculus (Itô, SDEs), Spatiotemporal PDEs, Rough Volatility, Convex Optimisation.
* **Systems Engineering:** C++20/23, DPDK (Kernel Bypass), Lock-free IPC, AVX-512 Intrinsics.
* **Quant & Data:** JAX, XLA, KDB+/q, SQL.
* **Infrastructure:** Bazel, CMake, Docker, Linux Performance Tooling (Perf, GDB).

---
[LinkedIn](https://www.linkedin.com/in/lukeross18/) | [Portfolio](https://lukemorganross.com) | [Email](mailto:luke.ross200121@gmail.com)
