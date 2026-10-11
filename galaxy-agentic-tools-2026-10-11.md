# Galaxy & Agentic Tools for Biological Data Analysis — Literature Scan

**Scan date:** 2026-10-11
**Previous scan:** 2026-06-28 (`galaxy-agentic-tools-2026-06-28.md`)
**Sources queried:** PubMed, Europe PMC, bioRxiv (via web search; direct eutils/REST APIs still unavailable in the sandbox)
**Query intent:** New / updated (2026-H2) papers on the Galaxy platform AND/OR agentic / LLM-agent tools for biological data analysis.

> This is an incremental update. Items present in the June 2026 scan are not repeated unless they have progressed (preprint → peer-reviewed, new version, concrete downstream result). Focus is July–October 2026.

---

## A. Directly Galaxy-related

### A1. Peer-reviewed / indexed since last scan

1. **Evaluating open LLMs for agentic analysis orchestration in a typical biomedical lab** — Nekrutenko (Penn State), **now PubMed-indexed as PMID 42239169** (May 2026 preprint referenced in June scan; the full text sits at PMC13228249).
   - URL: https://pubmed.ncbi.nlm.nih.gov/42239169/ · https://pmc.ncbi.nlm.nih.gov/articles/PMC13228249/
   - Status change: the only Galaxy-centric agentic-orchestration study has now been pulled into the biomedical literature index, so it is citable from PubMed as well as from bioRxiv.

### A2. New Galaxy-centric work (June → October 2026)

2. **FlowBench — separating planning, fault recovery and interpretation in agentic bioinformatics** — bioRxiv 2026.06.12.731844 (posted mid-June, just after the last scan).
   - URL: https://www.biorxiv.org/content/10.64898/2026.06.12.731844v1.full
   - Three tiers scored independently (plan / recover / interpret) across 23 Anthropic/OpenAI/Google models, in triplicate. Positions Galaxy as the canonical "programming-expertise" baseline motivating the NL-driven agent interface. Secondary reporting (ampcome.com) notes that most failures were planning errors, not execution faults, and that a general-purpose coding agent (Claude Code) matched or beat dedicated bio-agents (BioMaster, AutoBA, Biomni) on both planning and execution — **worth verifying against the preprint directly** before citing.

3. **Process-Reward Tactic Evolution for Long-Horizon Bioinformatics Workflows** — arXiv 2606.20839 (June 2026).
   - URL: https://arxiv.org/html/2606.20839v1 · https://arxiv.org/pdf/2606.20839
   - Frames **Galaxy workflow construction** as a long-horizon agent-training problem. Benchmark: 26 training tasks + 35 held-out test tasks spanning DAG construction, input binding, dataset-collection handling, execution monitoring, debugging, and biological-output validation. This is the first paper we have seen that uses Galaxy workflows themselves as a training/eval corpus for agent process-reward models.

4. **A Conversational Multi-Agent AI System for Integrated (bioinformatics analysis)** — bioRxiv, posted 2026-08-14.
   - URL: https://www.biorxiv.org/content/biorxiv/early/2026/08/14/2026.08.08.743577.full.pdf
   - Full title truncated in listings; needs direct fetch for abstract. Appeared in the Galaxy-adjacent cluster of results, so flagged for follow-up.

### A3. Community / infrastructure signal

5. **Galaxy blog, 2026-06-09 — "Eight LLMs, one RNA-seq dataset: what we learned controlling Galaxy from Orbit."**
   - URL: https://galaxyproject.org/news/2026-06-09-llm-agents-reanalyze-rnaseq/ · mirror https://artifact.galaxyproject.org/news/2026-06-09-llm-agents-reanalyze-rnaseq/
   - Eight frontier LLMs (Claude Opus/Sonnet/Haiku, GPT-5.5 ×2, Gemini 2.5 Pro, Gemini 3.5 Flash, DeepSeek) drove Orbit sessions against usegalaxy.org through the Galaxy MCP server with BRC-analytics reference data. Target: Santana et al. 2023 *Science* (Scf1 / C. auris adhesin). **6 of 8 runs completed and all 6 independently reproduced the paper's central Scf1 down-regulation finding.** Opus mildly attenuated the fold-change (reported raw, unshrunken DESeq2). Headline failure modes called out: agents stalling on polling loops. This is the most concrete published demonstration of agent-driven Galaxy use to date and is the operational counterpart to §A1.

6. **GCC2026 CollaborationFest outcomes (news post, 2026-07-20).**
   - URL: https://galaxyproject.org/news/2026-07-20-gcc2026-cofest-outcomes/
   - CoFest project (Enis Afgan et al.) proposed a persistent agent to **auto-wrap new tools from Bioconda and Bioconductor** into Galaxy tool wrappers. Companion resources: a Python command-line wrapper generator and **R2G2** for R / Bioconductor. State: project / prototype — no production-ready auto-wrapper agent yet.

7. **GCC2026 schedule — AI-agent evaluation framework for Galaxy** — https://galaxyproject.org/events/gcc2026/schedule/
   - Describes a framework for testing whether AI agents can carry out end-to-end computational biology analyses inside Galaxy (interpreting task specs, selecting Galaxy tools, consuming Galaxy datasets). The second described framework is explicitly "capacity of AI agents to conduct end-to-end computational biology analyses within the Galaxy platform."

8. **`galaxy-mcp` MCP server for Galaxy** — https://github.com/galaxyproject/galaxy-mcp (not re-verified this scan; third-party indexers show PyPI versions in the 1.3.0 → 1.9.0 range).
   - Python + FastMCP 2.3+ server wrapping Galaxy's BioBlend-level API: connect to any Galaxy instance, search/run tools, manage workflows, upload files, import IWC workflows, optional browser-based OAuth. This is the actual tool the Galaxy–Orbit blog post (§A3.5) relies on; version pace suggests active development.

---

## B. Agentic AI for biology — new 2026-H2 preprints

| # | Title | Venue / Date | Link |
|---|-------|--------------|------|
| 1 | **Trustworthy Agentic AI in Bioinformatics: From Workflow Automation to Traceable and Validated Biological Inference** | PMC13565537 (indexed Jul–Sep 2026) | https://pmc.ncbi.nlm.nih.gov/articles/PMC13565537 |
| 2 | **BiomniBench — Process-level Evaluation of LLM Agents for Biomedical Research** | bioRxiv 2026.05.12.724604 | https://www.biorxiv.org/content/10.64898/2026.05.12.724604v1.full.pdf |
| 3 | **BaseCamp — An Agentic AI Framework for Automating DNA Sequencing Data Pipelines** | arXiv 2609.28557 | https://arxiv.org/pdf/2609.28557 |
| 4 | **Agentic systems are adept at solving well-scoped, verifiable problems in computational biology** | bioRxiv 2026.04.06.716850 | https://www.biorxiv.org/content/10.64898/2026.04.06.716850v1.full |
| 5 | **PlotGDP — an AI Agent for Bioinformatics Plotting** | bioRxiv 2026.01.31.702995 | https://www.biorxiv.org/content/10.64898/2026.01.31.702995v1.full |
| 6 | **Agentic AI for Structural Elucidation and Discovery of Drug Metabolites from Mass Spectrometry Data** (GNPS2-based) | PMC13320852 | https://pmc.ncbi.nlm.nih.gov/articles/PMC13320852 |
| 7 | **EcoXAI — Autonomous Agentic Ecosystem for Explainable AI and Biomedical Discovery** (KG-grounded; v4 Aug 2026; Alzheimer's drug-repurposing demo) | PMC13405269 | https://pmc.ncbi.nlm.nih.gov/articles/PMC13405269 |
| 8 | **Evaluating Agentic Bioinformatics through Function, Evidence, and Validation** | arXiv 2607.27556 | https://arxiv.org/pdf/2607.27556 |
| 9 | **BioAgent Bench — An AI Agent Evaluation Suite for Bioinformatics** (ICML 2026 paper; v2 updated Mar 2026) | arXiv 2601.21800 · ICML 2026 | https://arxiv.org/pdf/2601.21800 · https://proceedings.mlr.press/v306/fa26a.html · https://icml.cc/virtual/2026/67848 |
| 10 | **Agentic AI for Bioinformatics Workflows** (BeeAI + RAG for omics planning) | IBM Research publication | https://research.ibm.com/publications/agentic-ai-for-bioinformatics-workflows |
| 11 | **Multi-agentic system for primer design in qPCR and LAMP diagnostics tests** | bioRxiv 2026.09.15.751771 (posted 2026-09-16) | https://www.biorxiv.org/content/10.64898/2026.09.15.751771v1 |
| 12 | **PaleoRigor — bounded research agent for paleomicrobiome data processing with reproducible evidence trail** | bioRxiv 2026.09.30.755805 (posted 2026-10-08) | https://doi.org/10.64898/2026.09.30.755805 |
| 13 | **ddkg.skill — agent skill translating biomedical/bioinformatics questions into Cypher queries over a knowledge graph** | bioRxiv 2026.09.21.753102 (posted 2026-10-07) | https://doi.org/10.64898/2026.09.21.753102 |
| 14 | **FrontierChallenge — Evaluating Scientific Workflow Completion** | arXiv 2608.24979 | https://arxiv.org/pdf/2608.24979 |
| 15 | **Bioinfoysis Technical Report** | arXiv 2609.03871 | https://arxiv.org/pdf/2609.03871 |

---

## C. MCP for bioinformatics — now a published thread

Momentum is now visible in peer-reviewed venues, not just preprints.

- **Sheffield — "Model Context Protocol: The unexpected catalyst of a bioinformatics interoperability revolution"** — *PLOS Computational Biology*, 2026 (PMC13528949). https://journals.plos.org/ploscompbiol/article?id=10.1371%2Fjournal.pcbi.1014543 · https://pmc.ncbi.nlm.nih.gov/articles/PMC13528949/
  - Positions MCP as the standardization layer for biological-data access. Notes that a major 2026 protocol revision made MCP core stateless and deprecated "sampling". Enumerates the active bio-MCP server ecosystem: **BioMCP, BioContextAI, MCPmed, galaxy-mcp, Holy Bio MCP Framework** — connecting PubMed, UniProt, ClinicalTrials.gov, and more.
- **MCPmed — now peer-reviewed in *Briefings in Bioinformatics* 27(1), bbag076 (January 2026)** — https://academic.oup.com/bib/article/27/1/bbag076/8495038 · PMID 41729821. The PMC12927880 record cited in the June scan was the pre-copyedit version. Implementations across GEO, STRING, UCSC Cell Browser.

**Implication for Galaxy:** the MCP ecosystem now has (a) a dedicated Galaxy server (`galaxy-mcp`, §A3.8), (b) a peer-reviewed call-to-action (MCPmed), (c) a *PLOS Comp Bio* perspective naming Galaxy's MCP server in the canonical list, and (d) a working end-to-end demonstration (Orbit × Galaxy × 8 LLMs). The June scan's bet that MCP would be the Galaxy ↔ agent integration layer looks correct.

---

## D. Reviews / surveys indexed in H2 2026

Peer-reviewed syntheses are now plentiful; four of these did not exist in indexed form in June.

- **Dip et al. — "Large language model agents for biological intelligence across genomics, proteomics, spatial biology, and biomedicine"** — *Briefings in Bioinformatics*, March 2026. PMID 41883029 · PMC13017847. First systematic synthesis across those domains; analyzes 60+ systems; flags unstable reasoning, weak biological grounding, reproducibility and biosafety.
- **Qi et al. — "Artificial Intelligence agents for biological research: a survey"** — *Briefings in Bioinformatics*, Jan 2026. PMID 41744224. 100+ studies; five-dimension taxonomy; open problems = reliability, privacy, scalability, standardized evaluation. (This was the PMC-only entry in the June scan; now PubMed-indexed with the Qi lead name.)
- **Branda et al. — "The next paradigm in bioinformatics: a review of multi-agent systems and foundational models for end-to-end scientific discovery"** — *Briefings in Bioinformatics*, May 2026. PMID 42160738.
- **Spieser et al. — "A Review of Multi-Agent AI Systems for Biological and Clinical Data Analysis"** — *Methods Protoc.*, Feb 2026. PMID 41874150.
- **"Advancing bioinformatics with language models: components, applications, and perspectives"** — PubMed, 2026. PMID 42430786.
- **"The rise and potential opportunities of large language model agents in bioinformatics and biomedicine"** — PubMed 41214870 (same bbaf601 cited last scan; now the PubMed stub is live).

---

## E. New named agents / systems observed this scan

Supplements the June table. Many of these appear only in benchmarks or secondary summaries — primary sources should be read before citing.

| Agent / system | Focus | First seen |
|---|---|---|
| **BaseCamp** | DNA-sequencing-pipeline automation (end-to-end) | arXiv 2609.28557 |
| **PlotGDP** | Bioinformatics plotting agent | bioRxiv Jan 2026 |
| **EcoXAI** | Multi-agent XAI + knowledge graphs; drug-repurposing use case | PMC13405269 |
| **PaleoRigor** | Paleomicrobiome processing with bounded, auditable evidence trail | bioRxiv Oct 2026 |
| **ddkg.skill** | NL → Cypher for biomed knowledge graphs | bioRxiv Oct 2026 |
| **BioMCP / BioContextAI / Holy Bio MCP Framework** | MCP servers over biological DBs | PLOS Comp Bio 2026 |
| **BioChatter** | Transparent, auditable workflows; "generic LLM agents lack reliability/reproducibility" positioning | SciLifeLab Feb 2026 |
| **Multi-agentic qPCR/LAMP primer designer** | Diagnostics primer design | bioRxiv Sep 2026 |
| **BeeAI omics agent** (IBM) | RAG-grounded 'omics workflow planning | IBM Research |

Community tracker still useful: https://github.com/aristoteleo/awesome-bioagent-papers

---

## F. What to read first (recommendations for the next sitting)

1. **Galaxy blog post + its reproduction run** (§A3.5) — most concrete demonstration that Galaxy MCP + Orbit + 2026-era frontier models can actually recapitulate a published RNA-seq finding, and the clearest list of failure modes to design against.
2. **FlowBench preprint** (§A2.2) — if the secondary reporting is right that Claude Code beats dedicated bio-agents on planning + execution, that reshapes the "should Galaxy build a bespoke agent?" question.
3. **Sheffield PLOS Comp Bio perspective + MCPmed** (§C) — the strategic layer. MCP is now the standardized way to expose Galaxy tools to any agent, with peer-reviewed buy-in.
4. **Process-Reward paper (arXiv 2606.20839)** (§A2.3) — if we care about training agents specifically on Galaxy workflows, this gives us a benchmark design to argue with or extend.
5. **Trustworthy Agentic AI in Bioinformatics** (§B.1) — probably the cleanest framing of what has to be true before any of this reaches a wet-lab-adjacent production setting.

---

## G. Delta vs. the June 2026 scan — at a glance

- **Galaxy ∩ agentic:** went from 1 solid paper (Nekrutenko) + 1 unverified rumor to **Nekrutenko (now PubMed-indexed) + FlowBench + Process-Reward Galaxy-workflow benchmark + Galaxy-blog demo of 8 LLMs reproducing a published result + CoFest auto-wrapper agent + `galaxy-mcp` active development + GCC2026 agent-eval framework**. The intersection is no longer thin.
- **MCP for bioinformatics:** went from "emerging theme" to a *PLOS Comp Bio* perspective + a peer-reviewed MCPmed in *BIB* + an explicit, named list of bio-MCP servers (galaxy-mcp among them).
- **Agentic-AI reviews:** at least four peer-reviewed syntheses added since June (Dip et al., Branda et al., Spieser et al., Advancing-bioinformatics-with-LLMs).
- **New agents added:** BaseCamp, PlotGDP, EcoXAI, PaleoRigor, ddkg.skill, BioChatter, BeeAI omics agent, multi-agentic qPCR/LAMP primer designer, FrontierChallenge/BioAgent Bench/BiomniBench on the evaluation side.

---

*Caveats:* Same as last scan — direct eutils / Europe PMC REST / bioRxiv API access was not available; everything above is reconstructed from web-search summaries and accessible HTML pages. Titles, DOIs, and PMIDs should be verified in the primary database before formal citation. In particular, items marked "secondary reporting" or "truncated title" need a direct fetch to confirm abstract contents.
