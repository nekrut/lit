# Galaxy & Agentic Tools for Biological Data Analysis — Literature Scan

**Scan date:** 2026-10-25
**Previous scan:** `galaxy-agentic-tools-2026-06-28.md` (≈4 months ago)
**Sources queried:** PubMed, Europe PMC, bioRxiv. Direct API access (eutils, EPMC REST, bioRxiv API) was again blocked by the sandbox network policy (HTTP 403 on CONNECT), so results come from web-search summaries over the three sources plus their accessible front-ends; titles / IDs / page numbers should be verified against the primary record before formal citation.
**Query intent:** What's new since late June 2026 at the Galaxy ∩ agentic-AI intersection, plus notable new agentic / LLM-agent systems for biological data analysis.

---

## Headline: Galaxy's agentic story has moved from third-party experiments into the platform itself.

The **Galaxy 2026 Nucleic Acids Research update** says the quiet part out loud, and **Galaxy 26.1** ships an in-platform MCP server. The 2025–mid-2026 pattern of bolting LLM agents onto Galaxy from the outside (via BioBlend wrappers, custom MCP shims, or tutorial-grounded RAG) is being replaced by a first-party interface: an MCP-compatible client can now search and run tools, inspect histories and datasets, invoke workflows, and monitor jobs against a Galaxy server, with no bespoke integration per agent. That is the single biggest change in this scan.

---

## A. Directly Galaxy-related — new since the June scan

1. **Galaxy for accessible, reproducible, and collaborative data analyses: 2026 update** — *Nucleic Acids Research* 54, W105–W116 (2026), Web Server issue; DOI 10.1093/nar/gkag469; advance access 9 June 2026. PMID 42261686.
   - Scale: >650,000 registered users; major public servers run ~2,000,000 analysis jobs/month from ~20,000 active monthly users.
   - UX: redesigned history interface, improved tool discovery, centralized dataset view, new visualization framework, workflow editor with search/undo-redo and invocation-graph views.
   - **Agentic hook:** explicitly flags deeper integration of the Galaxy-MCP project to let external AI clients interact with Galaxy programmatically. This is the paper to cite as the authoritative anchor on where Galaxy's LLM/agent strategy sits today.
   - URL: https://academic.oup.com/nar/article/54/W1/W105/8704296

2. **Galaxy 26.1 — built-in MCP support** (release in 2026, discussed at GCC2026, June 23–26 2026, Clermont-Ferrand).
   - When enabled by an admin, MCP-compatible clients can: search + run tools, inspect histories/datasets, invoke workflows, monitor jobs, and discover community workflows.
   - GCC2026 abstracts describe an in-platform agent framework with intent-based routing (e.g., routes to Galaxy Training Network recommendations). This is the operational realization of the plan sketched in the NAR 2026 paper.
   - Refs: Galaxy Q3 2026 newsletter (https://galaxyproject.org/news/2026-09-08-q3-newsletter/); GCC2026 abstract book (https://galaxy-community-conference.s3.us-east-1.amazonaws.com/GCC2026-abstract-book.pdf)

3. **Introducing GalaxyR: an easy-to-use R implementation of the Galaxy API** — *BMC Bioinformatics*, Aug 2026. PMID 42581344.
   - Opens programmatic Galaxy access beyond the Python/BioBlend ecosystem; demonstrated on drone-based laser-scanning data (tree-level segmentation) with workflow control in R.
   - URL: https://pubmed.ncbi.nlm.nih.gov/42581344/

4. **Community-curated Galaxy interfaces with the Galaxy Labs Engine** — *GigaScience*, 2026. PMID 41964931.
   - Framework behind labs.usegalaxy.org.au; multiple Labs already running for active user communities. Natural substrate for agent-targeted, scoped tool catalogs.
   - URL: https://pubmed.ncbi.nlm.nih.gov/41964931/

5. **GalaxyMemMD: an end-to-end Galaxy toolset for reproducible membrane embedding** — bioRxiv 10.64898/2026.09.28.755125 (Sept 2026).
   - Packages legacy comp-chem tooling into Galaxy workflows for membrane-protein MD setup.
   - URL: https://www.biorxiv.org/content/10.64898/2026.09.28.755125v1.full.pdf

6. **FAIRyMAGs — a series of FAIR Galaxy workflows for the generation of metagenome-assembled genomes** — bioRxiv 10.64898/2026.07.31.741430 (Jul 2026).
   - Six interconnected workflows from preprocessing through functional annotation; runs on public or private Galaxy instances; ships with tutorials and test data.
   - URL: https://www.biorxiv.org/content/10.64898/2026.07.31.741430v1

---

## B. The Galaxy ∩ MCP / agent intersection — the strategic axis to watch

| Project | What it is | Status | Note |
|---|---|---|---|
| **Galaxy 26.1 built-in MCP server** (galaxyproject) | First-party MCP interface shipped with Galaxy | In release; admin-opt-in | The one to prefer going forward — displaces the external shims |
| **galaxyproject/galaxy-mcp** (PyPI 1.8.0) | Python MCP server built on BioBlend; TypeScript workspace + Node MCP server also added | Active; experimental CodeMode | Three meta-tools: `search`, `get_schema`, `run_galaxy_tool` to keep agent context lean |
| **Rhea** (described in "Experiences with MCP Servers for Science and HPC", arXiv 2508.18489) | External MCP server exposing Galaxy Toolshed via a single `find_tools` call; RAG over tool + GTN tutorial text | Prior work (~2025) | Benchmark: Recall@k against 380 queries derived from GTN tutorials — a usable Galaxy-side evaluation harness |
| **BioinfoMCP Compiler** — "Beyond Prompt-Based Planning: MCP-Native Graph Planning-based Biomedical Agent System" (arXiv 2606.04494) | LLM-driven converter that builds MCP servers from CLI docs, Python/R packages, containerized workflows | Reports ecosystem of 910 MCP servers / 3,500 tools | The scale extension of the BioinfoMCP line from the June scan |
| **MCPmed** — *Briefings in Bioinformatics* 27(1), bbag076, now indexed as PMID 41729821 | Community proposal for MCP-enabled bio web services, with "breadcrumb" lightweight registration | Published in print 2026 | Promoted from preprint since the June scan |
| **MCP server for differential diagnosis using NCBI E-utilities** — medRxiv 10.64898/2026.08.18.26359085 | Human-in-the-loop LLM system that reads EMRs and queries PubMed/PMC via MCP | Preprint, Aug 2026 | Illustrates the PubMed-side of the MCP story |

Why this is the file to re-read first: everything in §C below either stacks on top of this layer or stays stuck in bespoke integration debt. Galaxy's 26.1 MCP server is the piece that lets any of the §C agents reach the Galaxy tool catalog without their authors shipping Galaxy-specific glue.

---

## C. New agentic systems and benchmarks (July–October 2026)

| # | Title | Venue / ID | What it adds |
|---|---|---|---|
| 1 | **BaseCamp — An Agentic AI Framework for Automating DNA Sequencing Data Pipelines** | arXiv 2609.28557 (Sept 2026) | Multi-institution team (ODU + FIU + Deloitte + NTU) proposing a pipeline-automation agent for DNA sequencing. Abstract/details require the arXiv page directly. |
| 2 | **Evaluating Autonomous LLM Agents Across Molecular Prediction and Optimization Benchmarks** | bioRxiv 10.64898/2026.10.01.755314 (Oct 2026) | TDC-leaderboard-style assessment of agent-developed models; Smbatyan, Ghukasyan, Petrosyan. |
| 3 | **A Conversational Multi-Agent AI System for Integrated Multi-Omics Analysis and Biomedical Discovery (LungChat)** | bioRxiv 10.64898/2026.08.08.743577 (Aug 2026) | Single-cell agent over 39 datasets / 2.8M cells with pre-computed DE statistics; multi-omics chat orchestration. |
| 4 | **EcoXAI** | bioRxiv (Jul 2026) | Knowledge-graph-grounded multi-agent framework for explainable AI in biomedical discovery. |
| 5 | **Evaluating Agentic Bioinformatics through Function, Evidence, and Validation** | arXiv 2607.27556 (Jul 2026) | Benchmark aimed at the three dimensions in its title; natural companion to BiomniBench. |
| 6 | **Bioinfoysis Technical Report** | arXiv 2609.03871 (Sept 2026) | Technical report on an agentic bioinformatics system (title suggests "bio + analysis"). |
| 7 | **BioVerge: A Comprehensive Benchmark and Study of Self-Evaluating Agents for Biomedical Hypothesis Generation** | arXiv 2511.08866 | Benchmark + study of self-evaluating hypothesis-generation agents. |
| 8 | **FrontierChallenge: Evaluating Scientific Workflow Completion** | arXiv 2608.24979 (Aug 2026) | End-to-end scientific-workflow completion benchmark. |
| 9 | **Process-Reward Tactic Evolution for Long-Horizon Bioinformatics Workflows** | arXiv 2606.20839 (Jun 2026) | Explicitly cites prior work on "LLM-powered task-aware retrieval of scientific workflows for Galaxy" — tracks a Galaxy-adjacent thread. |
| 10 | **GLOW: Graph-Language Co-Encoding for Agentic Workflow Performance Prediction** | arXiv 2512.15751 | Workflow performance prediction for agent systems (lead-forward dated; verify). |
| 11 | **LLM Agents for Interactive Workflow Provenance** | arXiv 2509.13978 | Reference architecture + evaluation methodology — workflow-provenance side of the agent stack. |

Already-tracked systems that gained ground since June:
- **CellAtria** (bioRxiv 2025.07.31.667880) — scRNA-seq ingestion/standardization now reads as the de-facto reference agent in this niche; multiple downstream citations.
- **OmniCellAgent** (bioRxiv 2025.07.31.667797, v3 Jun 2026) — AI scientist for omic-driven discovery.

---

## D. Peer-reviewed journal items worth noting

- **MCPmed** — *Briefings in Bioinformatics* 27(1), bbag076. PMID 41729821. (Promoted from PMC-only to indexed since the last scan.) https://academic.oup.com/bib/article/27/1/bbag076/8495038
- **Interacting with IoT Data Spaces Using LLMs and the Model Context Protocol** — PubMed 41755134. Non-bio, but it illustrates how MCP is being treated as the common integration bus across science domains. https://pubmed.ncbi.nlm.nih.gov/41755134/

(The two large reviews flagged in the June scan — *Briefings in Bioinformatics* "AI agents for biological research: a survey" and "Rise and potential opportunities of large language model agents in bioinformatics and biomedicine" — remain the best general entry points; nothing in this scan has displaced them.)

---

## E. What changed vs. the June 2026 scan

- **Galaxy owns the integration layer now.** Galaxy 26.1 ships MCP support in-platform; the NAR 2026 update formally commits to the Galaxy-MCP track. The MCP-wrapping-Galaxy effort has crossed from third-party curiosity (Rhea, galaxy-mcp pre-26.1) into vendor-blessed primary interface.
- **Agent benchmarking has gone from "name a system" to "measure the behavior."** EcoXAI, BiomniBench, BixBench-adjacent work, FrontierChallenge, "Evaluating Agentic Bioinformatics...", "Evaluating Autonomous LLM Agents Across Molecular Prediction and Optimization Benchmarks" — benchmarks now dominate the preprint volume. The June scan had maybe one or two; October has at least six.
- **BioinfoMCP Compiler (arXiv 2606.04494) is the Galaxy complement.** Where Galaxy exposes its own tool catalog via MCP, BioinfoMCP's Compiler bulk-converts arbitrary bioinformatics software to MCP: 910 servers / 3,500 tools reported. Together these two lines could reduce "wrap your tool for an agent" from a per-tool engineering task to a near-free one.
- **Pipeline-automation agents matured.** BaseCamp (sequencing pipelines), the May-2026 "open LLMs for agentic analysis orchestration" PMC-indexed paper (Galaxy-aware), and LungChat (multi-omics) are no longer isolated demos — they are starting to resemble product-shaped systems with explicit evaluation.
- **Still open:** a plainly-named, peer-reviewed demonstration that an off-the-shelf agent, pointed at Galaxy 26.1's MCP endpoint, outperforms the same agent on the previous bespoke-wrapper architecture. That is the natural next paper and it isn't out yet (or isn't in indexable form) as of this scan.

---

## F. Read-first list, in order

1. **NAR 2026 Galaxy update** — the authoritative anchor; everything else fits around it. https://academic.oup.com/nar/article/54/W1/W105/8704296
2. **GCC2026 abstract book** — details on the 26.1 MCP server and intent-routed agent framework. https://galaxy-community-conference.s3.us-east-1.amazonaws.com/GCC2026-abstract-book.pdf
3. **"Beyond Prompt-Based Planning: MCP-Native Graph Planning-based Biomedical Agent System"** — the Compiler counterpart on the agent side. https://arxiv.org/html/2606.04494
4. **MCPmed journal version** — community proposal, now indexed. https://academic.oup.com/bib/article/27/1/bbag076/8495038
5. **"Experiences with MCP Servers for Science and HPC"** (Rhea) — the earlier Galaxy-side MCP work that 26.1 effectively subsumes but whose GTN-based 380-query benchmark is still useful. https://arxiv.org/html/2508.18489v1

---

## Caveats

- Direct API access to PubMed eutils, Europe PMC REST, and bioRxiv API was again denied (HTTP 403 on CONNECT at the gateway) during this scan. Results above come from web-search summaries and accessible article pages.
- A few arXiv IDs in §C (particularly those with "26XX" month-prefixes beyond calendar-month) look forward-dated per arXiv's rolling scheme; verify the actual posting date before citing.
- Field-level details for BaseCamp (arXiv 2609.28557), GLOW (arXiv 2512.15751), and Bioinfoysis (arXiv 2609.03871) could not be read in full here — only title + author lists from search snippets. Open the arXiv pages before relying on specifics.
