# Galaxy & Agentic Tools for Biological Data Analysis — Literature Scan

**Scan date:** 2026-09-20
**Prior scan:** `galaxy-agentic-tools-2026-06-28.md` (this scan is the delta since June, plus consolidated notes on peer-reviewed material that has appeared or been finalized in the meantime).
**Sources queried:** PubMed, Europe PMC, bioRxiv.
**Access caveat:** Direct API access to `eutils.ncbi.nlm.nih.gov`, `www.ebi.ac.uk/europepmc`, `api.biorxiv.org`, and `www.biorxiv.org`/`galaxyproject.org` HTML is denied by this environment's egress proxy (verified via `$HTTPS_PROXY/__agentproxy/status`: `connect_rejected` / 403 for all three hosts). All findings below therefore come from indexed web-search summaries that reference PubMed / PMC / Europe PMC / bioRxiv records; titles, DOIs, and PMIDs should be verified against the primary databases before formal citation.

---

## Executive summary — what changed since 2026-06-28

The Galaxy ∩ agentic-AI intersection went from "one flagship preprint" to a shipping product surface. Three developments dominate:

1. **Galaxy 26.1 (July 2026)** made agent operations a first-class feature: a built-in Model Context Protocol (MCP) server, context-aware in-UI agents, and a shared "Agent Operations" API layer for tools, histories, datasets, workflows, jobs, and IWC.
2. **Orbit** — Galaxy's own agentic harness, built on **Loom** — was benchmarked against eight frontier LLMs on a Candida auris RNA-seq reanalysis (six of eight reproduced the headline result), and its results were published on the Galaxy news channel.
3. The **NAR 2026 database issue** carries the Galaxy platform's 2026 update paper, which for the first time frames Galaxy as an AI-native platform.

Independently, "agentic bioinformatics" has crystallized as a named subfield: three separate 2026 Briefings in Bioinformatics reviews now use the term, several purpose-built benchmarks (FlowBench, BioAgent Bench, PromptBio-Bench) have landed, and the community has begun to publish on **agent-facing tool re-architecture** (Clair3-Connect, Coala, Bio-Babel) — an interface pattern that is directly relevant to how Galaxy tool wrappers could be exposed to agents.

---

## A. Directly Galaxy-related

### A.1 Peer-reviewed

| # | Title | Venue | Link |
|---|-------|-------|------|
| 1 | **Galaxy for accessible, reproducible, and collaborative data analyses: 2026 update** | Nucleic Acids Research 54(W1):W105–W116, June 2026 | [OUP](https://academic.oup.com/nar/article/54/W1/W105/8704296) · [PMC13355071](https://pmc.ncbi.nlm.nih.gov/articles/PMC13355071/) · [PubMed 42261686](https://pubmed.ncbi.nlm.nih.gov/42261686/) |
| 2 | **Coala: a standard-based framework for converting CWL-described command-line tools into agentic toolsets** | Bioinformatics 42(9):btag641, September 2026 | [OUP](https://academic.oup.com/bioinformatics/article/42/9/btag641/8771239) · [PubMed 42647176](https://pubmed.ncbi.nlm.nih.gov/42647176/) |
| 3 | **Evaluating open LLMs for agentic analysis orchestration in a typical biomedical lab** (previously the flagship bioRxiv item in §A.1 of the June scan) | Now indexed on PMC/PubMed | [PMC13228249](https://pmc.ncbi.nlm.nih.gov/articles/PMC13228249/) · [PubMed 42239169](https://pubmed.ncbi.nlm.nih.gov/42239169/) |

**Why they matter for Galaxy:** the NAR 2026 update paper is the canonical citation for anything mentioning Galaxy from now on. Coala is the closest peer-reviewed complement to the Galaxy-MCP effort — it takes the *other* community workflow standard (CWL) and lowers it into MCP tool schemas, and community CWL descriptors from Dockstore and bio-cwl-tools are cited as the source of leverage. It is the natural comparator for any "Galaxy tools as MCP" story.

### A.2 Preprints and community releases

- **"Towards LLM-Powered Task-Aware Retrieval of Scientific Workflows for Galaxy"** — arXiv 2511.01757. (The Google-Scholar hit noted as unverified in §A.2 of the June scan is now confirmed as this arXiv preprint.) https://arxiv.org/pdf/2511.01757
- **Galaxy Newsletter — July 2026 & September 2026** (Q2 and Q3 quarterly reports) — https://galaxyproject.org/news/2026-07-22-q2-newsletter/ ; https://galaxyproject.org/news/2026-09-08-q3-newsletter/
- **"Eight LLMs, one RNA-seq dataset: what we learned controlling Galaxy from Orbit"** — Galaxy Hub, 2026-06-09. Eight frontier LLMs drove Orbit sessions (Loom harness → Galaxy MCP server → usegalaxy.org, with reference data from BRC-analytics) against a *Candida auris* RNA-seq reanalysis; six reproduced the Scf1 headline result. Notably, a common Galaxy-side failure with optional workflow parameters was fixed in **Galaxy PR #22820** during the run window. https://galaxyproject.org/news/2026-06-09-llm-agents-reanalyze-rnaseq/
- **GCC2026 talk — "Building an AI-Native Galaxy: Agent Operations, Agent Framework, and MCP"** (Dannon Baker, John Chilton, Marius van den Beek) — describes the two-pillar architecture: (1) an **Agent Operations** layer built into Galaxy on top of `galaxy-mcp`, exposing tools/histories/datasets/workflows/jobs/IWC through a built-in MCP server; (2) an **Agent Framework** with a specialized-agent registry, intent-based routing, hand-offs, and multi-agent orchestration. https://galaxyproject.org/events/gcc2026/schedule/
- **GCC2026 Fishbowl — "AI, Galaxy, and Trustworthy Scientific Software"** — the community-facing counterpart to the trustworthy-agentic-AI thread in §D. https://galaxyproject.org/news/2026-07-09-gcc2026-fishbowl-summary/
- **Galaxy 26.1 release (July 2026)** — Galaxy Notebooks (browser-side JupyterLite with AI support, `usegalaxy.org` datasets/APIs), **context-aware GalaxyAI agents** (dockable assistant aware of the current tool form / job / history / notebook; specialized agents for error analysis, tool recommendations, GTN tutorials, and IWC workflows), and **first-class MCP server support**. https://docs.galaxyproject.org/en/release_26.1/releases/26.1_announce_user.html
- **`galaxy-mcp` v1.8.0** (PyPI, June 2026) — full BioBlend-backed Galaxy MCP server, community-maintained. https://pypi.org/project/galaxy-mcp/1.8.0/

---

## B. Agentic AI for biology — new / newly indexed since 2026-06-28

Ordered newest first. Everything below is a bioRxiv record (10.64898 DOIs), except where flagged otherwise.

| # | Title | Posted | Link |
|---|-------|--------|------|
| 1 | **Bio-Babel: autonomous cross-language reconstruction of agent-ready computational biology ecosystems** — rebuilds packages natively in the target language, each shipping an agent-readable usage contract; demonstrated on an R→Python single-cell stack. | 2026-08-30 | https://www.biorxiv.org/content/10.64898/2026.08.30.743167v1 |
| 2 | **EcoXAI: Autonomous Agentic Ecosystem for Explainable Artificial Intelligence and Biomedical Discovery** — modular, containerized multi-agent system with explicit knowledge-graph integration; targets clinical/translational users. | 2026-07-08 (v3/v4 updated Aug 2026) | https://www.biorxiv.org/content/10.64898/2026.07.08.737358v4 |
| 3 | **Autonomous computational prioritisation of colorectal cancer vulnerabilities via multi-scale AI swarms** | 2026-07-05 (v2) | https://www.biorxiv.org/content/10.64898/2026.07.05.736565v2 |
| 4 | **Client-server interfaces enable efficient agent-driven variant calling (Clair3-Connect)** — re-architects Clair3 into a client-server split: client keeps identifiable genomic data and exposes schema-defined agent-facing tools; server runs only NN inference. 60/60 correct on an APOE diplotyping task. | 2026-06-25 | https://www.biorxiv.org/content/10.64898/2026.06.25.734665v1 |
| 5 | **FlowBench + FlowAgent — separating planning, fault recovery and interpretation in agentic bioinformatics** — decomposes agent performance into planning (66 prompts), fault recovery (28-fault catalogue), and biological interpretation; scored across 23 models from Anthropic/OpenAI/Google. Reports that reasoning-tier models were often *least* reliable at recognising unrecoverable faults. | 2026-06-12 | https://www.biorxiv.org/content/10.64898/2026.06.12.731844v1 |
| 6 | **Trustworthy agentic genomics through versioned skill libraries** (Corpas et al.) | 2026-06-11 | https://www.biorxiv.org/content/10.64898/2026.06.11.731523v1 |
| 7 | **Evaluating agentic AI for biological discovery in autonomous and copilot settings (M3A framework)** — now indexed on PMC/PubMed. Was §B.1 in the June scan as a bioRxiv-only record. | Preprint 2026-06-04 · PMC/PubMed August 2026 | [bioRxiv](https://www.biorxiv.org/content/10.64898/2026.06.04.729919v1) · [PMC13278126](https://pmc.ncbi.nlm.nih.gov/articles/PMC13278126/) · [PubMed 42327254](https://pubmed.ncbi.nlm.nih.gov/42327254/) |
| 8 | **CGAgentX: Agentic AI Framework to Develop Transferable Coarse-Grained Models** — six specialized LLM agents (Mapping, Topology, Boundary, Hypothesis, Diagnostic, Optimization) orchestrated by a Master Agent; closed-loop CG parameter refinement with molecular-dynamics tool calls; hits <5% error on DMSO/DMA. | 2026-04-17 | https://www.biorxiv.org/content/10.64898/2026.04.17.719081v1 |
| 9 | **Pipette: Encoding scientific literature into an executable Skill Graph for multi-agent bioinformatics** — Skill Graph mined from ~20k PMC papers (78 skills, 483 directed edges); constrains agent workflows to biologically valid transitions. Demonstrated on ACMG/AMP variant classification with machine-readable provenance. | 2026-04-08 | https://www.biorxiv.org/content/10.64898/2026.04.08.717332v1 |
| 10 | **Benchmarking Agentic LLMs for Complex Protein-Set Functional Annotation** | 2026-04-18 | https://www.biorxiv.org/content/10.64898/2026.04.18.719404v1 |
| 11 | **PlotGDP: an AI Agent for Bioinformatics Plotting** — natural-language chart authoring across common bioinformatics plot types, packaged as a web server. | 2026-01-31 | https://www.biorxiv.org/content/10.64898/2026.01.31.702995v1 |

Additional named benchmarks / arXiv:
- **BioAgent Bench** — arXiv 2601.21800 (posted Jan 2026): 10 realistic end-to-end tasks (bulk & scRNA-seq, comparative genomics, variant calling, metagenomics, viral metagenomics, transcript quantification, experimental evolution); LLM-graded, includes stress tests. https://arxiv.org/pdf/2601.21800
- **PromptBio-Bench** (bioRxiv 2026.05.05.723092, v2 May 2026): 244 expert-curated tasks across bioinformatics/data science. Biomni ≈ ToolsGenie in aggregate; accuracy declines sharply with task difficulty. https://www.biorxiv.org/content/10.64898/2026.05.05.723092v2

---

## C. Model Context Protocol (MCP) for bioinformatics — now a named integration point for Galaxy

Since the June scan this cluster has become the fastest-moving one and is now the natural pipe between Galaxy's tool registry and any external agent.

- **Coala** (peer-reviewed, §A.1 above) — the CWL ↔ MCP bridge; treats tool definitions as *data*, executes in containerized environments through a generic MCP server. https://academic.oup.com/bioinformatics/article/42/9/btag641/8771239
- **Model Context Protocol: The unexpected catalyst of a bioinformatics interoperability revolution** — commentary, indexed on PMC. https://pmc.ncbi.nlm.nih.gov/articles/PMC13528949/
- **BioinfoMCP** — arXiv 2510.02139 (carried over from June scan; still active). https://arxiv.org/html/2510.02139v1
- **MCPmed** — PMC12927880 (carried over; still active). https://www.ncbi.nlm.nih.gov/pmc/articles/PMC12927880/
- **`galaxy-mcp`** — Python MCP server, PyPI v1.8.0 (June 2026). https://pypi.org/project/galaxy-mcp/1.8.0/

Note: MCP 2026 protocol revision makes the core stateless and moves capabilities into independently versioned extensions — worth tracking, since the Galaxy 26.1 built-in MCP server will need to track it.

---

## D. Peer-reviewed reviews & perspectives — 2026 harvest

The term "agentic bioinformatics" now recurs in Briefings in Bioinformatics with consistent framing. The reviews below are all now indexed on PubMed / PMC / OUP, i.e. citable in a formal manuscript.

- **When intelligence begins to act: a thoughtful appraisal of agentic AI in biomedicine** — *Briefings in Bioinformatics* 27(3), May 2026, bbag213. https://academic.oup.com/bib/article/27/3/bbag213/8670388
- **Large language model agents for biological intelligence across genomics, proteomics, spatial biology, and biomedicine** — *Briefings in Bioinformatics* 27(2), bbag110. https://academic.oup.com/bib/article/27/2/bbag110/8540361 · [PubMed 41883029](https://pubmed.ncbi.nlm.nih.gov/41883029/)
- **Next paradigm in bioinformatics: a review of multi-agent systems and foundational models for end-to-end scientific discovery** — *Briefings in Bioinformatics* 27(3), bbag245. https://academic.oup.com/bib/article/27/3/bbag245/8688274
- **Streamline automated biomedical discoveries with agentic bioinformatics** — *Briefings in Bioinformatics* 26(5), bbaf505 (late-2025, still the field-naming reference). https://academic.oup.com/bib/article/26/5/bbaf505/8266996
- **Artificial Intelligence agents for biological research: a survey** — *Briefings in Bioinformatics* 27(1), bbag075. Structured review of 115 studies (Jan 2023 – Sep 2025). https://academic.oup.com/bib/article/27/1/bbag075/8499367
- **Agentic genomics: From pipeline automation to autonomous validation** — PubMed 42480539 (August 2026). https://pubmed.ncbi.nlm.nih.gov/42480539/
- **Entering the agentic era of AI in drug discovery** — PubMed 42618630 (August 2026). https://pubmed.ncbi.nlm.nih.gov/42618630/
- **Closed-loop agentic AI in drug discovery** — PubMed 42582871. https://pubmed.ncbi.nlm.nih.gov/42582871/
- **AI agents in drug discovery: applications and case studies** — PubMed 41887499. https://pubmed.ncbi.nlm.nih.gov/41887499/
- **Artificial intelligence agents and agentic artificial intelligence applied to precision medicine** — PubMed 42617946 (August 2026). https://pubmed.ncbi.nlm.nih.gov/42617946/
- **Democratising real-world drug discovery through agentic AI** — PubMed 41548711. https://pubmed.ncbi.nlm.nih.gov/41548711/
- **Trustworthy Agentic AI in Bioinformatics: From Workflow Automation to Traceable and Validated Biological Inference** — PMC13565537 (proposes THREAD-Bio, a reporting framework for reconstructible, challengeable, human-accountable agent-assisted inference). https://pmc.ncbi.nlm.nih.gov/articles/PMC13565537
- **Agentic AI for trustworthy synthetic microbial genomics: a perspective on generation, validation, and governance** — *Frontiers in Bioinformatics* 2026 (PubMed 42656568). https://www.frontiersin.org/journals/bioinformatics/articles/10.3389/fbinf.2026.1903746/full

Still-relevant items carried over from the June scan (verified links):

- **BioAgents: Bridging the gap in bioinformatics analysis with multi-agent systems** — *Scientific Reports* (2025). https://www.nature.com/articles/s41598-025-25919-z
- **An agentic AI framework for ingestion and standardization of single-cell RNA-seq data analysis** — *npj Artificial Intelligence*. https://www.nature.com/articles/s44387-025-00064-0

---

## E. Named agents & systems — updated tracker

New entries flagged **NEW**; §E of the June scan remains valid for the rest.

| Agent / system | Focus | Notes |
|----------------|-------|-------|
| **Orbit** *(NEW-in-scan; Galaxy)* | Agentic harness over Loom, driving Galaxy via `galaxy-mcp` | Reference implementation for using arbitrary frontier LLMs against a Galaxy instance. https://galaxyproject.org/tools/orbit/ |
| **Galaxy Agent Operations** *(NEW-in-scan)* | Native Galaxy agent layer | Ships with Galaxy 26.1; the platform-side complement to Orbit. |
| **Clair3-Connect** *(NEW)* | Long-read variant calling, agent-facing | Client-server split, schema-typed agent tools. |
| **Coala** *(NEW)* | CWL → MCP bridge | Turns any CWL tool description into an MCP tool; container-executed. |
| **Bio-Babel** *(NEW)* | Cross-language rebuild + agent-callable contracts | Stanford; biobabel.stanford.edu. |
| **Pipette** *(NEW)* | Literature-derived Skill Graph for multi-agent workflows | 78-skill, 483-edge graph from ~20k PMC papers. |
| **CGAgentX** *(NEW)* | Coarse-grained MD parameter development | Six-agent hierarchy under a Master Agent. |
| **EcoXAI** *(NEW)* | Explainable biomedical discovery | Multi-agent, containerized, knowledge-graph-grounded. |
| **PlotGDP** *(NEW)* | Bioinformatics plotting | LLM-powered chart authoring. |
| **FlowAgent** *(NEW)* | Provider-agnostic bioinformatics agent harness | Shipped alongside FlowBench. |
| Biomni · BioMaster · CellAgent · BIA · CellAtria · CellVoyager / CellVerse / scAgent / Teddy · CRISPR-GPT · Paper2Agent · TusoAI · CellForge · HeurekaBench | (see June scan §E) | Still active; several are named baselines in FlowBench / BioAgent Bench / PromptBio-Bench. |

Community tracker: https://github.com/aristoteleo/awesome-bioagent-papers (still active).
Weekly digest style tracker (autonomous biology): https://github.com/HSZD-Team/Awesome-Autonomous-Biology (new since June).

---

## F. Implications / what to read first

1. **If the goal is Galaxy-relevant agentic tooling:** start with the Galaxy 26.1 release notes and the GCC2026 "AI-Native Galaxy" talk; then read the Orbit / eight-LLM RNA-seq write-up as the operational proof point. `galaxy-mcp` v1.8.0 is the code entry point.
2. **If the goal is a citable framing:** the NAR 2026 Galaxy update (§A.1 #1) plus one of the three 2026 BiB reviews (§D) gives a defensible pair for the introduction of a manuscript. Coala (§A.1 #2) is the sharpest peer-reviewed comparator for a "wrap our tools for agents" argument.
3. **If the goal is designing agent-facing tool interfaces for Galaxy tools:** read Clair3-Connect (§B #4) and Coala (§A.1 #2) together. Both show that redesigning the *tool boundary* (schema-defined, single-call, container-executed) — rather than the tool itself — is what makes agent runs efficient. This is the design lens Galaxy tool wrappers will need.
4. **If the goal is evaluating agents on bioinformatics work:** the current benchmark trio is **FlowBench** (planning / fault recovery / interpretation, provider-agnostic), **BioAgent Bench** (end-to-end pipelines with stress tests), and **PromptBio-Bench** (244 tasks, difficulty-stratified). Running Galaxy-driven agents against these would produce a directly citable position piece.
5. **If the goal is trustworthiness / provenance:** THREAD-Bio (§D) and the versioned-skill-library paper (§B #6) are the two frameworks to cite; both align with the GCC2026 Fishbowl framing and would compose naturally with Galaxy's existing history-and-invocation provenance model.

---

## G. Caveats

- **Verify against primaries.** The scan environment blocks direct API access to PubMed eutils, Europe PMC REST, the bioRxiv API, and HTML on `www.biorxiv.org` / `galaxyproject.org` (403 CONNECT). All records above come from web-search summaries citing PMC / PubMed / OUP / bioRxiv URLs; DOIs and PMIDs need one round of confirmation in the actual databases before formal citation.
- **bioRxiv DOIs.** All 2026 bioRxiv entries use the `10.64898/2026.*` prefix (the successor to `10.1101/*` that Cold Spring Harbor announced late 2025). This is expected, not an artifact.
- **Priority read for one-hour skim:** Coala (peer-reviewed) → Clair3-Connect (bioRxiv, tightest engineering) → Galaxy 26.1 release notes + Orbit write-up (product state of the art) → any one 2026 BiB review (framing).
