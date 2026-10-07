<h1 align="center">🧪 Awesome Self-Evolving Scientific Agents</h1>

<p align="center"><b>LLM agents that get better at science by learning from their own research.</b></p>

<div align="center">

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![Papers](https://img.shields.io/badge/papers-139-2a78d6)](#-paper-list)
[![Last Updated](https://img.shields.io/badge/updated-2026--10-eb6834)](#-news)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](https://github.com/REAL-Lab-NU/Awesome-Self-Evolving-Scientific-Agents/pulls)
[![GitHub stars](https://img.shields.io/github/stars/REAL-Lab-NU/Awesome-Self-Evolving-Scientific-Agents?style=social)](https://github.com/REAL-Lab-NU/Awesome-Self-Evolving-Scientific-Agents)

</div>

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="assets/taxonomy-dark.svg">
    <img src="assets/taxonomy-light.svg" alt="Taxonomy: what evolves, when, how, and where" width="100%">
  </picture>
</p>

This repository collects work on **self-evolving LLM agents in the natural sciences**: systems whose memory, knowledge, tools, or own architecture improve from their research experience and carry over to later decisions. Every entry was screened against an explicit inclusion rule and labeled with a four-question taxonomy. If you know of a paper we missed, please open an issue or a pull request!

## 📢 News

- **[2026-10]** 🎉 Repository launched with **139 papers**, each labeled by what evolves, when, how, and where.

## 📑 Contents

- [🔍 What counts as self-evolving](#-what-counts-as-self-evolving)
- [📐 Taxonomy](#-taxonomy)
- [📊 At a glance](#-at-a-glance)
- [📚 Paper list](#-paper-list)
  - [🧬 Life Sciences](#-life-sciences) (56)
  - [🔬 Chemistry & Materials](#-chemistry--materials) (45)
  - [🌌 Physics, Earth & Space Sciences](#-physics-earth--space-sciences) (25)
  - [🧭 General Scientific Agent Frameworks](#-general-scientific-agent-frameworks) (13)
- [🤝 Contributing](#-contributing)

## 🔍 What counts as self-evolving

We view an agent as a **model θ plus a scaffold S**: memory, knowledge, tools, prompts, workflows, multi-agent organization, and the agent's own code. A paper is included when an LLM agent working on a natural-science research task

1. **writes back** part of its scaffold S persistently,
2. driven by **feedback** from its own execution, experiments, evaluations, or researchers, and
3. **reads the updated state again** in later decisions.

<details>
<summary><b>What is not included</b></summary>

- **Candidate-only evolution**: only the solutions evolve (programs, molecules, equations) while the agent stays the same, as in FunSearch/AlphaEvolve-style loops.
- **Weights-only updates**: RL or SFT of the model with no persistent scaffold state.
- **Read-only retrieval**, **single-run retries**, and **extra inference compute** (sampling, voting, tree search).
- **Out of scope tasks**: engineering design (devices, lenses, control laws), AI/ML research, pure mathematics, social science, and clinical medicine. Design of quantum control protocols and quantum error-correcting codes counts as physics.

</details>

## 📐 Taxonomy

| Question | Labels |
|---|---|
| **What evolves** | 🗂️ **Memory**: concrete cases, trajectories, experiment records · 💡 **Knowledge**: rules, mechanisms, hypotheses distilled from many cases · 🛠️ **Toolkit**: executable tools, functions, procedures · 🏗️ **Architecture**: prompts, workflows, team topology, the agent's own code |
| **When** | `training-time`: built in a dedicated phase, then frozen · `cross-task`: grows during use and carries over to new tasks · `within-project`: persists across rounds of one research project |
| **How** | *Feedback signal*: formal verification, code execution, simulation, datasets & benchmarks, literature, LLM judge, human expert, wet lab & instruments · *Update method*: direct recording, reflection & summarization, imitation & distillation, search & evolution, optimization, RL |
| **Where** | 🧬 Life Sciences · 🔬 Chemistry & Materials · 🌌 Physics, Earth & Space · 🧭 General Scientific Agent Frameworks (evaluated in two or more domains) |

## 📊 At a glance

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="assets/stats-dark.svg">
    <img src="assets/stats-light.svg" alt="Papers per domain by what evolves and when" width="100%">
  </picture>
</p>

## 📚 Paper list

One table per domain. Rows are sorted by the deepest component that evolves (Architecture › Toolkit › Knowledge › Memory), then by when it evolves (cross-task › training-time › within-project), then newest first. All labels, including feedback signals and update methods, are in [`data/papers.csv`](data/papers.csv).

### 🧬 Life Sciences

| Paper | Venue | What evolves | When | How (method · <sub>signal</sub>) |
|---|---|---|---|---|
| [A Persistent Fleet of AI Scientists Exhibits Cooperative and Autopoietic Behavior](https://doi.org/10.64898/2026.08.16.745122) | bioRxiv'26 | 🏗️ Architecture<br>💡 Knowledge<br>🗂️ Memory | Cross-task | Reflection<br><sub>code, benchmark, literature, LLM judge, human</sub> |
| [**RareAgent**: Self-Evolving Reasoning for Drug Repurposing in Rare Diseases](https://arxiv.org/abs/2510.05764) | arXiv'25 | 🏗️ Architecture<br>💡 Knowledge | Cross-task | Reflection, Distillation<br><sub>LLM judge</sub> |
| [**VCAgent**: A Mutation-Guided Self-Reflective Agent Framework for Virtual Cell Modeling](https://doi.org/10.1145/3770855.3818989) | KDD'26 | 🏗️ Architecture | Training-time | Reflection, Search<br><sub>benchmark</sub> |
| [**SIA**: Self Improving AI with Harness & Weight Updates](https://arxiv.org/abs/2605.27276) | arXiv'26 | 🏗️ Architecture<br>🛠️ Toolkit | Within-project | Reflection, Search, RL<br><sub>code, benchmark</sub> |
| [**AutoScientists**: Self-Organizing Agent Teams for Long-Running Scientific Experimentation](https://arxiv.org/abs/2605.28655) | arXiv'26 | 🏗️ Architecture<br>💡 Knowledge<br>🗂️ Memory | Within-project | Direct recording, Reflection<br><sub>code, benchmark, LLM judge</sub> |
| [**MAC-AMP**: A Closed-Loop Multi-Agent Collaboration System for Multi-Objective Antimicrobial Peptide Design](https://arxiv.org/abs/2602.14926) | arXiv'26 | 🏗️ Architecture<br>🛠️ Toolkit<br>🗂️ Memory | Within-project | Reflection, Search, Direct recording<br><sub>code, simulation, LLM judge, human</sub> |
| [**The Station**: An Open-World Environment for AI-Driven Discovery](https://arxiv.org/abs/2511.06309) | arXiv'25 | 🏗️ Architecture<br>🛠️ Toolkit<br>💡 Knowledge<br>🗂️ Memory | Within-project | Reflection, Direct recording<br><sub>code, benchmark, LLM judge</sub> |
| [Hypothesis Hunting with Evolving Networks of Autonomous Scientific Agents](https://arxiv.org/abs/2510.08619) | arXiv'25 | 🏗️ Architecture<br>🗂️ Memory | Within-project | Direct recording, Reflection<br><sub>code, LLM judge</sub> |
| [**TusoAI**: Agentic Optimization for Scientific Methods](https://arxiv.org/abs/2509.23986) | arXiv'25 | 🏗️ Architecture<br>🗂️ Memory | Within-project | Reflection, Optimization<br><sub>code, benchmark</sub> |
| [**Robin**: A multi-agent system for automating scientific discovery](https://arxiv.org/abs/2505.13400) | Nature'25 | 🏗️ Architecture<br>💡 Knowledge<br>🗂️ Memory | Within-project | Reflection<br><sub>human, wet lab</sub> |
| [Accelerating scientific discovery with Co-Scientist](https://arxiv.org/abs/2502.18864) | Nature'25 | 🏗️ Architecture<br>💡 Knowledge | Within-project | Reflection<br><sub>LLM judge, literature</sub> |
| [**SpaCellAgent**: A Self-Evolving LLM-Based Multi-Agent Framework for Trajectory Analysis](https://arxiv.org/abs/2607.07467) | KDD'26 | 🛠️ Toolkit<br>🗂️ Memory | Cross-task | Direct recording<br><sub>code, LLM judge, literature</sub> |
| [**ReCo**: a self-configuring and self-extending agentic framework for biomedical research](https://doi.org/10.64898/2026.07.14.26358025) | medRxiv'26 | 🛠️ Toolkit | Cross-task | Reflection<br><sub>code, human</sub> |
| [Self-evolving AI agents for protein discovery and directed evolution](https://arxiv.org/abs/2603.27303) | arXiv'26 | 🛠️ Toolkit | Cross-task | Reflection, Optimization<br><sub>code, benchmark, LLM judge</sub> |
| [**PantheonOS**: An Evolvable Multi-Agent Framework for Automatic Genomics Discovery](https://doi.org/10.64898/2026.02.26.707870) | bioRxiv'26 | 🛠️ Toolkit<br>💡 Knowledge | Cross-task | Search, Reflection<br><sub>code, benchmark, LLM judge</sub> |
| [**LabOS**: The AI-XR Co-Scientist That Sees and Works With Humans](https://arxiv.org/abs/2510.14861) | bioRxiv'25 | 🛠️ Toolkit<br>🗂️ Memory | Cross-task | Reflection, Direct recording<br><sub>code, LLM judge, wet lab</sub> |
| [**STELLA**: Towards a Biomedical World Model with Self-Evolving Multimodal Agents](https://doi.org/10.1101/2025.07.01.662467) | bioRxiv'25 | 🛠️ Toolkit<br>💡 Knowledge | Cross-task | Reflection, Distillation, Optimization<br><sub>code, LLM judge, wet lab</sub> |
| [**STELLA**: Self-Evolving LLM Agent for Biomedical Research](https://arxiv.org/abs/2507.02004) | arXiv'25 | 🛠️ Toolkit<br>💡 Knowledge | Cross-task | Reflection, Distillation<br><sub>code, LLM judge</sub> |
| [Autonomous self-evolving research on biomedical data: the DREAM paradigm](https://arxiv.org/abs/2407.13637) | Advanced Science 2025 | 🛠️ Toolkit | Cross-task | Reflection, Search<br><sub>code, LLM judge</sub> |
| [**Vestrum**: Improving Agent Harnesses by Adapting Their Verification, Structure and Memory](https://arxiv.org/abs/2609.33822) | arXiv'26 | 🛠️ Toolkit<br>💡 Knowledge | Training-time | Reflection<br><sub>benchmark, LLM judge</sub> |
| [**LabAgent**: Customize Any Research Hubs for Scientific Discoveries Using AI Agents](https://arxiv.org/abs/2609.13437) | arXiv'26 | 🛠️ Toolkit<br>🗂️ Memory | Training-time | Reflection, Direct recording<br><sub>code, LLM judge</sub> |
| [**PRAXIS**: Case-distilled and code-verified AI agents for biological research](https://arxiv.org/abs/2605.23169) | arXiv'26 | 🛠️ Toolkit<br>💡 Knowledge<br>🗂️ Memory | Training-time | Reflection, Distillation<br><sub>code, literature, human</sub> |
| [**DrugSAGE**: Self-evolving Agent Experience for Efficient State-of-the-Art Drug Discovery](https://arxiv.org/abs/2605.15461) | arXiv'26 | 🛠️ Toolkit<br>🗂️ Memory | Training-time | Direct recording, Reflection<br><sub>code, benchmark</sub> |
| [**ToolUniverse**: An open platform for democratizing AI scientists](https://arxiv.org/abs/2509.23426) | arXiv'25 | 🛠️ Toolkit | Training-time | Reflection<br><sub>code, literature, LLM judge, human</sub> |
| [**Paper2Agent**: Reimagining Research Papers As Interactive and Reliable AI Agents](https://arxiv.org/abs/2509.06917) | Nature'25 | 🛠️ Toolkit | Training-time | Reflection<br><sub>code</sub> |
| [An autonomous agentic framework for cross-campaign generalization and sensor shift adaptation](https://doi.org/10.1088/2632-2153/ae9fb7) | Machine Learning: Science and Technology 2026 | 💡 Knowledge<br>🗂️ Memory | Cross-task | Direct recording, Reflection, Optimization<br><sub>code, benchmark, LLM judge</sub> |
| [**Agri-SAGE**: Simulation-Grounded Multi-Agent LLM for Context-Aware Agricultural Advisory Generation](https://arxiv.org/abs/2607.00454) | arXiv'26 | 💡 Knowledge<br>🗂️ Memory | Cross-task | Reflection<br><sub>simulation</sub> |
| [A Self-Evolving Agentic System for Automated Generation and Execution of Biological Protocols](https://arxiv.org/abs/2606.31763) | arXiv'26 | 💡 Knowledge<br>🗂️ Memory | Cross-task | Reflection<br><sub>code, human, wet lab</sub> |
| [**SpatialClaw**: A Memory-Augmented Autonomous Ecosystem for Spatial Omics Analysis](https://doi.org/10.64898/2026.05.21.723451) | bioRxiv'26 | 💡 Knowledge<br>🗂️ Memory | Cross-task | Reflection, Direct recording<br><sub>code, LLM judge, human</sub> |
| [**Agentic Lab**: An Agentic-physical AI system for cell and organoid experimentation and manufacturing](https://doi.org/10.1101/2025.11.11.686354) | bioRxiv'25 | 💡 Knowledge<br>🗂️ Memory | Cross-task | Reflection, Direct recording<br><sub>wet lab, literature, human</sub> |
| [**OriGene**: A Self-Evolving Virtual Disease Biologist Automating Therapeutic Target Discovery](https://doi.org/10.1101/2025.06.03.657658) | bioRxiv'25 | 💡 Knowledge | Cross-task | Reflection, Distillation<br><sub>LLM judge, human, wet lab</sub> |
| [**SSE-Bio**: A Structured Self-Evolving Agent with Agentic Retrieval Policy for Multi-Hop Biomedical Reasoning](https://arxiv.org/abs/2608.22132) | arXiv'26 | 💡 Knowledge | Training-time | Reflection, Distillation<br><sub>LLM judge</sub> |
| [Process-Reward Tactic Evolution for Long-Horizon Bioinformatics Workflows](https://arxiv.org/abs/2606.20839) | arXiv'26 | 💡 Knowledge | Training-time | Reflection, Distillation, Optimization<br><sub>code, benchmark, LLM judge</sub> |
| [**MDAgent**: A Multi-Agent Framework for End-to-End Molecular Dynamics Research](https://arxiv.org/abs/2604.18622) | arXiv'26 | 💡 Knowledge<br>🗂️ Memory | Training-time | Reflection<br><sub>code, simulation, LLM judge</sub> |
| [**AgentFold**: Closed-Loop Agentic Search for Protein Folding Model Design](https://arxiv.org/abs/2608.26747) | arXiv'26 | 💡 Knowledge<br>🗂️ Memory | Within-project | Reflection<br><sub>code, benchmark, literature, LLM judge</sub> |
| [Accelerating Scientific Research with Gemini in the Real-World](https://arxiv.org/abs/2608.26701) | arXiv'26 | 💡 Knowledge | Within-project | Reflection<br><sub>code, LLM judge</sub> |
| [**Networked Intelligence**: Active Shared Context Graphs for Human-AI Team Science](https://arxiv.org/abs/2607.13220) | arXiv'26 | 💡 Knowledge<br>🗂️ Memory | Within-project | Reflection, Direct recording<br><sub>code, human, wet lab</sub> |
| [Autonomous Scientific Discovery via Iterative Meta-Reflection](https://arxiv.org/abs/2607.01131) | arXiv'26 | 💡 Knowledge<br>🗂️ Memory | Within-project | Direct recording, Reflection<br><sub>code, benchmark</sub> |
| [Can AI Scientist Agents Learn from Lab-in-the-Loop Feedback? Evidence from Iterative Perturbation Discovery](https://arxiv.org/abs/2603.26177) | arXiv'26 | 💡 Knowledge | Within-project | Reflection<br><sub>benchmark</sub> |
| [An AI-Native Biofoundry for Autonomous Enzyme Engineering: Integrating Active Learning with Automated Experimentation](https://doi.org/10.64898/2026.02.01.703093) | bioRxiv'26 | 💡 Knowledge | Within-project | Optimization<br><sub>wet lab</sub> |
| [**MARBLE**: Multi-Agent Reasoning for Bioinformatics Learning and Evolution](https://arxiv.org/abs/2601.14349) | arXiv'26 | 💡 Knowledge<br>🗂️ Memory | Within-project | Direct recording, Reflection<br><sub>code, benchmark</sub> |
| [Swarms of Large Language Model Agents for Protein Sequence Design with Experimental Validation](https://arxiv.org/abs/2511.22311) | arXiv'25 | 💡 Knowledge<br>🗂️ Memory | Within-project | Direct recording<br><sub>simulation</sub> |
| [**Kosmos**: An AI Scientist for Autonomous Discovery](https://arxiv.org/abs/2511.02824) | arXiv'25 | 💡 Knowledge<br>🗂️ Memory | Within-project | Reflection<br><sub>code, literature</sub> |
| [**BioDiscoveryAgent**: An AI Agent for Designing Genetic Perturbation Experiments](https://arxiv.org/abs/2405.17631) | ICLR'25 | 💡 Knowledge | Within-project | Reflection<br><sub>benchmark, literature</sub> |
| [**EasyBCI Agent**: Towards Universal Neural Data Preprocessing for Brain-Computer Interfaces](https://arxiv.org/abs/2607.29007) | arXiv'26 | 🗂️ Memory | Cross-task | Direct recording<br><sub>code, human</sub> |
| [**HarmonyCell**: Automating Single-Cell Perturbation Modeling under Semantic and Distribution Shifts](https://arxiv.org/abs/2603.01396) | arXiv'26 | 🗂️ Memory | Cross-task | Direct recording<br><sub>code, benchmark</sub> |
| [Empowering AI data scientists using a multi-agent LLM framework with self-evolving capabilities for autonomous, tool-aware biomedical data analyses](https://doi.org/10.1038/s41551-026-01634-6) | Nature Biomedical Engineering 2026 | 🗂️ Memory | Cross-task | Reflection, Direct recording<br><sub>code</sub> |
| [**GenCellAgent**: Generalizable, Training-Free Cellular Image Segmentation via Large Language Model Agents](https://arxiv.org/abs/2510.13896) | arXiv'25 | 🗂️ Memory | Cross-task | Direct recording, Reflection<br><sub>LLM judge, human</sub> |
| [**Chat Modeling**: Interaction-Enhanced Agent Framework for Visualizing Literature-Grounded Biological Structures](https://arxiv.org/abs/2404.01063) | arXiv'24 | 🗂️ Memory | Cross-task | Reflection, Direct recording<br><sub>human</sub> |
| [Harnessing AI to Build Virtual Cells](https://doi.org/10.64898/2026.04.11.717183) | bioRxiv'26 | 🗂️ Memory | Within-project | Reflection<br><sub>code, benchmark</sub> |
| [**BioDyad**: Synchronize Biomedical Discovery and Machine Learning Engineering](https://arxiv.org/abs/2609.31939) | arXiv'26 | 🗂️ Memory | Within-project | Direct recording<br><sub>code, benchmark</sub> |
| [**ADMET-EvO**: a self-evolving scientific agent for sustained research across heterogeneous tasks](https://arxiv.org/abs/2609.10121) | arXiv'26 | 🗂️ Memory | Within-project | Optimization<br><sub>code, benchmark</sub> |
| [**ASI-Evolve**: AI Accelerates AI](https://arxiv.org/abs/2603.29640) | arXiv'26 | 🗂️ Memory | Within-project | Reflection<br><sub>code, benchmark</sub> |
| [Using a GPT-5-driven autonomous lab to optimize the cost and titer of cell-free protein synthesis](https://doi.org/10.64898/2026.02.05.703998) | bioRxiv'26 | 🗂️ Memory | Within-project | Reflection<br><sub>wet lab</sub> |
| [**Aleks**: AI powered Multi Agent System for Autonomous Scientific Discovery via Data-Driven Approaches in Plant Science](https://arxiv.org/abs/2508.19383) | arXiv'25 | 🗂️ Memory | Within-project | Direct recording<br><sub>code, benchmark, LLM judge</sub> |
| [**AutoDiscovery**: Open-ended Scientific Discovery via Bayesian Surprise](https://arxiv.org/abs/2507.00310) | NeurIPS'25 | 🗂️ Memory | Within-project | Reflection, Direct recording<br><sub>code, benchmark, LLM judge</sub> |

### 🔬 Chemistry & Materials

| Paper | Venue | What evolves | When | How (method · <sub>signal</sub>) |
|---|---|---|---|---|
| [Fantastic Scientific Agents and How to Build Them: AgentBuild for Rietveld Refinement](https://arxiv.org/abs/2606.12834) | arXiv'26 | 🏗️ Architecture<br>💡 Knowledge | Training-time | Search<br><sub>code, simulation, benchmark, LLM judge</sub> |
| [Autonomous heterogeneous catalyst discovery with a self-evolving multi-agent digital twin](https://arxiv.org/abs/2606.05050) | arXiv'26 | 🏗️ Architecture<br>💡 Knowledge<br>🗂️ Memory | Training-time | Direct recording, Reflection, Optimization<br><sub>code, simulation, LLM judge</sub> |
| [**AgentCAT**: An LLM Agent for Extracting and Analyzing Catalytic Reaction Data from Chemical Engineering Literature](https://arxiv.org/abs/2602.18479) | arXiv'26 | 🏗️ Architecture | Training-time | Reflection<br><sub>literature, LLM judge, human</sub> |
| [**ChemAmp**: Amplified Chemistry Tools via Composable Agents](https://arxiv.org/abs/2505.21569) | arXiv'25 | 🏗️ Architecture<br>🛠️ Toolkit | Training-time | Search<br><sub>benchmark</sub> |
| [**ChemHTS**: Hierarchical Tool Stacking for Enhancing Chemical Agents](https://arxiv.org/abs/2502.14327) | arXiv'25 | 🏗️ Architecture<br>🛠️ Toolkit | Training-time | Search<br><sub>benchmark</sub> |
| [Human-agent discovery of reconfigurable in-plane ferroelectric superdomain control](https://arxiv.org/abs/2609.06887) | arXiv'26 | 🏗️ Architecture<br>🛠️ Toolkit<br>💡 Knowledge<br>🗂️ Memory | Within-project | Reflection, Direct recording<br><sub>wet lab, human, code, benchmark</sub> |
| [From Human Hypotheses to LLM Insights: Advancing Bayesian Optimisation for Autonomous Scientific Discovery](https://livrepository.liverpool.ac.uk/3197318/) | PhD thesis, University of Liverpool 2026 | 🏗️ Architecture<br>💡 Knowledge | Within-project | Reflection<br><sub>simulation, human</sub> |
| [**NISPO**: Open-source IUPAC name generation tool](https://arxiv.org/abs/2607.26113) | arXiv'26 | 🏗️ Architecture | Within-project | Reflection<br><sub>code, benchmark, LLM judge, human</sub> |
| [Discovering physical mechanisms from experiment-simulation mismatches](https://arxiv.org/abs/2604.26703) | arXiv'26 | 🛠️ Toolkit<br>💡 Knowledge | Cross-task | Reflection, Distillation, Optimization<br><sub>simulation, benchmark</sub> |
| [Autonomous Multi-objective Alloy Design through Simulation-guided Optimization](https://arxiv.org/abs/2507.16005) | arXiv'25 | 🛠️ Toolkit | Training-time | Optimization<br><sub>simulation, literature</sub> |
| [Hypothesis-Driven Autonomous Materials Synthesis with Multimodal LLM Agents](https://arxiv.org/abs/2609.18598) | arXiv'26 | 🛠️ Toolkit<br>💡 Knowledge | Within-project | Reflection<br><sub>wet lab, code</sub> |
| [Autonomous discovery of new structure-plausibility laws for explainable and rapid crystal diagnosis and screening](https://arxiv.org/abs/2609.01209) | arXiv'26 | 🛠️ Toolkit<br>🗂️ Memory | Within-project | Reflection<br><sub>code, simulation, benchmark</sub> |
| [Autonomous computational catalysis through an agentic research system](https://arxiv.org/abs/2601.13508) | arXiv'26 | 🛠️ Toolkit<br>💡 Knowledge<br>🗂️ Memory | Within-project | Reflection, Optimization, Direct recording<br><sub>code, simulation, LLM judge, human</sub> |
| [Human-AI collaborative autonomous synthesis with pulsed laser deposition for remote epitaxy](https://arxiv.org/abs/2511.11558) | Research Square 2025 | 🛠️ Toolkit | Within-project | Reflection<br><sub>wet lab, code, human</sub> |
| [**MolecureAI**: an agentic AI platform for autonomous drug discovery](https://doi.org/10.3389/fphar.2026.1917774) | Frontiers in Pharmacology 2026 | 💡 Knowledge<br>🗂️ Memory | Cross-task | Reflection<br><sub>code, simulation, literature, LLM judge</sub> |
| [**LabEvolver**: Training-Free Experience Evolution for Safe and Grounded Wet-Lab Agents](https://arxiv.org/abs/2607.27690) | arXiv'26 | 💡 Knowledge<br>🗂️ Memory | Cross-task | Reflection<br><sub>wet lab, benchmark</sub> |
| [Harnessing agent memory to build lifelong AI partners for materials scientists](https://arxiv.org/abs/2608.11224) | arXiv'26 | 💡 Knowledge<br>🗂️ Memory | Cross-task | Reflection, Distillation, Direct recording<br><sub>code, simulation</sub> |
| [Agentic generation of verifiable rules for deterministic, self-expanding reaction classification](https://arxiv.org/abs/2607.01061) | arXiv'26 | 💡 Knowledge | Cross-task | Reflection<br><sub>LLM judge</sub> |
| [**CASCADE**: Cumulative Agentic Skill Creation through Autonomous Development and Evolution](https://arxiv.org/abs/2512.23880) | arXiv'25 | 💡 Knowledge<br>🗂️ Memory | Cross-task | Reflection, Direct recording<br><sub>human</sub> |
| [**S3C-LLM**: Skill-Code Guided Agentic Language Models for Spectrum-to-Structure Elucidation](https://arxiv.org/abs/2608.30910) | arXiv'26 | 💡 Knowledge | Training-time | Reflection<br><sub>benchmark</sub> |
| [**MolMem**: Memory-Augmented Agentic Reinforcement Learning for Sample-Efficient Molecular Optimization](https://arxiv.org/abs/2604.12237) | ACL'26 | 💡 Knowledge | Training-time | Reflection, Distillation, RL<br><sub>simulation</sub> |
| [AI-guided high-throughput discovery of iridium- and ruthenium-free palladium-oxide catalysts for durable acidic oxygen evolution](https://arxiv.org/abs/2609.30133) | arXiv'26 | 💡 Knowledge | Within-project | Reflection, Optimization<br><sub>wet lab</sub> |
| [Toward Auditable AI Scientists: A Hypothesis Evolution Protocol for LLM Agents](https://arxiv.org/abs/2607.09195) | arXiv'26 | 💡 Knowledge<br>🗂️ Memory | Within-project | Direct recording, Reflection, Search<br><sub>simulation, code, LLM judge</sub> |
| [Symbolic Predicate-Guided Language Agents for Inverse Design of Perovskite Oxides](https://arxiv.org/abs/2607.15535) | arXiv'26 | 💡 Knowledge | Within-project | Reflection<br><sub>simulation, code, LLM judge</sub> |
| [**My Chemical Harness**: Evolutionary Molecular Design over Synthetic Pathways with Large Language Model Agents](https://arxiv.org/abs/2606.11256) | arXiv'26 | 💡 Knowledge<br>🗂️ Memory | Within-project | Reflection, Direct recording<br><sub>code, simulation</sub> |
| [Interpretable Inverse Design of Metal-Organic Frameworks with Large Language Model Agents](https://arxiv.org/abs/2606.29459) | arXiv'26 | 💡 Knowledge<br>🗂️ Memory | Within-project | Reflection, Direct recording<br><sub>simulation, benchmark</sub> |
| [Towards Discovery of Polymers for Insulin Delivery via Physics-Grounded Agentic Workflows](https://arxiv.org/abs/2605.18831) | arXiv'26 | 💡 Knowledge<br>🗂️ Memory | Within-project | Reflection<br><sub>code, simulation, literature</sub> |
| [**Probe Before You Edit**: Probing-Guided Molecular Optimization for LLM Agents in Structure-Based Drug Design](https://arxiv.org/abs/2606.00555) | arXiv'26 | 💡 Knowledge<br>🗂️ Memory | Within-project | Reflection<br><sub>simulation</sub> |
| [**Battery-Sim-Agent**: Leveraging LLM-Agent for Inverse Battery Parameter Estimation](https://arxiv.org/abs/2605.29560) | KDD'26 | 💡 Knowledge<br>🗂️ Memory | Within-project | Reflection, Direct recording<br><sub>simulation, benchmark</sub> |
| [Agentic Discovery of Exchange-Correlation Density Functionals](https://arxiv.org/abs/2605.05460) | arXiv'26 | 💡 Knowledge<br>🗂️ Memory | Within-project | Reflection<br><sub>simulation, benchmark</sub> |
| [**AI4S-SDS**: A Neuro-Symbolic Solvent Design System via Sparse MCTS and Differentiable Physics Alignment](https://arxiv.org/abs/2603.03686) | arXiv'26 | 💡 Knowledge<br>🗂️ Memory | Within-project | Reflection<br><sub>simulation, LLM judge</sub> |
| [Reasoning-Driven Design of Single Atom Catalysts via a Multi-Agent Large Language Model Framework](https://arxiv.org/abs/2602.21533) | arXiv'26 | 💡 Knowledge<br>🗂️ Memory | Within-project | Reflection, Direct recording<br><sub>simulation, LLM judge</sub> |
| [**ChemNavigator**: Agentic AI Discovery of Design Rules for Organic Photocatalysts](https://arxiv.org/abs/2601.17084) | arXiv'26 | 💡 Knowledge | Within-project | Reflection<br><sub>simulation</sub> |
| [**Reasoning BO**: Enhancing Bayesian Optimization with Long-Context Reasoning Power of LLMs](https://arxiv.org/abs/2505.12833) | arXiv'25 | 💡 Knowledge<br>🗂️ Memory | Within-project | Reflection<br><sub>benchmark, LLM judge</sub> |
| [**Feedback to Reasoning**: LLM-Assisted Molecular Optimization with Domain Feedback and Historical Reasoning](https://doi.org/10.18653/v1/2026.findings-acl.619) | Findings of ACL 2026 | 💡 Knowledge<br>🗂️ Memory | — | Reflection<br><sub>code, simulation</sub> |
| [Long-Term Memory for VLA-based Agents in Open-World Task Execution](https://arxiv.org/abs/2604.15671) | arXiv'26 | 🗂️ Memory | Cross-task | Reflection, Direct recording<br><sub>human</sub> |
| [Operating advanced scientific instruments with AI agents that learn on the job](https://arxiv.org/abs/2509.00098) | npj Computational Materials 2025 | 🗂️ Memory | Cross-task | Direct recording<br><sub>human</sub> |
| [**TopoMAS**: Large Language Model Driven Topological Materials Multiagent System](https://arxiv.org/abs/2507.04053) | arXiv'25 | 🗂️ Memory | Cross-task | Direct recording<br><sub>simulation, LLM judge</sub> |
| [**ChemAgent**: Self-updating Library in Large Language Models Improves Chemical Reasoning](https://arxiv.org/abs/2501.06590) | arXiv'25 | 🗂️ Memory | Training-time | Direct recording, Reflection, Distillation<br><sub>benchmark, LLM judge</sub> |
| [Agentic Design of Compositional Descriptors via Autoresearch for Materials Science Applications](https://arxiv.org/abs/2605.14671) | arXiv'26 | 🗂️ Memory | Within-project | Reflection<br><sub>benchmark</sub> |
| [Constraint-Aware Corrective Memory for Language-Based Drug Discovery Agents](https://arxiv.org/abs/2604.09308) | arXiv'26 | 🗂️ Memory | Within-project | Reflection<br><sub>code, simulation, benchmark, LLM judge</sub> |
| [Accelerated Inorganic Materials Design with Generative AI Agents](https://arxiv.org/abs/2504.00741) | Cell Reports Physical Science 2025 | 🗂️ Memory | Within-project | Direct recording<br><sub>simulation</sub> |
| [A Multi-agent Framework for Physical Laws Discovery](https://arxiv.org/abs/2411.16416) | arXiv'24 | 🗂️ Memory | Within-project | Reflection<br><sub>code, benchmark, LLM judge</sub> |
| [**LLMatDesign**: Autonomous Materials Discovery with Large Language Models](https://arxiv.org/abs/2406.13163) | arXiv'24 | 🗂️ Memory | Within-project | Reflection<br><sub>simulation</sub> |
| [**PharmAgents**: Building a Virtual Pharma with Large Language Model Agents](https://arxiv.org/abs/2503.22164) | arXiv'25 | 🗂️ Memory | — | Reflection<br><sub>simulation, LLM judge</sub> |

### 🌌 Physics, Earth & Space Sciences

| Paper | Venue | What evolves | When | How (method · <sub>signal</sub>) |
|---|---|---|---|---|
| [**GeoForge**: Non-Parametric Self-Evolving Agents for Earth-Observation Reasoning](https://arxiv.org/abs/2608.10494) | arXiv'26 | 🏗️ Architecture<br>💡 Knowledge<br>🗂️ Memory | Cross-task | Reflection, Distillation<br><sub>code, LLM judge</sub> |
| [**GRAFT-ATHENA**: Self-Improving Agentic Teams for Autonomous Discovery and Evolutionary Numerical Algorithms](https://arxiv.org/abs/2605.11117) | arXiv'26 | 🏗️ Architecture<br>💡 Knowledge<br>🗂️ Memory | Cross-task | Reflection, Direct recording<br><sub>formal, code, simulation, benchmark, literature, LLM judge, human</sub> |
| [Recursive self-improvement of AI research agents](https://arxiv.org/abs/2609.26457) | arXiv'26 | 🏗️ Architecture | Training-time | Search<br><sub>code, benchmark</sub> |
| [Auto-Configuring Scientific Simulators with Lightweight Coding-Agent Adapters](https://arxiv.org/abs/2606.09774) | arXiv'26 | 🏗️ Architecture<br>💡 Knowledge | Training-time | Reflection, Search<br><sub>benchmark</sub> |
| [**Eureka**: Task-Conditioned Meta-Agent Orchestration for Scientific Discovery](https://arxiv.org/abs/2608.19047) | arXiv'26 | 🏗️ Architecture<br>🗂️ Memory | Within-project | Search, Optimization, Direct recording<br><sub>code</sub> |
| [CLVisc Agent for autonomous relativistic hydrodynamics studies](https://arxiv.org/abs/2607.27822) | arXiv'26 | 🛠️ Toolkit | Training-time | Reflection<br><sub>code, human</sub> |
| [Deploying Frontier Agentic Technology in MOOSEnger, a Multiphysics-Capable AI Assistant](https://arxiv.org/abs/2608.15881) | arXiv'26 | 💡 Knowledge<br>🗂️ Memory | Cross-task | Reflection<br><sub>code, human</sub> |
| [LLM-Driven Cross-Paradigm Design for Quantum Optimal Control](https://arxiv.org/abs/2607.17498) | arXiv'26 | 💡 Knowledge<br>🗂️ Memory | Cross-task | Direct recording, Reflection<br><sub>simulation</sub> |
| [End-to-end autonomous scientific discovery on a real optical platform](https://arxiv.org/abs/2604.27092) | arXiv'26 | 💡 Knowledge<br>🗂️ Memory | Cross-task | Reflection<br><sub>wet lab, code, simulation, LLM judge, literature</sub> |
| [From Experiments to Expertise: Scientific Knowledge Consolidation for AI-Driven Computational Physics](https://arxiv.org/abs/2603.13191) | arXiv'26 | 💡 Knowledge<br>🗂️ Memory | Cross-task | Direct recording, Reflection<br><sub>code, simulation, benchmark, literature</sub> |
| [Experience-Driven Multi-Agent Systems Are Training-free Context-aware Earth Observers](https://arxiv.org/abs/2602.02559) | arXiv'26 | 💡 Knowledge | Cross-task | Reflection, Distillation<br><sub>code, LLM judge</sub> |
| [**PhysMaster**: Building an Autonomous AI Physicist for Theoretical and Computational Physics Research](https://arxiv.org/abs/2512.19799) | arXiv'25 | 💡 Knowledge<br>🗂️ Memory | Cross-task | Reflection<br><sub>code, LLM judge</sub> |
| [**CangLing-KnowFlow**: A Unified Knowledge-and-Flow-fused Agent for Comprehensive Remote Sensing Applications](https://arxiv.org/abs/2512.15231) | arXiv'25 | 💡 Knowledge | Cross-task | Reflection, Distillation<br><sub>code</sub> |
| [Interpreting Multi-band Galaxy Observations with Large Language Model-Based Agents](https://arxiv.org/abs/2409.14807) | NeurIPS ML4PS Workshop 2024 | 💡 Knowledge | Cross-task | Reflection<br><sub>simulation, benchmark, LLM judge</sub> |
| [**GeoSkill**: Experience-Driven Hierarchical Skill Learning with Collaborative Revision for Geospatial Agents](https://arxiv.org/abs/2609.13667) | arXiv'26 | 💡 Knowledge | Training-time | Reflection<br><sub>code, benchmark, LLM judge</sub> |
| [**TimeClaw**: A Time-Series AI Agent with Exploratory Execution Learning](https://arxiv.org/abs/2605.10038) | arXiv'26 | 💡 Knowledge | Training-time | Reflection, Distillation<br><sub>benchmark</sub> |
| [MadAgents](https://arxiv.org/abs/2601.21015) | arXiv'26 | 💡 Knowledge | Training-time | Reflection<br><sub>code, LLM judge</sub> |
| [**Mephisto**: Self-Improving Large Language Model-Based Agents for Automated Interpretation of Multi-band Galaxy Observations](https://arxiv.org/abs/2510.08354) | The Astrophysical Journal Supplement Series 2025 | 💡 Knowledge | Training-time | Reflection, Distillation<br><sub>simulation, benchmark, LLM judge</sub> |
| [Multi-agent discovery of practical quantum LDPC codes](https://arxiv.org/abs/2608.08996) | arXiv'26 | 💡 Knowledge<br>🗂️ Memory | Within-project | Reflection, Direct recording<br><sub>formal, code, LLM judge</sub> |
| [Socratic agents for autonomous scientific discovery in high-dimensional physical systems](https://arxiv.org/abs/2606.26722) | arXiv'26 | 💡 Knowledge | Within-project | Reflection<br><sub>wet lab, LLM judge, human</sub> |
| [Toward General Quantum Control with Physics-Informed Large Language Models](https://arxiv.org/abs/2605.26021) | arXiv'26 | 💡 Knowledge | Within-project | Reflection<br><sub>simulation</sub> |
| [**PhysMiner**: An Agentic AI Framework for Automated Flow Component Analysis](https://arxiv.org/abs/2607.04009) | arXiv'26 | 🗂️ Memory | Cross-task | Direct recording<br><sub>simulation</sub> |
| [**OmniQEC**: discovering practical quantum error-correcting codes by an AI scientist](https://arxiv.org/abs/2607.25865) | arXiv'26 | 🗂️ Memory | Within-project | Reflection<br><sub>formal, code, simulation</sub> |
| [**RSMeM**: Knowledge-Enhanced Memory Evolution for Remote Sensing Agents with Systematic Evaluation](https://arxiv.org/abs/2607.24772) | arXiv'26 | 🗂️ Memory | Within-project | Reflection<br><sub>code</sub> |
| [**AI CFD Scientist**: Toward Open-Ended Computational Fluid Dynamics Discovery with Physics-Aware AI Agents](https://arxiv.org/abs/2605.06607) | arXiv'26 | 🗂️ Memory | Within-project | Reflection, Direct recording<br><sub>code, simulation, LLM judge</sub> |

### 🧭 General Scientific Agent Frameworks

| Paper | Venue | What evolves | When | How (method · <sub>signal</sub>) |
|---|---|---|---|---|
| [Autonomous Agents Coordinating Distributed Discovery Through Emergent Artifact Exchange](https://arxiv.org/abs/2603.14312) | arXiv'26 | 🏗️ Architecture<br>💡 Knowledge<br>🗂️ Memory | Cross-task | Direct recording, Reflection, Search<br><sub>simulation, literature, LLM judge</sub> |
| [**SKILLFOUNDRY**: Building Self-Evolving Agent Skill Libraries from Heterogeneous Scientific Resources](https://arxiv.org/abs/2604.03964) | arXiv'26 | 🏗️ Architecture<br>🛠️ Toolkit | Training-time | Reflection<br><sub>code, literature, LLM judge</sub> |
| [Accelerating Scientific Discovery with Autonomous Goal-evolving Agents](https://arxiv.org/abs/2512.21782) | arXiv'25 | 🏗️ Architecture<br>🛠️ Toolkit<br>🗂️ Memory | Within-project | Reflection<br><sub>code, simulation, literature, LLM judge, human</sub> |
| [**El Agente Forjador**: Task-Driven Agent Generation for Quantum Simulation](https://arxiv.org/abs/2604.14609) | arXiv'26 | 🛠️ Toolkit | Training-time | Reflection<br><sub>code, LLM judge</sub> |
| [**S1-NexusAgent**: a Self-Evolving Agent Framework for Multidisciplinary Scientific Research](https://arxiv.org/abs/2602.01550) | arXiv'26 | 💡 Knowledge<br>🗂️ Memory | Cross-task | Reflection, Distillation<br><sub>LLM judge</sub> |
| [**FLEX**: Continuous Agent Evolution via Forward Learning from Experience](https://arxiv.org/abs/2511.06449) | arXiv'25 | 💡 Knowledge<br>🗂️ Memory | Training-time | Reflection, Distillation<br><sub>benchmark, LLM judge</sub> |
| [**EvoSCM**: Scientific Belief Revision Through Causal Model Evolution and Experimentation](https://arxiv.org/abs/2609.01526) | arXiv'26 | 💡 Knowledge<br>🗂️ Memory | Within-project | Direct recording, Reflection, Search, Optimization<br><sub>simulation</sub> |
| [**Large Discovery Models**: Empirically-grounded Model-Based Open-Ended Search](https://arxiv.org/abs/2608.15669) | arXiv'26 | 💡 Knowledge<br>🗂️ Memory | Within-project | Reflection, Distillation, Optimization<br><sub>simulation</sub> |
| [**LLM-AutoSciLab**: Closed-Loop Scientific Discovery via Active Experimentation with LLMs](https://arxiv.org/abs/2605.24043) | arXiv'26 | 💡 Knowledge<br>🗂️ Memory | Within-project | Direct recording<br><sub>simulation, benchmark</sub> |
| [**InternAgent-1.5**: A Unified Agentic Framework for Long-Horizon Autonomous Scientific Discovery](https://arxiv.org/abs/2602.08990) | arXiv'26 | 💡 Knowledge<br>🗂️ Memory | Within-project | Reflection, Direct recording<br><sub>code, benchmark</sub> |
| [**DrSR**: LLM based Scientific Equation Discovery with Dual Reasoning from Data and Experience](https://arxiv.org/abs/2506.04282) | arXiv'25 | 💡 Knowledge | Within-project | Reflection<br><sub>code, benchmark</sub> |
| [Bayesian Optimization for Biochemical Discovery with LLMs](https://doi.org/10.26434/chemrxiv-2025-w1wsh) | ChemRxiv'25 | 🗂️ Memory | Within-project | Reflection<br><sub>code, benchmark</sub> |
| [**ExLLM**: Experience-Enhanced LLM Optimization for Molecular Design and Beyond](https://arxiv.org/abs/2502.12845) | arXiv'25 |  | — | — |

## 🤝 Contributing

Contributions are welcome! To suggest a paper, open an issue or pull request with the link and point to where the paper shows:

1. what scaffold state is written back,
2. what feedback drives the update, and
3. where the updated state is read again.

<p align="center">⭐ If this list helps your research, please give it a star! ⭐</p>
