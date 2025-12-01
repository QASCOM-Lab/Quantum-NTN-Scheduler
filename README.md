# 🌌 Quantum-NTN-Scheduler: Hybrid Quantum Optimization for Dynamic Satellite Routing

**QASCOM Lab Initiative** | **[Associated Publication: Challenges in Applying Variational Quantum Algorithms to Dynamic Satellite Network Routing (arXiv:2508.04288)]**

[![DOI Badge]](https://doi.org/10.48550/ARXIV.2508.04288)
[![GitHub Stars]](https://github.com/QASCOM-Lab/Quantum-NTN-Scheduler/stargazers)
[![License: MIT]](https://opensource.org/licenses/MIT)
[![Docker Build]](https://hub.docker.com/r/qascom/ntn-scheduler)

---

### 🚀 Overview

The `Quantum-NTN-Scheduler` repository provides the foundational simulation environment and core algorithms for applying **Hybrid Quantum-Classical Optimization** to solve critical resource management challenges within dynamic Non-Terrestrial Networks (NTN), specifically focusing on Low Earth Orbit (LEO) satellite constellations.

We specialize in modeling real-world constraints—such như **thay đổi topology (inter-satellite links)** và **hạn chế băng thông**—into a mathematical framework suitable for quantum computation, demonstrating how VQA/QAOA can achieve near-optimal solutions faster than traditional brute-force or heuristic methods.

### 💡 Key Features & Technical Contributions (PoC Focus)

1.  **QUBO Formulation Engine:** Tools to map dynamic shortest path problems and resource allocation constraints onto **Quadratic Unconstrained Binary Optimization (QUBO)** format, the required input for Quantum Annealers and QAOA circuits.
2.  **Hybrid Solver Framework:** Implementation of various **Variational Quantum Algorithms (VQA)** (e.g., QAOA) using **Qiskit** and **PennyLane** libraries, integrated with classical optimization backends (e.g., COBYLA, SLSQP).
3.  **Dynamic LEO Topology Simulator:** Integration with the `Poliastro` library to generate realistic LEO satellite orbits, calculate dynamic Inter-Satellite Link (ISL) schedules, and output time-variant network graph data.
4.  **Performance Benchmarking Suite:** Scripts to run comparative tests, measuring solution quality (optimality gap) and runtime complexity for:
    *   VQA/QAOA (Quantum)
    *   Classic Exact Solvers (Brute-Force/CPLEX)
    *   Classical Heuristics (Dijkstra, GA)

### 📈 Business & Research Impact Showcase

This toolkit provides vital proof-of-concept for:

*   **Ultra-Low Latency Routing:** Demonstrating the speed advantage of quantum-inspired algorithms in calculating dynamic routes in highly mobile networks (crucial for 6G and mission-critical communications).
*   **Feasibility Assessment:** Allowing telecommunications entities to benchmark the potential speed-up of quantum solutions over their current classical scheduling systems.
*   **Reproducibility:** Ensuring scientific rigor by providing the exact code and environment used to generate our published results on arXiv and future journal submissions.

### ⚙️ Setup and Reproducibility (Dockerized)

To ensure maximum reproducibility, the entire environment is containerized.

**Prerequisites:** Docker and Docker Compose must be installed.

#### Step 1: Clone the Repository

```bash
git clone https://github.com/QASCOM-Lab/Quantum-NTN-Scheduler.git
cd Quantum-NTN-Scheduler
```

#### Step 2: Build and Run the Environment

We use Docker to manage all dependencies (Python version, Qiskit, PennyLane, Poliastro).

```bash
# Build the Docker image (this may take a few minutes)
docker build -t qascom-ntn-scheduler:latest .

# Run the comparative simulation test (runs VQA vs. Dijkstra on a sample LEO graph)
docker run qascom-ntn-scheduler:latest python src/run_comparison_test.py --num_satellites 50 --algorithm VQA
```

#### Step 3: View Results

Simulation outputs (graph visualizations, performance metrics, and comparison charts) will be saved in the `./results` directory.

### 📚 Associated Publications

This repository is directly tied to the following research paper:

*   **Challenges in Applying Variational Quantum Algorithms to Dynamic Satellite Network Routing**
    *   *P. H. Do, T. D. Le*
    *   **[Read the Preprint on arXiv]** (Link đến DOI)
*   *Other related papers on QIO and resource allocation will be added here.*

### 🤝 Contribution

We welcome contributions! Please refer to the `CONTRIBUTING.md` file for guidelines on submitting pull requests, opening issues, and contributing to the development of our quantum simulation tools.
