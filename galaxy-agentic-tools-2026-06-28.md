# Galaxy & Agentic Tools for Biological Data Analysis — Literature Scan

**Scan date:** 2026-06-28
**Sources queried:** PubMed, Europe PMC, bioRxiv (PubMed/EPMC direct APIs were blocked by the sandbox network policy; results below come from web search and accessible front-ends.)
**Query intent:** Recent (2025–2026) papers on the Galaxy platform AND/OR new agentic / LLM-agent tools for biological data analysis.

---

## A. Directly Galaxy-related

1. **Evaluating open LLMs for agentic analysis orchestration in a typical biomedical lab** — bioRxiv, May 2026.
   - DOI: 10.64898/2026.05.13.724985
   - URL: https://www.biorxiv.org/content/10.64898/2026.05.13.724985v1.full
   - Highlights: Claude Opus 4.7 authors the analysis plan; six 2026-release open-weight models execute on a desktop GPU; strongest implementer cross-platform validated. Explicitly involves the **Galaxy Project Intergalactic Utilities Commission (IUC)** and community-curated **Galaxy tool wrappers**. Most directly Galaxy-relevant paper in this scan.

2. **"LLM-powered task-aware retrieval of scientific workflows for Galaxy"** — surfaced as a related result; verify via Google Scholar / direct title search before citing.

---

## B. Agentic AI for biology — high-signal recent preprints (2026)

| # | Title | Venue / Date | Link |
|---|-------|--------------|------|
| 1 | Evaluating agentic AI for biological discovery in autonomous and copilot settings (M3A framework, multi-omic single-cell across 11 cancer types) | bioRxiv, Jun 2026 | https://www.biorxiv.org/content/10.64898/2026.06.04.729919v1.full |
| 2 | Agentomics: An Agentic System that Autonomously Develops Novel SOTA Solutions for Biomedical ML Tasks | bioRxiv, Jan 2026 | https://www.biorxiv.org/content/10.64898/2026.01.27.702049v1 |
| 3 | BioTrouble: A Multi-Agent Workflow for Troubleshooting | bioRxiv, early 2026 | https://www.biorxiv.org/content/biorxiv/early/2026/01/02/2025.12.30.697016.full.pdf |
| 4 | Benchmarking and behavioral characterization of LLM agents for protein design | bioRxiv, May 2026 | https://www.biorxiv.org/content/10.64898/2026.05.06.723381v1.full.pdf |
| 5 | Benchmarking LLM-based Bioinformatics Agents for End-to-End Tasks | bioRxiv, May 2026 | https://www.biorxiv.org/content/10.64898/2026.05.05.723092v1.full-text |
| 6 | Large Language Model Agent Enables Autonomous ML Model Building for Biomedicine | bioRxiv, Apr 2026 | https://www.biorxiv.org/content/10.64898/2026.04.20.719735v1.full |
| 7 | ToolsGenie 2.0: A Scalable and Extensible Multi-Agent System | bioRxiv, Jan 2026 | https://www.biorxiv.org/content/10.64898/2026.01.06.697527v1.full.pdf |
| 8 | Development of an Agentic AI Model for NGS Downstream Analysis (researchers with limited bio background) | arXiv 2512.09964 | https://arxiv.org/pdf/2512.09964 |

---

## C. Model Context Protocol (MCP) for bioinformatics — emerging theme

- **BioinfoMCP: A Unified Platform Enabling MCP Interfaces in Agentic Bioinformatics** — arXiv 2510.02139 (built on FastMCP 2.0). https://arxiv.org/html/2510.02139v1
- **MCPmed: a call for Model Context Protocol-enabled bioinformatics web services for LLM-driven discovery** — PMC12927880. Community proposal with lightweight "breadcrumbs" for services not yet fully MCP-enabled; implementations across GEO, STRING, UCSC Cell Browser. https://www.ncbi.nlm.nih.gov/pmc/articles/PMC12927880/
- **Mozi: Governed Autonomy for Drug Discovery LLM Agents** — arXiv 2603.03655 (early 2026). https://arxiv.org/pdf/2603.03655

This is a natural integration point for Galaxy tool wrappers — worth tracking closely.

---

## D. Peer-reviewed journal articles (PubMed / PMC indexed)

- **Artificial Intelligence agents for biological research: a survey** — *Briefings in Bioinformatics* 27(1), Jan 2026. Structured review of 115 studies from Jan 2023 – Sep 2025 (arXiv, PubMed, bioRxiv, Google Scholar). https://academic.oup.com/bib/article/27/1/bbag075/8499367
- **Rise and potential opportunities of large language model agents in bioinformatics and biomedicine** — *Briefings in Bioinformatics* 26(6), bbaf601. https://academic.oup.com/bib/article/26/6/bbaf601/8320153
- **BioAgents: Bridging the gap in bioinformatics analysis with multi-agent systems** — *Scientific Reports* (2025). https://www.nature.com/articles/s41598-025-25919-z
- **An agentic AI framework for ingestion and standardization of single-cell RNA-seq data analysis** — *npj Artificial Intelligence*. https://www.nature.com/articles/s44387-025-00064-0
- **From foundation models to autonomous agents in biology** — Max Press review. https://www.maxapress.com/article/id/69c6349ffa6c58267402f879
- **LLM4Cell: A Survey of Large Language and Agentic Models for Single-Cell Biology** — arXiv 2510.07793. https://arxiv.org/pdf/2510.07793

---

## E. Named agents/systems frequently cited

| Agent | Focus | Notes |
|-------|-------|-------|
| **Biomni** (Stanford, May 2025) | General-purpose biomedical agent | Biomni-E1: 105 packages, 59 DBs, 150 tools; Biomni-A1 navigator |
| **BioMaster** (Jan 2025) | Automated RNA-seq workflows | Multi-agent, end-to-end |
| **CellAgent** | Single-cell RNA-seq | NL-based, multi-agent |
| **BIA (BioInformatics Agent)** | scRNA-seq, workflow generation | Chat-based, static + dynamic workflow adaptation |
| **CellAtria** | scRNA-seq | Document-to-analysis chatbot |
| **CellVoyager / CellVerse / scAgent / Teddy** | Single-cell | Domain encoders + LLM controllers |
| **CRISPR-GPT** | CRISPR design | |
| **Paper2Agent** | Turn research papers into interactive AI agents | arXiv 2509.06917 |
| **TusoAI** | Agentic optimization for scientific methods | arXiv 2509.23986 |
| **CellForge** | Agentic virtual-cell model design | arXiv 2508.02276 |
| **HeurekaBench** | Benchmarking AI co-scientists | arXiv 2601.01678 |

A community-maintained tracker exists: https://github.com/aristoteleo/awesome-bioagent-papers

---

## F. Implications / what to read first

If the goal is "what's new at the Galaxy ∩ agentic-AI intersection," the **single highest-priority read** is the May 2026 bioRxiv paper in §A.1 — it is the only piece in this scan that operationalizes agentic orchestration against the actual Galaxy tool catalogue.

After that, the MCP cluster (§C) is the strategically important thread: it points at how Galaxy-managed tools could be exposed as first-class citizens to any LLM agent without bespoke per-agent integration work.

---

*Caveat:* Direct API access to PubMed eutils, Europe PMC REST, and bioRxiv API was denied by the sandbox network policy during this scan. Findings above come from web-search summaries and accessible HTML pages; titles/DOIs should be verified against the original databases before formal citation.
