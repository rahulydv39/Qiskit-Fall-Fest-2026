# Quantum Portfolio Optimization with Qiskit

**Event:** Qiskit Fall Fest 2026 — IIIT Delhi  
**Track:** Track 2 — Quantum Optimization  
**Team:** Superposition Squad  
**Team members:** Rahul Kumar, Alden Antony, Krishna Aggarwal  
**Level reached:** Advanced — Beginner, Intermediate, and Advanced notebooks  
**Presentation date:** 16 October 2026

## Project Overview

This project explores quantum approaches to portfolio optimization through three progressive notebooks. It combines classical reference solutions, QAOA circuit simulation, quantum-kernel machine learning, and selected experiments on IBM Quantum hardware.

All portfolio datasets are synthetic and intended for educational experimentation, not investment advice. The results do not establish quantum advantage.

## Notebooks

| Level | Notebook | Focus |
|---|---|---|
| Beginner | [Beginner_QAOA.ipynb](notebooks/Beginner_QAOA.ipynb) | QAOA for selecting 3 stocks from 6; classical exhaustive-search comparison and hardware execution |
| Intermediate | [Intermediate_Quantum_ML.ipynb](notebooks/Intermediate_Quantum_ML.ipynb) | Quantum fidelity kernel, SVM classification, ranking evaluation, and a separate small hardware demonstration |
| Advanced | [Advanced_QAOA.ipynb](notebooks/Advanced_QAOA.ipynb) | Constrained 20-qubit QAOA, Hamiltonian validation, simulation, and hardware evaluation |

## Approach and Results

### Beginner — QAOA Portfolio Optimization

The problem selects exactly 3 stocks from 6, giving 20 possible portfolios. Exhaustive classical search identifies **Stock 2, Stock 3, and Stock 6** as the reference optimum, with objective cost **−0.503015**.

The IBM `ibm_kingston` hardware run used 1,024 shots. It produced 609 valid portfolios (**59.47%**) and sampled the exact classical optimum 29 times (**2.83%**). The best valid sampled portfolio matched the reference optimum.

**Hardware job ID:** `db7mlh0r1c5c738kspdg`

### Intermediate — Quantum Machine Learning

The notebook considers 924 portfolios formed by selecting 6 of 12 stocks. It compares a quantum fidelity-kernel SVM with a classical RBF-kernel SVM and evaluates portfolio rankings against an exhaustive-search reference.

Both classifiers recorded 100% accuracy on the initial evaluated split. Across five recorded ranking evaluations, the quantum approach had mean Spearman correlation of approximately **0.94687**, while the classical comparison had approximately **0.95627**. These results do not indicate a quantum ranking advantage.

A separate **two-qubit feature-map-style circuit** ran on IBM `ibm_kingston` with 512 shots. This was a hardware demonstration only; the complete 12-qubit fidelity-kernel SVM pipeline was not executed or trained on hardware.

**Hardware job ID:** `db7n3e0r1c5c738ktlbg`

### Advanced — Constrained QAOA

The problem selects 10 stocks from 20, arranged as five sectors of four stocks each, with no more than two selected stocks per sector. The exhaustive classical search evaluates **7,776 feasible portfolios** and identifies the reference optimum as Stock 2, 4, 5, 7, 11, 12, 13, 16, 18, and 20, with objective cost **−1.111739**.

The cost Hamiltonian uses 20 logical qubits and 211 Pauli terms. The Hamiltonian check tested 101 bitstrings, with a maximum absolute numerical error of approximately **5.116 × 10⁻¹³**.

The simulator used 4,096 shots and produced 422 valid portfolios (**10.30%**); the exact classical optimum appeared once. The best valid simulated portfolio matched the classical optimum.

The IBM `ibm_kingston` hardware run used 256 shots. The transpiled circuit had depth 680 and 938 CZ gates. Only one valid portfolio was observed (**0.39%**), and the exact optimum was not observed. The best valid sampled cost was **−0.794773**, with an absolute gap of **0.316966** from the classical optimum. The parameter search reached its evaluation limit, so convergence was not established.

**Hardware job ID:** `db7n9iuil99s73fogb5g`

## How to Run

1. Open a notebook from the [`notebooks/`](notebooks/) directory in Google Colab or a compatible Jupyter environment.
2. Follow the setup instructions inside that notebook and execute its cells **from top to bottom**.
3. Review the saved outputs for the classical reference, simulator, and hardware analyses.
4. Running the notebook's IBM hardware cells is optional for reviewing the recorded results. Submitting new hardware jobs may consume IBM Quantum access or runtime.

Typical dependencies include `qiskit`, `qiskit-aer`, `qiskit-ibm-runtime`, `numpy`, `scipy`, and `scikit-learn`. The Intermediate notebook may also require `qiskit-machine-learning`; follow each notebook's setup cell for its exact environment.

Hardware execution requires IBM Quantum access and credentials. Store credentials in Google Colab Secrets or another secure secret manager; never commit API keys or tokens.

## Repository Structure

```text
Qiskit-Fall-Fest-2026/
├── README.md
├── REFERENCES.md
├── .gitignore
├── notebooks/
│   ├── Beginner_QAOA.ipynb
│   ├── Intermediate_Quantum_ML.ipynb
│   └── Advanced_QAOA.ipynb
└── presentation/
    ├── Final_Presentation.pdf
    └── Final_Presentation.pptx
```

## Limitations

- **Synthetic data:** The portfolio inputs are generated for experimentation and do not represent historical market data.
- **Classical baseline:** The current search spaces are small enough for exhaustive classical search. No quantum advantage is established.
- **Hardware noise and sampling:** Valid portfolio rates differed between simulation and hardware, especially in the advanced experiment. The experiments do not isolate the effects of noise, circuit depth, sampling, or parameter quality.
- **Parameter optimization:** The Advanced QAOA pilot reached its evaluation limit, so parameter convergence was not established.
- **Intermediate hardware scope:** The IBM hardware run was a separate two-qubit demonstration, not execution of the full quantum-kernel SVM pipeline.

## References

See [REFERENCES.md](REFERENCES.md) for Qiskit and IBM Quantum documentation, tutorial and code attribution, research references, and hardware job identifiers.

## AI Tools and Usage

**ChatGPT (OpenAI)** assisted with quantum-computing explanations, code troubleshooting, interpretation of experiment outputs, and drafting and refining project documentation and presentation content. The team is responsible for reviewing the implementation and verifying the reported results. Any additional AI tools used by team members should also be named here.

## Presentation

The presentation PDF (up to 8 slides) is available at [presentation/Final_Presentation.pdf](presentation/Final_Presentation.pdf). The editable PowerPoint is included as a backup at [presentation/Final_Presentation.pptx](presentation/Final_Presentation.pptx).
