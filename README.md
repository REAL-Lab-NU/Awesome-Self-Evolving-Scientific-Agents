<h1 align="center">🧪 Awesome Self-Evolving Scientific Agents</h1>

<p align="center"><b>LLM agents that get better at science by learning from their own research.</b></p>

<div align="center">

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![Papers](https://img.shields.io/badge/papers-138-2a78d6)](#-paper-list)
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

- **[2026-10]** 🎉 Repository launched with **138 papers**, each labeled by what evolves, when, how, and where.

## 📑 Contents

- [🔍 What counts as self-evolving](#-what-counts-as-self-evolving)
- [📐 Taxonomy](#-taxonomy)
- [📊 At a glance](#-at-a-glance)
- [📚 Paper list](#-paper-list)
  - [🧬 Life Sciences](#-life-sciences) (55)
  - [🔬 Chemistry & Materials](#-chemistry--materials) (46)
  - [🌌 Physics, Earth & Space Sciences](#-physics-earth--space-sciences) (25)
  - [🧭 General Scientific Agent Frameworks](#-general-scientific-agent-frameworks) (12)
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

One table per domain, grouped by **When** (cross-task › training › within-project) and listed in order of release within each group.

- **What**: 🗂️ Memory · 💡 Knowledge · 🛠️ Toolkit · 🏗️ Architecture
- **How**: the main feedback signals that drive the update (up to two)
- **Code**: 💻 links to the official repository

 All labels, including feedback signals and update methods, are in [`data/papers.csv`](data/papers.csv).

### 🧬 Life Sciences

| Paper | Venue | When | What | How | Code |
|:---|:---:|:---:|:---:|:---|:---:|
| [**Chat Modeling**: Interaction-Enhanced Agent Framework for Visualizing Literature-Grounded Biological Structures](https://arxiv.org/abs/2404.01063) | arXiv<br><sub>2024.04</sub> | Cross-task | 🗂️ | Human |  |
| [Autonomous self-evolving research on biomedical data: the DREAM paradigm](https://arxiv.org/abs/2407.13637) | Advanced Science<br><sub>2024.07</sub> | Cross-task | 🛠️ | Code exec, LLM judge |  |
| [**Agentic Lab**: An Agentic-physical AI system for cell and organoid experimentation and manufacturing](https://doi.org/10.1101/2025.11.11.686354) | bioRxiv<br><sub>2025</sub> | Cross-task | 🗂️ 💡 | Wet lab, Literature |  |
| [**OriGene**: A Self-Evolving Virtual Disease Biologist Automating Therapeutic Target Discovery](https://doi.org/10.1101/2025.06.03.657658) | bioRxiv<br><sub>2025.06</sub> | Cross-task | 💡 | Wet lab, Human | [💻](https://github.com/GENTEL-lab/OriGene) |
| [**STELLA**: Self-Evolving LLM Agent for Biomedical Research](https://arxiv.org/abs/2507.02004) | arXiv<br><sub>2025.07</sub> | Cross-task | 💡 🛠️ | Code exec, LLM judge |  |
| [**STELLA**: Towards a Biomedical World Model with Self-Evolving Multimodal Agents](https://doi.org/10.1101/2025.07.01.662467) | bioRxiv<br><sub>2025.07</sub> | Cross-task | 💡 🛠️ | Wet lab, Code exec |  |
| [**GenCellAgent**: Generalizable, Training-Free Cellular Image Segmentation via Large Language Model Agents](https://arxiv.org/abs/2510.13896) | arXiv<br><sub>2025.10</sub> | Cross-task | 🗂️ | Human, LLM judge | [💻](https://github.com/yuxi120407/GenCELLAgent) |
| [**LabOS**: The AI-XR Co-Scientist That Sees and Works With Humans](https://arxiv.org/abs/2510.14861) | bioRxiv<br><sub>2025.10</sub> | Cross-task | 🗂️ 🛠️ | Wet lab, Code exec |  |
| [**RareAgent**: Self-Evolving Reasoning for Drug Repurposing in Rare Diseases](https://arxiv.org/abs/2510.05764) | arXiv<br><sub>2025.10</sub> | Cross-task | 💡 🏗️ | LLM judge |  |
| [A Persistent Fleet of AI Scientists Exhibits Cooperative and Autopoietic Behavior](https://doi.org/10.64898/2026.08.16.745122) | bioRxiv<br><sub>2026</sub> | Cross-task | 🗂️ 💡 🏗️ | Code exec, Benchmark |  |
| [**PantheonOS**: An Evolvable Multi-Agent Framework for Automatic Genomics Discovery](https://doi.org/10.64898/2026.02.26.707870) | bioRxiv<br><sub>2026.02</sub> | Cross-task | 💡 🛠️ | Code exec, Benchmark | [💻](https://github.com/aristoteleo/pantheonos-reproducibility) |
| [Empowering AI data scientists using a multi-agent LLM framework with self-evolving capabilities for autonomous, tool-aware biomedical data analyses](https://doi.org/10.1038/s41551-026-01634-6) | Nature Biomedical Engineering<br><sub>2026.03</sub> | Cross-task | 🗂️ | Code exec |  |
| [**HarmonyCell**: Automating Single-Cell Perturbation Modeling under Semantic and Distribution Shifts](https://arxiv.org/abs/2603.01396) | arXiv<br><sub>2026.03</sub> | Cross-task | 🗂️ | Code exec, Benchmark |  |
| [Self-evolving AI agents for protein discovery and directed evolution](https://arxiv.org/abs/2603.27303) | arXiv<br><sub>2026.03</sub> | Cross-task | 🛠️ | Code exec, Benchmark | [💻](https://github.com/ai4protein/VenusFactory2) |
| [**SpatialClaw**: A Memory-Augmented Autonomous Ecosystem for Spatial Omics Analysis](https://doi.org/10.64898/2026.05.21.723451) | bioRxiv<br><sub>2026.05</sub> | Cross-task | 🗂️ 💡 | Code exec, Human | [💻](https://github.com/ShangBioLab/SpatialClaw) |
| [A Self-Evolving Agentic System for Automated Generation and Execution of Biological Protocols](https://arxiv.org/abs/2606.31763) | arXiv<br><sub>2026.06</sub> | Cross-task | 🗂️ 💡 | Wet lab, Code exec |  |
| [**Agri-SAGE**: Simulation-Grounded Multi-Agent LLM for Context-Aware Agricultural Advisory Generation](https://arxiv.org/abs/2607.00454) | arXiv<br><sub>2026.07</sub> | Cross-task | 🗂️ 💡 | Simulation |  |
| [**EasyBCI Agent**: Towards Universal Neural Data Preprocessing for Brain-Computer Interfaces](https://arxiv.org/abs/2607.29007) | arXiv<br><sub>2026.07</sub> | Cross-task | 🗂️ | Code exec, Human |  |
| [**ReCo**: a self-configuring and self-extending agentic framework for biomedical research](https://doi.org/10.64898/2026.07.14.26358025) | medRxiv<br><sub>2026.07</sub> | Cross-task | 🛠️ | Code exec, Human | [💻](https://github.com/eltzanis/ReCo) |
| [**SpaCellAgent**: A Self-Evolving LLM-Based Multi-Agent Framework for Trajectory Analysis](https://arxiv.org/abs/2607.07467) | KDD<br><sub>2026.07</sub> | Cross-task | 🗂️ 🛠️ | Code exec, Literature | [💻](https://github.com/LittleXH-shw/SpaCellAgent) |
| [**ADMET-EvO**: a self-evolving scientific agent for sustained research across heterogeneous tasks](https://arxiv.org/abs/2609.10121) | arXiv<br><sub>2026.09</sub> | Cross-task | 🗂️ 💡 🏗️ | Code exec, Benchmark |  |
| [An autonomous agentic framework for cross-campaign generalization and sensor shift adaptation](https://doi.org/10.1088/2632-2153/ae9fb7) | Machine Learning: Science and Technology<br><sub>2026.09</sub> | Cross-task | 🗂️ 💡 | Code exec, Benchmark |  |
| [**Paper2Agent**: Reimagining Research Papers As Interactive and Reliable AI Agents](https://arxiv.org/abs/2509.06917) | Nature<br><sub>2025.09</sub> | Training | 🛠️ | Code exec | [💻](https://github.com/jmiao24/Paper2Agent) |
| [**ToolUniverse**: An open platform for democratizing AI scientists](https://arxiv.org/abs/2509.23426) | arXiv<br><sub>2025.09</sub> | Training | 🛠️ | Code exec, Literature | [💻](https://github.com/mims-harvard/ToolUniverse) |
| [**MDAgent**: A Multi-Agent Framework for End-to-End Molecular Dynamics Research](https://arxiv.org/abs/2604.18622) | arXiv<br><sub>2026.04</sub> | Training | 🗂️ 💡 | Simulation, Code exec |  |
| [**DrugSAGE**: Self-evolving Agent Experience for Efficient State-of-the-Art Drug Discovery](https://arxiv.org/abs/2605.15461) | arXiv<br><sub>2026.05</sub> | Training | 🗂️ 🛠️ | Code exec, Benchmark |  |
| [**PRAXIS**: Case-distilled and code-verified AI agents for biological research](https://arxiv.org/abs/2605.23169) | arXiv<br><sub>2026.05</sub> | Training | 🗂️ 💡 🛠️ | Code exec, Literature |  |
| [Process-Reward Tactic Evolution for Long-Horizon Bioinformatics Workflows](https://arxiv.org/abs/2606.20839) | arXiv<br><sub>2026.06</sub> | Training | 💡 | Code exec, Benchmark |  |
| [**SSE-Bio**: A Structured Self-Evolving Agent with Agentic Retrieval Policy for Multi-Hop Biomedical Reasoning](https://arxiv.org/abs/2608.22132) | arXiv<br><sub>2026.08</sub> | Training | 💡 | LLM judge | [💻](https://github.com/ZhaohanM/SSE-Bio) |
| [**VCAgent**: A Mutation-Guided Self-Reflective Agent Framework for Virtual Cell Modeling](https://doi.org/10.1145/3770855.3818989) | KDD<br><sub>2026.08</sub> | Training | 🏗️ | Benchmark | [💻](https://github.com/LZYBUPT/VCAgent) |
| [**LabAgent**: Customize Any Research Hubs for Scientific Discoveries Using AI Agents](https://arxiv.org/abs/2609.13437) | arXiv<br><sub>2026.09</sub> | Training | 🗂️ 🛠️ | Code exec, LLM judge | [💻](https://github.com/fpxlei/LabAgent) |
| [**Vestrum**: Improving Agent Harnesses by Adapting Their Verification, Structure and Memory](https://arxiv.org/abs/2609.33822) | arXiv<br><sub>2026.09</sub> | Training | 💡 🛠️ | Benchmark, LLM judge |  |
| [**BioDiscoveryAgent**: An AI Agent for Designing Genetic Perturbation Experiments](https://arxiv.org/abs/2405.17631) | ICLR<br><sub>2024.05</sub> | Within-project | 💡 | Benchmark, Literature |  |
| [Accelerating scientific discovery with Co-Scientist](https://arxiv.org/abs/2502.18864) | Nature<br><sub>2025.02</sub> | Within-project | 💡 🏗️ | Literature, LLM judge |  |
| [**Robin**: A multi-agent system for automating scientific discovery](https://arxiv.org/abs/2505.13400) | Nature<br><sub>2025.05</sub> | Within-project | 🗂️ 💡 🏗️ | Wet lab, Human |  |
| [**AutoDiscovery**: Open-ended Scientific Discovery via Bayesian Surprise](https://arxiv.org/abs/2507.00310) | NeurIPS<br><sub>2025.06</sub> | Within-project | 🗂️ | Code exec, Benchmark | [💻](https://github.com/allenai/autodiscovery-neurips) |
| [**Aleks**: AI powered Multi Agent System for Autonomous Scientific Discovery via Data-Driven Approaches in Plant Science](https://arxiv.org/abs/2508.19383) | arXiv<br><sub>2025.08</sub> | Within-project | 🗂️ | Code exec, Benchmark |  |
| [**TusoAI**: Agentic Optimization for Scientific Methods](https://arxiv.org/abs/2509.23986) | arXiv<br><sub>2025.09</sub> | Within-project | 🗂️ 🏗️ | Code exec, Benchmark | [💻](https://github.com/Alistair-Turcan/TusoAI) |
| [Hypothesis Hunting with Evolving Networks of Autonomous Scientific Agents](https://arxiv.org/abs/2510.08619) | arXiv<br><sub>2025.10</sub> | Within-project | 🗂️ 🏗️ | Code exec, LLM judge |  |
| [**Kosmos**: An AI Scientist for Autonomous Discovery](https://arxiv.org/abs/2511.02824) | arXiv<br><sub>2025.11</sub> | Within-project | 🗂️ 💡 | Code exec, Literature |  |
| [Swarms of Large Language Model Agents for Protein Sequence Design with Experimental Validation](https://arxiv.org/abs/2511.22311) | arXiv<br><sub>2025.11</sub> | Within-project | 🗂️ 💡 | Simulation | [💻](https://github.com/lamm-mit/ProteinSwarm) |
| [**The Station**: An Open-World Environment for AI-Driven Discovery](https://arxiv.org/abs/2511.06309) | arXiv<br><sub>2025.11</sub> | Within-project | 🗂️ 💡 🛠️ 🏗️ | Code exec, Benchmark | [💻](https://github.com/dualverse-ai/station) |
| [**MARBLE**: Multi-Agent Reasoning for Bioinformatics Learning and Evolution](https://arxiv.org/abs/2601.14349) | arXiv<br><sub>2026.01</sub> | Within-project | 🗂️ 💡 | Code exec, Benchmark | [💻](https://github.com/PRISM-DGU/MARBLE) |
| [**MAC-AMP**: A Closed-Loop Multi-Agent Collaboration System for Multi-Objective Antimicrobial Peptide Design](https://arxiv.org/abs/2602.14926) | arXiv<br><sub>2026.02</sub> | Within-project | 🗂️ 🛠️ 🏗️ | Simulation, Code exec | [💻](https://github.com/CLMFAP/MAC-AMP_v1) |
| [Using a GPT-5-driven autonomous lab to optimize the cost and titer of cell-free protein synthesis](https://doi.org/10.64898/2026.02.05.703998) | bioRxiv<br><sub>2026.02</sub> | Within-project | 🗂️ | Wet lab |  |
| [**ASI-Evolve**: AI Accelerates AI](https://arxiv.org/abs/2603.29640) | arXiv<br><sub>2026.03</sub> | Within-project | 🗂️ | Code exec, Benchmark | [💻](https://github.com/GAIR-NLP/ASI-Evolve) |
| [Can AI Scientist Agents Learn from Lab-in-the-Loop Feedback? Evidence from Iterative Perturbation Discovery](https://arxiv.org/abs/2603.26177) | arXiv<br><sub>2026.03</sub> | Within-project | 💡 | Benchmark |  |
| [**AutoScientists**: Self-Organizing Agent Teams for Long-Running Scientific Experimentation](https://arxiv.org/abs/2605.28655) | arXiv<br><sub>2026.05</sub> | Within-project | 🗂️ 💡 🏗️ | Code exec, Benchmark | [💻](https://github.com/mims-harvard/AutoScientists) |
| [**SIA**: Self Improving AI with Harness & Weight Updates](https://arxiv.org/abs/2605.27276) | arXiv<br><sub>2026.05</sub> | Within-project | 🛠️ 🏗️ | Code exec, Benchmark |  |
| [Autonomous Scientific Discovery via Iterative Meta-Reflection](https://arxiv.org/abs/2607.01131) | arXiv<br><sub>2026.07</sub> | Within-project | 🗂️ 💡 | Code exec, Benchmark |  |
| [**Networked Intelligence**: Active Shared Context Graphs for Human-AI Team Science](https://arxiv.org/abs/2607.13220) | arXiv<br><sub>2026.07</sub> | Within-project | 🗂️ 💡 | Wet lab, Code exec |  |
| [Accelerating Scientific Research with Gemini in the Real-World](https://arxiv.org/abs/2608.26701) | arXiv<br><sub>2026.08</sub> | Within-project | 💡 | Code exec, LLM judge |  |
| [**AgentFold**: Closed-Loop Agentic Search for Protein Folding Model Design](https://arxiv.org/abs/2608.26747) | arXiv<br><sub>2026.08</sub> | Within-project | 🗂️ 💡 | Code exec, Benchmark | [💻](https://github.com/lmqfly/AgentFold) |
| [**BioDyad**: Synchronize Biomedical Discovery and Machine Learning Engineering](https://arxiv.org/abs/2609.31939) | arXiv<br><sub>2026.09</sub> | Within-project | 🗂️ | Code exec, Benchmark |  |
| [Harnessing AI to Build Virtual Cells](https://doi.org/10.64898/2026.04.11.717183) | bioRxiv<br><sub>2026.4.</sub> | Within-project | 🗂️ | Code exec, Benchmark |  |

### 🔬 Chemistry & Materials

| Paper | Venue | When | What | How | Code |
|:---|:---:|:---:|:---:|:---|:---:|
| [**TopoMAS**: Large Language Model Driven Topological Materials Multiagent System](https://arxiv.org/abs/2507.04053) | arXiv<br><sub>2025.07</sub> | Cross-task | 🗂️ | Simulation, LLM judge |  |
| [Operating advanced scientific instruments with AI agents that learn on the job](https://arxiv.org/abs/2509.00098) | npj Computational Materials<br><sub>2025.08</sub> | Cross-task | 🗂️ | Human |  |
| [**CASCADE**: Cumulative Agentic Skill Creation through Autonomous Development and Evolution](https://arxiv.org/abs/2512.23880) | arXiv<br><sub>2025.12</sub> | Cross-task | 🗂️ 💡 | Human | [💻](https://github.com/CederGroupHub/CASCADE) |
| [Discovering physical mechanisms from experiment-simulation mismatches](https://arxiv.org/abs/2604.26703) | arXiv<br><sub>2026.04</sub> | Cross-task | 💡 🛠️ | Simulation, Benchmark |  |
| [Long-Term Memory for VLA-based Agents in Open-World Task Execution](https://arxiv.org/abs/2604.15671) | arXiv<br><sub>2026.04</sub> | Cross-task | 🗂️ | Human |  |
| [Agentic generation of verifiable rules for deterministic, self-expanding reaction classification](https://arxiv.org/abs/2607.01061) | arXiv<br><sub>2026.07</sub> | Cross-task | 💡 | LLM judge |  |
| [Harnessing agent memory to build lifelong AI partners for materials scientists](https://arxiv.org/abs/2608.11224) | arXiv<br><sub>2026.07</sub> | Cross-task | 🗂️ 💡 | Simulation, Code exec |  |
| [**LabEvolver**: Training-Free Experience Evolution for Safe and Grounded Wet-Lab Agents](https://arxiv.org/abs/2607.27690) | arXiv<br><sub>2026.07</sub> | Cross-task | 🗂️ 💡 | Wet lab, Benchmark |  |
| [**MolecureAI**: an agentic AI platform for autonomous drug discovery](https://doi.org/10.3389/fphar.2026.1917774) | Frontiers in Pharmacology<br><sub>2026.09</sub> | Cross-task | 🗂️ 💡 | Simulation, Code exec |  |
| [**ChemAgent**: Self-updating Library in Large Language Models Improves Chemical Reasoning](https://arxiv.org/abs/2501.06590) | arXiv<br><sub>2025.01</sub> | Training | 🗂️ | Benchmark, LLM judge | [💻](https://github.com/gersteinlab/ChemAgent) |
| [**ChemHTS**: Hierarchical Tool Stacking for Enhancing Chemical Agents](https://arxiv.org/abs/2502.14327) | arXiv<br><sub>2025.02</sub> | Training | 🛠️ 🏗️ | Benchmark | [💻](https://github.com/Chang-pw/ChemAmp) |
| [**ChemAmp**: Amplified Chemistry Tools via Composable Agents](https://arxiv.org/abs/2505.21569) | arXiv<br><sub>2025.05</sub> | Training | 🛠️ 🏗️ | Benchmark | [💻](https://github.com/Chang-pw/ChemAmp) |
| [Autonomous Multi-objective Alloy Design through Simulation-guided Optimization](https://arxiv.org/abs/2507.16005) | arXiv<br><sub>2025.07</sub> | Training | 🛠️ | Simulation, Literature | [💻](https://github.com/penghui-yang/AutoMAT) |
| [**Feedback to Reasoning**: LLM-Assisted Molecular Optimization with Domain Feedback and Historical Reasoning](https://doi.org/10.18653/v1/2026.findings-acl.619) | Findings of ACL<br><sub>2026</sub> | Training | 🗂️ 💡 | Simulation | [💻](https://github.com/wenhangao21/ACL2026-F2R) |
| [**AgentCAT**: An LLM Agent for Extracting and Analyzing Catalytic Reaction Data from Chemical Engineering Literature](https://arxiv.org/abs/2602.18479) | arXiv<br><sub>2026.02</sub> | Training | 🏗️ | Literature, Human |  |
| [**MolMem**: Memory-Augmented Agentic Reinforcement Learning for Sample-Efficient Molecular Optimization](https://arxiv.org/abs/2604.12237) | ACL<br><sub>2026.04</sub> | Training | 💡 | Simulation | [💻](https://github.com/REAL-Lab-NU/MolMem) |
| [Autonomous heterogeneous catalyst discovery with a self-evolving multi-agent digital twin](https://arxiv.org/abs/2606.05050) | arXiv<br><sub>2026.06</sub> | Training | 🗂️ 💡 🏗️ | Simulation, Code exec |  |
| [Fantastic Scientific Agents and How to Build Them: AgentBuild for Rietveld Refinement](https://arxiv.org/abs/2606.12834) | arXiv<br><sub>2026.06</sub> | Training | 💡 🏗️ | Simulation, Code exec |  |
| [**S3C-LLM**: Skill-Code Guided Agentic Language Models for Spectrum-to-Structure Elucidation](https://arxiv.org/abs/2608.30910) | arXiv<br><sub>2026.08</sub> | Training | 💡 | Benchmark |  |
| [**LLMatDesign**: Autonomous Materials Discovery with Large Language Models](https://arxiv.org/abs/2406.13163) | arXiv<br><sub>2024.06</sub> | Within-project | 🗂️ | Simulation |  |
| [A Multi-agent Framework for Physical Laws Discovery](https://arxiv.org/abs/2411.16416) | arXiv<br><sub>2024.11</sub> | Within-project | 🗂️ | Code exec, Benchmark |  |
| [**ExLLM**: Experience-Enhanced LLM Optimization for Molecular Design and Beyond](https://arxiv.org/abs/2502.12845) | arXiv<br><sub>2025.02</sub> | Within-project | 💡 | Simulation | [💻](https://github.com/HuskyNian/ExLLM) |
| [**PharmAgents**: Building a Virtual Pharma with Large Language Model Agents](https://arxiv.org/abs/2503.22164) | arXiv<br><sub>2025.03</sub> | Within-project | 🗂️ | Simulation, LLM judge |  |
| [Accelerated Inorganic Materials Design with Generative AI Agents](https://arxiv.org/abs/2504.00741) | Cell Reports Physical Science<br><sub>2025.04</sub> | Within-project | 🗂️ | Simulation | [💻](https://github.com/izumitkhr/matagent) |
| [**Reasoning BO**: Enhancing Bayesian Optimization with Long-Context Reasoning Power of LLMs](https://arxiv.org/abs/2505.12833) | arXiv<br><sub>2025.05</sub> | Within-project | 🗂️ 💡 | Benchmark, LLM judge |  |
| [Human-AI collaborative autonomous synthesis with pulsed laser deposition for remote epitaxy](https://arxiv.org/abs/2511.11558) | Research Square<br><sub>2025.11</sub> | Within-project | 🛠️ | Wet lab, Code exec |  |
| [Autonomous computational catalysis through an agentic research system](https://arxiv.org/abs/2601.13508) | arXiv<br><sub>2026.01</sub> | Within-project | 🗂️ 💡 🛠️ | Simulation, Code exec | [💻](https://github.com/q734738781/CatMaster) |
| [**ChemNavigator**: Agentic AI Discovery of Design Rules for Organic Photocatalysts](https://arxiv.org/abs/2601.17084) | arXiv<br><sub>2026.01</sub> | Within-project | 💡 | Simulation |  |
| [Reasoning-Driven Design of Single Atom Catalysts via a Multi-Agent Large Language Model Framework](https://arxiv.org/abs/2602.21533) | arXiv<br><sub>2026.02</sub> | Within-project | 🗂️ 💡 | Simulation, LLM judge |  |
| [**AI4S-SDS**: A Neuro-Symbolic Solvent Design System via Sparse MCTS and Differentiable Physics Alignment](https://arxiv.org/abs/2603.03686) | arXiv<br><sub>2026.03</sub> | Within-project | 🗂️ 💡 | Simulation, LLM judge |  |
| [Constraint-Aware Corrective Memory for Language-Based Drug Discovery Agents](https://arxiv.org/abs/2604.09308) | arXiv<br><sub>2026.04</sub> | Within-project | 🗂️ | Simulation, LLM judge |  |
| [Agentic Design of Compositional Descriptors via Autoresearch for Materials Science Applications](https://arxiv.org/abs/2605.14671) | arXiv<br><sub>2026.05</sub> | Within-project | 🗂️ | Benchmark |  |
| [Agentic Discovery of Exchange-Correlation Density Functionals](https://arxiv.org/abs/2605.05460) | arXiv<br><sub>2026.05</sub> | Within-project | 🗂️ 💡 | Simulation, Benchmark |  |
| [**Battery-Sim-Agent**: Leveraging LLM-Agent for Inverse Battery Parameter Estimation](https://arxiv.org/abs/2605.29560) | KDD<br><sub>2026.05</sub> | Within-project | 🗂️ 💡 | Simulation, Benchmark | [💻](https://github.com/opqrst-chen/Battery-Sim-Agent) |
| [**Probe Before You Edit**: Probing-Guided Molecular Optimization for LLM Agents in Structure-Based Drug Design](https://arxiv.org/abs/2606.00555) | arXiv<br><sub>2026.05</sub> | Within-project | 🗂️ 💡 | Simulation |  |
| [Towards Discovery of Polymers for Insulin Delivery via Physics-Grounded Agentic Workflows](https://arxiv.org/abs/2605.18831) | arXiv<br><sub>2026.05</sub> | Within-project | 🗂️ 💡 | Simulation, Code exec |  |
| [Interpretable Inverse Design of Metal-Organic Frameworks with Large Language Model Agents](https://arxiv.org/abs/2606.29459) | arXiv<br><sub>2026.06</sub> | Within-project | 🗂️ 💡 | Simulation, Benchmark | [💻](https://github.com/kn1218/LLM4MOF) |
| [**My Chemical Harness**: Evolutionary Molecular Design over Synthetic Pathways with Large Language Model Agents](https://arxiv.org/abs/2606.11256) | arXiv<br><sub>2026.06</sub> | Within-project | 🗂️ 💡 | Simulation, Code exec |  |
| [**NISPO**: Open-source IUPAC name generation tool](https://arxiv.org/abs/2607.26113) | arXiv<br><sub>2026.07</sub> | Within-project | 🏗️ | Code exec, Benchmark | [💻](https://github.com/oxpig/nispo) |
| [Symbolic Predicate-Guided Language Agents for Inverse Design of Perovskite Oxides](https://arxiv.org/abs/2607.15535) | arXiv<br><sub>2026.07</sub> | Within-project | 💡 | Simulation, Code exec |  |
| [Toward Auditable AI Scientists: A Hypothesis Evolution Protocol for LLM Agents](https://arxiv.org/abs/2607.09195) | arXiv<br><sub>2026.07</sub> | Within-project | 🗂️ 💡 | Simulation, Code exec |  |
| [From Human Hypotheses to LLM Insights: Advancing Bayesian Optimisation for Autonomous Scientific Discovery](https://livrepository.liverpool.ac.uk/3197318/) | PhD thesis, University of Liverpool<br><sub>2026.08</sub> | Within-project | 💡 🏗️ | Simulation, Human |  |
| [AI-guided high-throughput discovery of iridium- and ruthenium-free palladium-oxide catalysts for durable acidic oxygen evolution](https://arxiv.org/abs/2609.30133) | arXiv<br><sub>2026.09</sub> | Within-project | 💡 | Wet lab |  |
| [Autonomous discovery of new structure-plausibility laws for explainable and rapid crystal diagnosis and screening](https://arxiv.org/abs/2609.01209) | arXiv<br><sub>2026.09</sub> | Within-project | 🗂️ 🛠️ | Simulation, Code exec |  |
| [Human-agent discovery of reconfigurable in-plane ferroelectric superdomain control](https://arxiv.org/abs/2609.06887) | arXiv<br><sub>2026.09</sub> | Within-project | 🗂️ 💡 🛠️ 🏗️ | Wet lab, Code exec |  |
| [Hypothesis-Driven Autonomous Materials Synthesis with Multimodal LLM Agents](https://arxiv.org/abs/2609.18598) | arXiv<br><sub>2026.09</sub> | Within-project | 💡 🛠️ | Wet lab, Code exec |  |

### 🌌 Physics, Earth & Space Sciences

| Paper | Venue | When | What | How | Code |
|:---|:---:|:---:|:---:|:---|:---:|
| [Interpreting Multi-band Galaxy Observations with Large Language Model-Based Agents](https://arxiv.org/abs/2409.14807) | NeurIPS ML4PS Workshop<br><sub>2024.09</sub> | Cross-task | 💡 | Simulation, Benchmark |  |
| [**CangLing-KnowFlow**: A Unified Knowledge-and-Flow-fused Agent for Comprehensive Remote Sensing Applications](https://arxiv.org/abs/2512.15231) | arXiv<br><sub>2025.12</sub> | Cross-task | 💡 | Code exec |  |
| [**PhysMaster**: Building an Autonomous AI Physicist for Theoretical and Computational Physics Research](https://arxiv.org/abs/2512.19799) | arXiv<br><sub>2025.12</sub> | Cross-task | 🗂️ 💡 | Code exec, LLM judge | [💻](https://github.com/sjtu-sai-agents/PhysMaster) |
| [Experience-Driven Multi-Agent Systems Are Training-free Context-aware Earth Observers](https://arxiv.org/abs/2602.02559) | arXiv<br><sub>2026.01</sub> | Cross-task | 💡 | Code exec, LLM judge |  |
| [From Experiments to Expertise: Scientific Knowledge Consolidation for AI-Driven Computational Physics](https://arxiv.org/abs/2603.13191) | arXiv<br><sub>2026.03</sub> | Cross-task | 🗂️ 💡 | Simulation, Code exec | [💻](https://github.com/QMatSuite/QMatSuite) |
| [End-to-end autonomous scientific discovery on a real optical platform](https://arxiv.org/abs/2604.27092) | arXiv<br><sub>2026.04</sub> | Cross-task | 🗂️ 💡 | Wet lab, Simulation |  |
| [**GRAFT-ATHENA**: Self-Improving Agentic Teams for Autonomous Discovery and Evolutionary Numerical Algorithms](https://arxiv.org/abs/2605.11117) | arXiv<br><sub>2026.05</sub> | Cross-task | 🗂️ 💡 🏗️ | Formal, Simulation |  |
| [LLM-Driven Cross-Paradigm Design for Quantum Optimal Control](https://arxiv.org/abs/2607.17498) | arXiv<br><sub>2026.07</sub> | Cross-task | 🗂️ 💡 | Simulation |  |
| [**PhysMiner**: An Agentic AI Framework for Automated Flow Component Analysis](https://arxiv.org/abs/2607.04009) | arXiv<br><sub>2026.07</sub> | Cross-task | 🗂️ | Simulation | [💻](https://github.com/iDesign-Lab/PhysMiner) |
| [Deploying Frontier Agentic Technology in MOOSEnger, a Multiphysics-Capable AI Assistant](https://arxiv.org/abs/2608.15881) | arXiv<br><sub>2026.08</sub> | Cross-task | 🗂️ 💡 | Code exec, Human |  |
| [**GeoForge**: Non-Parametric Self-Evolving Agents for Earth-Observation Reasoning](https://arxiv.org/abs/2608.10494) | arXiv<br><sub>2026.08</sub> | Cross-task | 🗂️ 💡 🏗️ | Code exec, LLM judge |  |
| [**Mephisto**: Self-Improving Large Language Model-Based Agents for Automated Interpretation of Multi-band Galaxy Observations](https://arxiv.org/abs/2510.08354) | The Astrophysical Journal Supplement Series<br><sub>2025.10</sub> | Training | 💡 | Simulation, Benchmark |  |
| [MadAgents](https://arxiv.org/abs/2601.21015) | arXiv<br><sub>2026.01</sub> | Training | 💡 | Code exec, LLM judge | [💻](https://github.com/MadGraphTeam/MadAgents) |
| [**TimeClaw**: A Time-Series AI Agent with Exploratory Execution Learning](https://arxiv.org/abs/2605.10038) | arXiv<br><sub>2026.05</sub> | Training | 💡 | Benchmark |  |
| [Auto-Configuring Scientific Simulators with Lightweight Coding-Agent Adapters](https://arxiv.org/abs/2606.09774) | arXiv<br><sub>2026.06</sub> | Training | 💡 🏗️ | Benchmark |  |
| [CLVisc Agent for autonomous relativistic hydrodynamics studies](https://arxiv.org/abs/2607.27822) | arXiv<br><sub>2026.07</sub> | Training | 🛠️ | Code exec, Human |  |
| [**GeoSkill**: Experience-Driven Hierarchical Skill Learning with Collaborative Revision for Geospatial Agents](https://arxiv.org/abs/2609.13667) | arXiv<br><sub>2026.09</sub> | Training | 💡 | Code exec, Benchmark |  |
| [Recursive self-improvement of AI research agents](https://arxiv.org/abs/2609.26457) | arXiv<br><sub>2026.09</sub> | Training | 🏗️ | Code exec, Benchmark |  |
| [**AI CFD Scientist**: Toward Open-Ended Computational Fluid Dynamics Discovery with Physics-Aware AI Agents](https://arxiv.org/abs/2605.06607) | arXiv<br><sub>2026.05</sub> | Within-project | 🗂️ | Simulation, Code exec | [💻](https://github.com/csml-rpi/AI-CFD-Scientist) |
| [Toward General Quantum Control with Physics-Informed Large Language Models](https://arxiv.org/abs/2605.26021) | arXiv<br><sub>2026.05</sub> | Within-project | 💡 | Simulation |  |
| [**RSMeM**: Knowledge-Enhanced Memory Evolution for Remote Sensing Agents with Systematic Evaluation](https://arxiv.org/abs/2607.24772) | arXiv<br><sub>2026.06</sub> | Within-project | 🗂️ | Code exec |  |
| [Socratic agents for autonomous scientific discovery in high-dimensional physical systems](https://arxiv.org/abs/2606.26722) | arXiv<br><sub>2026.06</sub> | Within-project | 💡 | Wet lab, Human |  |
| [**OmniQEC**: discovering practical quantum error-correcting codes by an AI scientist](https://arxiv.org/abs/2607.25865) | arXiv<br><sub>2026.07</sub> | Within-project | 🗂️ | Formal, Simulation |  |
| [**Eureka**: Task-Conditioned Meta-Agent Orchestration for Scientific Discovery](https://arxiv.org/abs/2608.19047) | arXiv<br><sub>2026.08</sub> | Within-project | 🗂️ 🏗️ | Code exec | [💻](https://github.com/manxis-contact/Eureka) |
| [Multi-agent discovery of practical quantum LDPC codes](https://arxiv.org/abs/2608.08996) | arXiv<br><sub>2026.08</sub> | Within-project | 🗂️ 💡 | Formal, Code exec |  |

### 🧭 General Scientific Agent Frameworks

| Paper | Venue | When | What | How | Code |
|:---|:---:|:---:|:---:|:---|:---:|
| [**S1-NexusAgent**: a Self-Evolving Agent Framework for Multidisciplinary Scientific Research](https://arxiv.org/abs/2602.01550) | arXiv<br><sub>2026.02</sub> | Cross-task | 🗂️ 💡 | LLM judge | [💻](https://github.com/CASIA-LM/S1-NexusAgent) |
| [Autonomous Agents Coordinating Distributed Discovery Through Emergent Artifact Exchange](https://arxiv.org/abs/2603.14312) | arXiv<br><sub>2026.03</sub> | Cross-task | 🗂️ 💡 🏗️ | Simulation, Literature | [💻](https://github.com/lamm-mit/scienceclaw) |
| [**FLEX**: Continuous Agent Evolution via Forward Learning from Experience](https://arxiv.org/abs/2511.06449) | arXiv<br><sub>2025.11</sub> | Training | 🗂️ 💡 | Benchmark, LLM judge |  |
| [**El Agente Forjador**: Task-Driven Agent Generation for Quantum Simulation](https://arxiv.org/abs/2604.14609) | arXiv<br><sub>2026.04</sub> | Training | 🛠️ | Code exec, LLM judge |  |
| [**SKILLFOUNDRY**: Building Self-Evolving Agent Skill Libraries from Heterogeneous Scientific Resources](https://arxiv.org/abs/2604.03964) | arXiv<br><sub>2026.04</sub> | Training | 🛠️ 🏗️ | Code exec, Literature | [💻](https://github.com/ma-compbio-lab/SkillFoundry) |
| [**DrSR**: LLM based Scientific Equation Discovery with Dual Reasoning from Data and Experience](https://arxiv.org/abs/2506.04282) | arXiv<br><sub>2025.06</sub> | Within-project | 💡 | Code exec, Benchmark |  |
| [Bayesian Optimization for Biochemical Discovery with LLMs](https://doi.org/10.26434/chemrxiv-2025-w1wsh) | ChemRxiv<br><sub>2025.11</sub> | Within-project | 🗂️ | Code exec, Benchmark |  |
| [Accelerating Scientific Discovery with Autonomous Goal-evolving Agents](https://arxiv.org/abs/2512.21782) | arXiv<br><sub>2025.12</sub> | Within-project | 🗂️ 🛠️ 🏗️ | Simulation, Code exec | [💻](https://github.com/btyu/SAGA) |
| [**InternAgent-1.5**: A Unified Agentic Framework for Long-Horizon Autonomous Scientific Discovery](https://arxiv.org/abs/2602.08990) | arXiv<br><sub>2026.02</sub> | Within-project | 🗂️ 💡 | Code exec, Benchmark | [💻](https://github.com/InternScience/InternAgent) |
| [**LLM-AutoSciLab**: Closed-Loop Scientific Discovery via Active Experimentation with LLMs](https://arxiv.org/abs/2605.24043) | arXiv<br><sub>2026.05</sub> | Within-project | 🗂️ 💡 | Simulation, Benchmark | [💻](https://github.com/scientific-discovery/LLM-AutoSciLab) |
| [**Large Discovery Models**: Empirically-grounded Model-Based Open-Ended Search](https://arxiv.org/abs/2608.15669) | arXiv<br><sub>2026.08</sub> | Within-project | 🗂️ 💡 | Simulation | [💻](https://github.com/yzailab/Large-Discovery-Models) |
| [**EvoSCM**: Scientific Belief Revision Through Causal Model Evolution and Experimentation](https://arxiv.org/abs/2609.01526) | arXiv<br><sub>2026.09</sub> | Within-project | 🗂️ 💡 | Simulation |  |

## 🤝 Contributing

Contributions are welcome! To suggest a paper, open an issue or pull request with the link and point to where the paper shows:

1. what scaffold state is written back,
2. what feedback drives the update, and
3. where the updated state is read again.

<p align="center">⭐ If this list helps your research, please give it a star! ⭐</p>
