# References

This file lists the event information and technical sources relevant to the project. The notebooks' synthetic datasets, parameter choices, experiments, numerical results, and hardware job IDs are project-specific; the references below provide background and API documentation.

## Event

1. **Quantica / IIIT Delhi — Qiskit Fall Fest 2026.** Event overview, schedule, and track descriptions. Available at: <https://qiskit-fall-fest-xi.vercel.app/>. Accessed 14 October 2026.
2. **IIIT Delhi — Qiskit Fall Fest x IIIT Delhi listing on Unstop.** Event summary, Track 2 (Quantum Optimization), and submission timeline. Available at: <https://api.unstop.com/hackathons/hackathon-qiskit-fall-fest-x-iiitd-indraprastha-institute-of-information-technology-delhi-1765560>. Accessed 14 October 2026.

## QAOA and quantum optimization

3. Farhi, E., Goldstone, J., & Gutmann, S. (2014). *A Quantum Approximate Optimization Algorithm.* arXiv:1411.4028. <https://arxiv.org/abs/1411.4028>
4. **IBM Quantum Documentation — Quantum approximate optimization algorithm.** Explanation of QAOA, cost Hamiltonians, parameterized circuits, and hardware execution in Qiskit. <https://quantum.cloud.ibm.com/docs/en/tutorials/quantum-approximate-optimization-algorithm>
5. **Qiskit Documentation — Qiskit and IBM Quantum guides.** SDK and platform guidance. <https://quantum.cloud.ibm.com/docs/en/guides/index>

## Quantum machine learning and kernels

6. **Qiskit Machine Learning — Quantum Kernel Machine Learning tutorial.** Describes feature maps, fidelity quantum kernels, and using kernels with classical SVM classifiers. <https://qiskit-community.github.io/qiskit-machine-learning/tutorials/03_quantum_kernel.html>
7. **Qiskit Machine Learning — API documentation for quantum kernels.** Overview of fidelity-based quantum kernels and related abstractions. <https://qiskit-community.github.io/qiskit-machine-learning/apidocs/qiskit_machine_learning.kernels.html>
8. **scikit-learn — Support Vector Machines.** Reference for classical SVM classification and kernel methods used as a baseline. <https://scikit-learn.org/stable/modules/svm.html>

## Portfolio optimization and classical computing

9. Markowitz, H. (1952). *Portfolio Selection.* The Journal of Finance, 7(1), 77–91. DOI: <https://doi.org/10.1111/j.1540-6261.1952.tb01525.x>
10. **Qiskit Finance — Portfolio Optimization tutorial.** Background on mean-variance portfolio objectives, cardinality constraints, and mapping portfolio optimization to quantum algorithms. <https://qiskit-community.github.io/qiskit-finance/tutorials/01_portfolio_optimization.html>
11. **NumPy documentation.** Arrays, linear algebra, and random-number generation used in the synthetic portfolio workflow. <https://numpy.org/doc/stable/>
12. **SciPy documentation — Optimization.** Reference for classical numerical optimization methods such as `scipy.optimize.minimize`. <https://docs.scipy.org/doc/scipy/reference/optimize.html>

## Simulation and quantum hardware

13. **Qiskit Aer.** Qiskit's simulator framework. <https://github.com/Qiskit/qiskit-aer>
14. **Qiskit IBM Runtime.** Client library and documentation for submitting workloads to IBM Quantum services. <https://quantum.cloud.ibm.com/docs/en/api/qiskit-ibm-runtime>

## Project-specific experiment identifiers

The following identifiers refer to completed hardware jobs from these experiments. They are included for traceability and are not external literature references.

- Beginner QAOA portfolio run: `db7mlh0r1c5c738kspdg` — 1,024 shots.
- Beginner Bell-state demonstration: `db7hinaraffc73faipbg` — 256 shots.
- Intermediate two-qubit feature-map-style demonstration: `db7n3e0r1c5c738ktlbg` — 512 shots.
- Advanced 20-qubit QAOA hardware run: `db7n9iuil99s73fogb5g` — 256 shots.

## Citation and attribution note

Qiskit, Qiskit Aer, Qiskit Machine Learning, IBM Quantum Runtime, NumPy, SciPy, and scikit-learn are third-party projects. Their names and trademarks belong to their respective owners. Please cite the relevant software or research paper if you reuse these methods or adapt the implementation in future work.

## AI Tools

- **ChatGPT (OpenAI):** Used for conceptual explanations, code troubleshooting, interpreting experiment outputs, and assistance with documentation and presentation preparation.

## Code and Tutorial Attribution

- **Qiskit Fall Fest 2026 / IIIT Delhi:** Cite the official event page and the Track 2 starter repository or tutorial used for this submission.
- **Qiskit and IBM Quantum documentation:** Cite the specific documentation pages consulted for circuit construction, simulation, QAOA, quantum kernels, and hardware execution.
- **External repositories and research papers:** List any additional repositories, notebooks, papers, or code that were actually consulted or adapted, together with their URLs and a brief description of their relevance.
