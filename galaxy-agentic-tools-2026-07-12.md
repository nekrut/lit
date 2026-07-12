# Galaxy & Agentic Tools for Biological Data Analysis — Literature Scan

**Scan date:** 2026-07-12
**Previous scan:** [galaxy-agentic-tools-2026-06-28.md](./galaxy-agentic-tools-2026-06-28.md) (2 weeks prior)
**Sources queried:** PubMed, Europe PMC, bioRxiv. Direct API endpoints (NCBI eutils, EPMC REST, bioRxiv) and several journal HTML pages returned 403 from the sandbox proxy — findings below come from web-search summaries and accessible front-ends; verify DOIs before formal citation.
**Query intent:** New items since 2026-06-28 at the Galaxy ∩ agentic-AI intersection.

---

## Headline items (new since last scan)

### 1. Galaxy 2026 update paper — *Nucleic Acids Research*
- **Title:** Galaxy for accessible, reproducible, and collaborative data analyses: 2026 update
- **Venue:** *Nucleic Acids Research*, advance article (2026)
- **URL / DOI:** https://academic.oup.com/nar/advance-article/doi/10.1093/nar/gkag469/8704296 (DOI 10.1093/nar/gkag469 — verify)
- **Why it matters:** This is the flagship Galaxy update paper for the year, and — crucially for this tracker — it explicitly frames Galaxy's AI/agentic direction. From search-result excerpts: *"AI-specific integration hooks and deeper integration of the Galaxy-MCP project will enable external AI clients to interact with Galaxy programmatically, while internal conversational agents will support job error interpretation, tool recommendation, and analysis guidance … with an emphasis on transparency, user control, and clear separation between automated assistance and reproducible computational steps."*
- **Status:** Highest-priority read this cycle. Retrieve full text through an authenticated channel — the OUP page was 403 from this sandbox.

### 2. Orbit / Galaxy-MCP: eight-LLM RNA-seq bake-off
- **Post:** *Eight LLMs, one RNA-seq dataset: what we learned controlling Galaxy from Orbit* — Galaxy Hub, 2026-06-09.
  - https://galaxyproject.org/news/2026-06-09-llm-agents-reanalyze-rnaseq/
- **Companion tool page:** *Orbit — AI Research Harness for Galaxy* — https://galaxyproject.org/tools/orbit/
- **Package:** `galaxy-mcp` **v1.8.0** released 2026-06-12 — https://pypi.org/project/galaxy-mcp/1.8.0/ ; repo https://github.com/galaxyproject/galaxy-mcp
- **Summary:** Eight frontier LLMs were asked to re-analyze the same *Candida auris* RNA-seq study on Galaxy via Orbit (the agentic interface built on the [Loom](https://github.com/galaxyproject/loom) harness), routed through usegalaxy.org via the Galaxy MCP server, with reference data from BRC-analytics. Six of the eight reproduced the headline result. Providers covered: Anthropic, OpenAI, Google, Mistral, Groq, xAI/Grok, and local Ollama (Qwen3).
- **Why it matters:** Not a peer-reviewed paper, but this is the first public, apples-to-apples LLM eval on the actual Galaxy stack. It also confirms the technical stack the NAR paper describes is shipping (Orbit + Loom + galaxy-mcp), not aspirational.

### 3. Streamline automated biomedical discoveries with agentic bioinformatics
- **Venue:** *Briefings in Bioinformatics* 26(5), bbaf505 (2026)
- **URL:** https://academic.oup.com/bib/article/26/5/bbaf505/8266996
- **PubMed:** https://pubmed.ncbi.nlm.nih.gov/41016012/
- **Why it matters:** Peer-reviewed opinion/position piece that names *"agentic bioinformatics"* as a distinct research field — a system-level rethink of "agents as tools" → "agents as autonomous collaborators" for hypothesis generation, experimental design, and iterative refinement. Not in the June 28 scan.

---

## New agentic-AI-for-biology papers (peer-reviewed)

| # | Title | Venue / Date | Link |
|---|-------|--------------|------|
| 1 | Empowering AI data scientists using a multi-agent LLM framework with self-evolving capabilities for autonomous, tool-aware biomedical data analyses | *Nature Biomedical Engineering* (2026) | https://www.nature.com/articles/s41551-026-01634-6 |
| 2 | The next paradigm in bioinformatics: a review of multi-agent systems and foundational models for end-to-end scientific discovery | *Briefings in Bioinformatics* 27(3), bbag245 | https://academic.oup.com/bib/article/27/3/bbag245/8688274 |
| 3 | Large language model agents for biological intelligence across genomics, proteomics, spatial biology, and biomedicine | *Briefings in Bioinformatics* 27(2), bbag110 | https://academic.oup.com/bib/article/27/2/bbag110/8540361 |

---

## New bioRxiv preprints (since last scan)

| # | Title | Date | Link |
|---|-------|------|------|
| 1 | biomeStat: Using Agentic AI for Scalable Genomic Epidemiology Demonstrated Through End-to-End Analysis of 1,000 Asian Dengue Virus Genomes | 2026-06-10 | https://www.biorxiv.org/content/10.64898/2026.06.10.731380v1 |
| 2 | Agentic systems are adept at solving well-scoped, verifiable problems in computational biology (benchmark spans genomics, transcriptomics, epigenomics, single-cell, human genetics, ML workflows; Codex CLI ≈ 83 %, Claude Code ≈ 81 %) | 2026-04-06 | https://www.biorxiv.org/content/10.64898/2026.04.06.716850v1 |
| 3 | Pipette: Encoding scientific literature into an executable Skill Graph for multi-agent bioinformatics (knowledge graph from ~20 000 papers, tested on scRNA-seq PBMC + human pancreas atlas) | 2026-04-08 | https://www.biorxiv.org/content/10.64898/2026.04.08.717332v1 |
| 4 | R2G2: A Python-R Framework for Seamless Integration of R/Bioconductor Tools into Galaxy (Galaxy-relevant; not agentic per se but relevant to the MCP-exposure thread) | 2025-12-22 | https://www.biorxiv.org/content/10.64898/2025.12.22.695980 |

---

## New arXiv preprints

- **Process-Reward Tactic Evolution for Long-Horizon Bioinformatics Workflows** — arXiv 2606.20839. https://arxiv.org/pdf/2606.20839
- **From Research Question to Scientific Workflow: Leveraging Agentic AI for Science Automation** — arXiv 2604.21910. https://arxiv.org/pdf/2604.21910

---

## Related but out of scope (noted for tracking)

- **2026 Galaxy Community Conference (GCC2026)** program — https://galaxyproject.org/events/gcc2026/schedule/ — worth watching for talks on the AI/Orbit track.
- **Article Galaxy MCP** (Research Solutions, 2026-04-07) — a *different* "Galaxy" product; MCP server for scientific-literature retrieval, no relation to the Galaxy Project. Filed here so it isn't rediscovered every scan.

---

## What to read first

1. **Galaxy 2026 NAR update** (Headline #1) — the canonical statement of where the Galaxy Project is placing its bet on agentic AI, and the single most important read of the cycle.
2. **Orbit RNA-seq bake-off blog + galaxy-mcp v1.8.0** (Headline #2) — the shipping reality behind the NAR paper's roadmap.
3. **Briefings in Bioinformatics — "Streamline automated biomedical discoveries with agentic bioinformatics"** (Headline #3) — sets the field-level framing and vocabulary; useful before reading the flood of preprints.

The Model Context Protocol / bioinformatics thread flagged in the 2026-06-28 scan continues to consolidate — Galaxy is now clearly aligning with it via `galaxy-mcp`, which retroactively strengthens the "MCP is the integration point" hypothesis from the last scan.

---

*Caveat:* Same as previous scan — direct API access to NCBI eutils, Europe PMC REST, and bioRxiv API was denied by the sandbox network policy; several journal HTML pages (OUP NAR, OUP BIB, galaxyproject.org) also returned 403 to the sandbox proxy. Titles and DOIs above come from web-search summaries and should be verified against the original databases before formal citation.
