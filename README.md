# 🌌 Quantum-NTN-Scheduler: Hybrid Quantum Optimization for Dynamic Satellite Routing

**QASCOM Lab Initiative** | **[Associated Publication: Challenges in Applying Variational Quantum Algorithms to Dynamic Satellite Network Routing (arXiv:2508.04288)]**

[![DOI Badge]](https://doi.org/10.48550/ARXIV.2508.04288)
[![GitHub Stars]](https://github.com/QASCOM-Lab/Quantum-NTN-Scheduler/stargazers)
[![License: MIT]](https://opensource.org/licenses/MIT)
[![Docker Build]](https://hub.docker.com/r/qascom/ntn-scheduler)

---

### 🚀 Overview

The `Quantum-NTN-Scheduler` repository provides the foundational simulation environment and core algorithms for applying **Hybrid Quantum-Classical Optimization** to solve critical resource management challenges within dynamic Non-Terrestrial Networks (NTN), specifically focusing on Low Earth Orbit (LEO) satellite constellations.

We specialize in modeling complex real-world network constraints—such as **time-varying inter-satellite links (ISLs)** and **dynamic bandwidth limitations**—into a mathematical framework suitable for quantum computation (QUBO). Our goal is to demonstrate how Variational Quantum Algorithms (VQA) and Quantum Approximate Optimization Algorithms (QAOA) can provide near-optimal scheduling solutions faster and more reliably than traditional classical methods.

### 💡 Key Features & Technical Contributions (PoC Focus)

1.  **QUBO Formulation Engine:** Provides robust tools to map dynamic shortest path problems, minimum spanning tree problems, and resource allocation constraints onto the **Quadratic Unconstrained Binary Optimization (QUBO)** format, essential for quantum solvers.
2.  **Hybrid Solver Framework:** Implements VQA/QAOA circuits using **Qiskit** and **PennyLane**, integrated with classical optimization layers (e.g., COBYLA, L-BFGS-B) for robust training on NISQ (Noisy Intermediate-Scale Quantum) devices.
3.  **Dynamic LEO Topology Simulator:** Integrated with `Poliastro` and `Skyfield` libraries to accurately generate time-variant LEO satellite orbits, compute dynamic Inter-Satellite Link (ISL) schedules, and output the time-sliced network graph data required for optimization input.
4.  **Performance Benchmarking Suite:** A comprehensive set of scripts for running rigorous comparative tests, measuring the **Solution Quality (Optimality Gap)** and **Runtime Complexity** for:
    *   Quantum Solvers (VQA/QAOA)
    *   Classic Exact Solvers (CPLEX/Gurobi via wrappers)
    *   Classical Heuristics (Dijkstra, Genetic Algorithms - GA)

### 📈 Business & Research Impact Showcase

This repository serves as a crucial Proof-of-Concept for industry and academic partners by providing:

*   **Ultra-Low Latency Routing Validation:** Empirical evidence demonstrating the speed and efficiency advantage of quantum-inspired algorithms in calculating dynamic routes in highly mobile, large-scale networks (a critical bottleneck for 6G NTN architectures).
*   **Feasibility Assessment:** A structured environment for telecommunications entities to benchmark the potential performance gain of quantum solutions against their existing classical scheduling systems.
*   **Scientific Rigor:** Full transparency and reproducibility for all published experimental results.

### ⚙️ Setup and Reproducibility (Dockerized)

To guarantee full reproducibility across different environments (local simulators or cloud platforms), the entire project is containerized.

**Prerequisites:** Docker and Docker Compose must be installed.

#### Step 1: Clone the Repository

```bash
git clone https://github.com/QASCOM-Lab/Quantum-NTN-Scheduler.git
cd Quantum-NTN-Scheduler
```

#### Step 2: Build and Run the Environment

We utilize the base environment from our `NTN-Environment-Docker` repository to ensure all dependencies (Python, Qiskit, Poliastro) are correctly configured.

```bash
# Build the Docker image
docker build -t qascom-ntn-scheduler:latest .

# Run a sample comparative simulation test (e.g., VQA vs. Dijkstra on a 50-satellite graph)
docker run qascom-ntn-scheduler:latest python src/tests/run_comparison_test.py --num_satellites 50 --alg VQA
```

#### Step 3: View and Visualize Results

Simulation outputs (JSON logs, convergence plots, and network graph visualizations) will be automatically saved in the `./results` directory.

### 🗺️ Project Roadmap

| Phase | Goal | Status |
| :--- | :--- | :--- |
| **V1.0 (Current)** | Implementation of QUBO formulation for Shortest Path. Benchmarking VQA (QAOA) vs. Dijkstra on static and small dynamic LEO graphs. | **Complete** |
| **V1.1 (Q4 2025)** | Integration of multi-constraint optimization (bandwidth, energy). Refinement of the VQA ansatz design for better convergence rates. | *In Progress* |
| **V2.0 (H1 2026)** | Development of a **Hybrid Quantum-Classical Scheduling** API. Integration support for D-Wave and IonQ backends. Release of tutorial notebooks. | *Planned* |

### 📚 Associated Publications

This repository is the official code base for experiments conducted in:

*   **Challenges in Applying Variational Quantum Algorithms to Dynamic Satellite Network Routing**
    *   *P. H. Do, T. D. Le*
*   *Further papers on Quantum Resource Allocation will be added here upon acceptance.*

### 🤝 Contribution

We welcome external contributions from researchers and developers focused on quantum algorithms, aerospace simulation, and network optimization. Please see the `CONTRIBUTING.md` file for details.
