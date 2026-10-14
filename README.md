# Quantum Portfolio Optimization with Qiskit

**Event:** Qiskit Fall Fest 2026 — IIIT Delhi  
**Track:** Track 2 — Quantum Optimization  
**Team:** Superposition Squad  
**Team members:** Rahul Kumar, Alden Antony, Krishna Aggarwal  
**Level reached:** Advanced  
**Presentation date:** 16 October 2026

## Project Overview

This project explores quantum approaches to portfolio optimization through three progressive notebooks: Beginner QAOA, Intermediate Quantum Machine Learning, and Advanced QAOA.

The experiments combine classical reference solutions, quantum circuit simulation, constraint validation, and selected executions on IBM Quantum hardware.

All portfolio inputs are synthetic. The results are educational experiments and are not financial advice. No quantum advantage is claimed.

## Notebooks

| Level | Notebook | Approach |
|---|---|---|
| Beginner | [Beginner_QAOA.ipynb](notebooks/Beginner_QAOA.ipynb) | QAOA for selecting 3 stocks from 6 |
| Intermediate | [Intermediate_Quantum_ML.ipynb](notebooks/Intermediate_Quantum_ML.ipynb) | Quantum fidelity kernel, SVM classification, and portfolio-ranking comparison |
| Advanced | [Advanced_QAOA.ipynb](notebooks/Advanced_QAOA.ipynb) | Constrained 20-qubit QAOA with cardinality and sector constraints |

## Approach

### Beginner — QAOA

A six-stock problem selects exactly three stocks. Exhaustive classical search evaluates all 20 possible portfolios and identifies Stock 2, Stock 3, and Stock 6 as the reference optimum, with objective cost -0.503015.

### Intermediate — Quantum Machine Learning

A 12-stock problem considers 924 portfolios containing six stocks each. The notebook compares a quantum fidelity-kernel SVM with a classical RBF-kernel SVM and evaluates portfolio rankings. A separate two-qubit feature-map-style circuit was executed on IBM hardware; the complete QML pipeline was not trained on hardware.

### Advanced — Constrained QAOA

A 20-stock problem selects ten stocks subject to sector constraints. The cost Hamiltonian uses 20 logical qubits and 211 Pauli terms. Exhaustive classical search evaluates 7,776 feasible portfolios and establishes a reference optimum with cost -1.111739.

## Results

### Beginner hardware experiment

- Backend: `ibm_kingston`
- Shots: 1,024
- Valid portfolios: 609 (59.47%)
- Exact classical optimum observed: 29 times (2.83%)
- Best valid portfolio matched the classical optimum.

Job ID: `db7mlh0r1c5c738kspdg`

### Intermediate hardware demonstration

- Backend: `ibm_kingston`
- Circuit: separate two-qubit feature-map-style demonstration
- Shots: 512
- Counts: `00 = 47`, `01 = 164`, `10 = 76`, `11 = 225`

Job ID: `db7n3e0r1c5c738ktlbg`

These measurements are from a small hardware demonstration, not from the complete 12-qubit QML training and evaluation pipeline.

### Advanced simulation

- Shots: 4,096
- Valid portfolios: 422 (10.30%)
- Exact classical optimum observed once
- Best valid cost: -1.111739

### Advanced hardware experiment

- Backend: `ibm_kingston`
- Shots: 256
- Compiled circuit depth: 680
- Valid portfolios: 1 (0.39%)
- Exact classical optimum observed: 0
- Best valid cost: -0.794773
- Absolute cost gap from the classical optimum: 0.316966

Job ID: `db7n9iuil99s73fogb5g`

The hardware results illustrate the challenges of constrained sampling with a deep circuit. Circuit depth, device noise, finite shots, and pilot parameters that were not shown to have converged may all affect performance.

## How to Run

1. Open a notebook from the `notebooks/` directory in Google Colab or a compatible Jupyter environment.
2. Follow its setup instructions and execute the cells in order from top to bottom.
3. Review the saved outputs for the classical reference, simulator evaluation, and hardware analysis.
4. Hardware execution is optional for reviewing the project. Existing job IDs and saved results are included; rerunning hardware cells may consume IBM Quantum resources.

Typical dependencies include `qiskit`, `qiskit-aer`, `qiskit-ibm-runtime`, `numpy`, `scipy`, and `scikit-learn`. The Intermediate notebook may also require `qiskit-machine-learning`. Follow the package installation instructions in each notebook.

IBM Quantum hardware cells require appropriate IBM Quantum access and credentials. Store credentials securely in Google Colab Secrets; never commit API keys or tokens.

## Repository Structure

```text
Qiskit-Fall-Fest-2026/
├── README.md
├── REFERENCES.md
├── notebooks/
│   ├── Beginner_QAOA.ipynb
│   ├── Intermediate_Quantum_ML.ipynb
│   └── Advanced_QAOA.ipynb
└── presentation/
    ├── Final_Presentation.pdf
    └── Final_Presentation.pptx


## Limitations

- **Synthetic data:** The portfolio experiments use synthetic data rather than historical market data.
- **Classical baseline:** The problem sizes are small enough for exhaustive classical search; no quantum advantage is established.
- **Hardware noise:** The Advanced hardware experiment produced only 1 valid portfolio from 256 shots (0.39%).
- **Parameter optimization:** The Advanced QAOA pilot reached its evaluation limit, so parameter convergence was not established.
- **Intermediate hardware scope:** The IBM hardware run tested a separate two-qubit demonstration circuit, not the complete quantum-kernel SVM pipeline.

These experiments demonstrate quantum algorithm implementation and evaluation, not a proven advantage over classical methods.

## AI Tools and Usage

**ChatGPT (OpenAI)** was used as an AI assistant for understanding quantum computing concepts, troubleshooting code, interpreting experimental results, and drafting and refining project documentation and presentation content.

The team is responsible for reviewing the implementation, checking reported experimental results against notebook outputs, and ensuring the accuracy of the final submission.

AI assistance is disclosed here for transparency. The team does not claim quantum advantage based on these experiments.