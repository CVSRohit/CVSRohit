<div align="center">

# Rohit Challa

### AI Researcher · Graph ML · Knowledge Systems

<p align="center">
  <i>Introduced the Anti-GraphRAG paradigm — surfacing what's absent in a knowledge graph, not just what's present.<br/>
  Working on the intersection of graph machine learning, contrastive learning, and applied decision intelligence.</i>
</p>

[![void-graph](https://img.shields.io/badge/void--graph-Anti--GraphRAG-10b981?style=for-the-badge&logo=github&logoColor=white)](https://github.com/CVSRohit/void-graph)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Rohit_Challa-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/rohitchalla)
[![Portfolio](https://img.shields.io/badge/Portfolio-rohitchalla.com-3B82F6?style=for-the-badge&logo=google-chrome&logoColor=white)](https://rohitchalla.com)

</div>

---

## Anti-GraphRAG · void-graph

> *Where GraphRAG asks "what's connected?" — Anti-GraphRAG asks "what's missing, and does it matter?"*

I introduced **Anti-GraphRAG**: an inversion of the standard GraphRAG retrieval paradigm that surfaces *absent* edges in a knowledge graph rather than present ones. The core insight is that meaningful absence — a missing drug-target interaction, an undocumented threat actor technique, an unlinked regulatory obligation — often carries more signal than what the graph already contains.

**How it works:**
1. Construct a domain knowledge graph and freeze it at time T
2. Train ComplEx embeddings on the frozen graph (link existence)
3. Apply a Contrastive Void Network (CVN) — trained on temporal ground truth — to rank absent edges by *significance*, not just likelihood
4. Validate: check which predicted voids were later confirmed by real-world data

**Results on open datasets:**

| Domain | Dataset | Ground Truth | P@100 |
|--------|---------|--------------|-------|
| Biomedical | Hetionet + STRING v12 | Protein interactions added post-cutoff | **0.94** |
| Threat Intelligence | MITRE ATT&CK Enterprise | ATT&CK edges added post-cutoff | **0.86** |

The temporal validation method — freeze, predict, wait, verify — is what separates significance from noise. Any system can score candidate edges; this one is calibrated against what *actually mattered later*.

**[→ void-graph on GitHub](https://github.com/CVSRohit/void-graph)** · Open source · Validated on real-world knowledge graphs

---

## AI Work

### Knowledge Graph Embeddings
Trained and evaluated KGE models (ComplEx, RotatE) for link prediction on biomedical and cybersecurity graphs. Extended standard KGE pipelines with contrastive significance heads and temporal holdout validation.

### Contrastive Learning for Absence
Developed the CVN (Contrastive Void Network) — an InfoNCE-trained head on frozen KGE embeddings that learns to distinguish structurally significant voids from random non-edges. Applied to Hetionet (47K nodes, 2.25M edges) and MITRE ATT&CK (1,757 nodes, 20K edges).

### Applied Domains
- **Biomedical**: Drug-target, gene-disease, compound-pathway void detection
- **Cybersecurity**: Threat actor → technique gap prediction; mitigation coverage analysis
- **[Open KG tooling](https://github.com/CVSRohit/open-knowledge-graphs)**: Knowledge graph construction and evaluation utilities

### Other AI Projects
- **[ai-data-analyst](https://github.com/CVSRohit/ai-data-analyst)** — Natural language interface for structured data analysis
- **[EvoPrompt](https://github.com/CVSRohit/EvoPrompt)** — Evolutionary prompt optimization
- **[FlyPyAgents](https://github.com/CVSRohit/FlyPyAgents)** — Lightweight Python agent framework
- **[PodcastGen](https://github.com/CVSRohit/PodcastGen)** — LLM-powered podcast generation pipeline

---

## Stack

![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=flat-square&logo=numpy&logoColor=white)
![HuggingFace](https://img.shields.io/badge/HuggingFace-FFD21E?style=flat-square&logo=huggingface&logoColor=black)
![OpenAI](https://img.shields.io/badge/OpenAI-412991?style=flat-square&logo=openai&logoColor=white)
![Google Cloud](https://img.shields.io/badge/Google_Cloud-4285F4?style=flat-square&logo=google-cloud&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-232F3E?style=flat-square&logo=amazon-aws&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![Next.js](https://img.shields.io/badge/Next.js-000000?style=flat-square&logo=next.js&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)

---

<div align="center">

**Interested in knowledge graphs, contrastive learning, or structured absence detection?**

[![Book a Call](https://img.shields.io/badge/📅_Schedule_a_Chat-3B82F6?style=for-the-badge)](https://calendly.com/cvsrohit/rohitchalla-com)
[![Portfolio](https://img.shields.io/badge/🌐_rohitchalla.com-1A1B27?style=for-the-badge)](https://rohitchalla.com)
[![LinkedIn](https://img.shields.io/badge/💼_LinkedIn-0077B5?style=for-the-badge)](https://linkedin.com/in/rohitchalla)

![Profile Views](https://komarev.com/ghpvc/?username=CVSRohit&color=10b981&style=flat-square)

</div>
