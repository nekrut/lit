# Galaxy & Agentic Tools for Biological Data Analysis — Literature Scan

**Scan date:** 2026-11-08
**Sources queried:** PubMed, Europe PMC, bioRxiv (direct database APIs remained blocked by the sandbox network policy; results below come from web search and accessible front-ends.)
**Prior scan:** `galaxy-agentic-tools-2026-06-28.md`. This update captures items published or surfaced since late June 2026.
**Query intent:** New (mid-2026 → Nov 2026) papers on the Galaxy platform AND/OR agentic / LLM-agent tools for biological data analysis.

---

## A. Galaxy platform — new, directly relevant material

1. **Galaxy for accessible, reproducible, and collaborative data analyses: 2026 update** — *Nucleic Acids Research* 54(W1):W105, published 2026-06-09.
   - https://academic.oup.com/nar/article/54/W1/W105/8704296
   - The biennial Galaxy update paper. Future-directions section explicitly calls out deeper integration of the **Galaxy-MCP** project so external AI clients can interact with Galaxy services.

2. **Galaxy 26.0 release (March 2026) — introduces ChatGXY.** In-platform AI assistant that answers tool/error questions, surfaces training tutorials, recommends tools, and locates Intergalactic Workflow Commission (IWC) workflows.
   - https://docs.galaxyproject.org/en/release_26.0/releases/26.0_announce_user.html

3. **Galaxy 26.1 release (July 2026) — first-class MCP support.** Administrators opt in (`enable_mcp_server`); once enabled, outside MCP-aware AI clients can search/run tools, invoke workflows, and discover IWC workflows. Requests go through Galaxy's existing authz/validation layer. Agent is treated as *untrusted*; sensitive actions are re-validated server-side.
   - https://docs.galaxyproject.org/en/release_26.1/releases/26.1_announce_user.html

4. **Towards LLM-Powered Task-Aware Retrieval of Scientific Workflows for Galaxy** — arXiv 2511.01757 (Nov 2026).
   - Direct follow-through on the "LLM-powered task-aware retrieval" item flagged as unverified in the June scan. Now a posted preprint.
   - https://arxiv.org/pdf/2511.01757

5. **Eight LLMs, one RNA-seq dataset: what we learned controlling Galaxy from Orbit** — Galaxy news, 2026-06-09.
   - Eight frontier LLMs asked to reanalyze a published *Candida auris* RNA-seq study via the Orbit agent and the Galaxy MCP server. Six reproduced the headline result; the failures are reported as the more interesting observations.
   - https://galaxyproject.org/news/2026-06-09-llm-agents-reanalyze-rnaseq/

6. **GCC2026 (Clermont-Ferrand, June 23–26, 2026).** Talks on "Agent Operations" built into Galaxy on top of standalone `galaxy-mcp`; CoFest outcomes write-up (2026-07-20) summarises security posture and planned work.
   - https://galaxyproject.org/events/gcc2026/schedule/
   - https://galaxyproject.org/news/2026-07-20-gcc2026-cofest-outcomes/
   - Abstract book: https://galaxy-community-conference.s3.us-east-1.amazonaws.com/GCC2026-abstract-book.pdf

7. **ELIXIR Biohackathon 2026 — project #31**: proposes LLM agent skills for porting Nextflow workflows into Galaxy and for evaluating FAIRness, exposed via MCP and as a ChatGXY plugin. Proposal, not yet shipped.
   - https://github.com/elixir-europe/biohackathon-projects-2026/blob/main/31.md

8. **`galaxyproject/galaxy-mcp`** — the standalone MCP server; published to PyPI and npm; supports streamable HTTP. Includes a mulled-recommender wrapping `galaxy.tool_util.deps.mulled.recommend` so container images are grounded against quay.io instead of hallucinated.
   - https://github.com/galaxyproject/galaxy-mcp

9. **Process-Reward Tactic Evolution for Long-Horizon Bioinformatics Workflows** — arXiv 2606.20839.
   - Treats workflow construction as an agent-environment problem. Introduces **BioWorkflow Bench** built on Galaxy (26 train / 35 held-out tasks); argues long-horizon agents need persistent process memory.
   - https://arxiv.org/html/2606.20839v1

> **Takeaway for the Galaxy ∩ agentic-AI axis:** the integration thesis flagged in the June 2026 scan has now landed in core Galaxy (ChatGXY in 26.0; MCP in 26.1). Galaxy is now itself an MCP target and an MCP client host — the thread to watch shifts from *will it happen* to *which agent frameworks drive it, and how is correctness validated*.

---

## B. New PubMed / PMC-indexed peer-reviewed work (since June 2026)

| Title | Venue / Date | Link |
|-------|--------------|------|
| **Trustworthy Agentic AI in Bioinformatics: From Workflow Automation to Traceable and Validated Biological Inference** | *Biology* 15(17):1537, 2026-09-04. Structured July-2026 PubMed search → 11 peer-reviewed systems reviewed; proposes claim-to-evidence traceability framework. | [PMC13565537](https://pmc.ncbi.nlm.nih.gov/articles/PMC13565537) · [PubMed 42737969](https://pubmed.ncbi.nlm.nih.gov/42737969/) |
| **Large language model agents for biological intelligence across genomics, proteomics, spatial biology, and biomedicine** | *Briefings in Bioinformatics*, Mar 2026. Systematic synthesis of LLM-based agents across subfields. | [PMC13017847](https://pmc.ncbi.nlm.nih.gov/articles/PMC13017847/) · [PubMed 41883029](https://pubmed.ncbi.nlm.nih.gov/41883029/) |
| **The next paradigm in bioinformatics: a review of multi-agent systems and foundational models for end-to-end scientific discovery** | Review, May 2026. Positions agentic AI as the step beyond predictive/generative models. | [PubMed 42160738](https://pubmed.ncbi.nlm.nih.gov/42160738/) |
| **When intelligence begins to act: a thoughtful appraisal of agentic AI in biomedicine** | Perspective, 2026. | [PubMed 42089750](https://pubmed.ncbi.nlm.nih.gov/42089750/) |
| **Artificial intelligence agents and agentic artificial intelligence applied to precision medicine** | Review covering genomics + regulatory posture, 2026. | [PubMed 42617946](https://pubmed.ncbi.nlm.nih.gov/42617946/) |
| **The rise of agentic AI in drug discovery: from static tools to autonomous virtual scientists** | Perspective with a six-level autonomy scale, 2026. | [PubMed 42864384](https://pubmed.ncbi.nlm.nih.gov/42864384/) |
| **Agentic genomics: from pipeline automation to autonomous validation** | PMC, 2026. Companion-perspective to the "Trustworthy Agentic AI" piece; the autonomous-validation framing is the common thread. | [PMC13477014](https://pmc.ncbi.nlm.nih.gov/articles/PMC13477014) |
| **Agentomics (published version)** | PMC, 2026. Peer-reviewed form of the Jan 2026 bioRxiv preprint. | [PMC13340167](https://pmc.ncbi.nlm.nih.gov/articles/PMC13340167/) |
| **Evaluating open LLMs for agentic analysis orchestration in a typical biomedical lab** | PMC, 2026. Published form of the May 2026 bioRxiv preprint flagged in §A.1 of the June scan — **this is the most directly Galaxy-relevant peer-reviewed article in the current literature.** | [PMC13228249](https://pmc.ncbi.nlm.nih.gov/articles/PMC13228249/) |
| **LLM-based agentic AI tool streamlines research processes in biomarker studies: a proof of concept** | PMC, 2026. | [PMC12795206](https://pmc.ncbi.nlm.nih.gov/articles/PMC12795206/) |
| **Fatumo perspective — "shifting bottleneck from pipeline construction to validation"** | *Cell Genomics* 6(8):101305, 2026-07-21. | (journal page) |

---

## C. High-signal new preprints (mid 2026 → Nov 2026)

| # | Title | Venue / Date | Link |
|---|-------|--------------|------|
| 1 | **AI Models Excel at Orchestration but Falter at Biological Judgment: Findings from an Agentic Gene Annotation Study** | bioRxiv, 2026-09-23 | https://www.biorxiv.org/content/10.64898/2026.09.23.753765v1.full |
| 2 | **biomeStat: Using Agentic AI for Scalable Genomic Epidemiology** — end-to-end analysis of 1,000 Asian dengue genomes in <24 h wall-clock. Deterministic orchestrator over established tools. | bioRxiv, 2026-06-10 | https://www.biorxiv.org/content/10.64898/2026.06.10.731380v1.full |
| 3 | **LungChat: A Conversational Multi-Agent AI System for Integrated single-cell + spatial analysis** | bioRxiv, 2026-08-08 | https://www.biorxiv.org/content/biorxiv/early/2026/08/14/2026.08.08.743577.full.pdf |
| 4 | **ProtCell** — single-cell proteomics foundation model, ~380 M cells across 98 datasets. Masked abundance modelling. | bioRxiv, 2026-10-22 | https://www.biorxiv.org/content/10.64898/2026.10.22.760932v1 |
| 5 | **Open-Rosalind**: tool-first biomedical LLM agents; comes with **Open-Rosalind BioBench** scoring tool correctness, citation presence, trace completeness. | bioRxiv, 2026-05-06 | https://www.biorxiv.org/content/10.64898/2026.05.06.722404v1 |
| 6 | **BiomniBench** — process-level evaluation of LLM agents for biomedical research. | bioRxiv, 2026-05-12 | https://www.biorxiv.org/content/10.64898/2026.05.12.724604v1 |
| 7 | **MechAInistic** — multi-agent LLM system over genome-scale metabolic models. | bioRxiv, 2026-05-11 | https://www.biorxiv.org/content/10.64898/2026.05.11.723319v2 |
| 8 | **PromptBio-Bench v2** — 244 end-to-end bioinformatics tasks across genomics/epigenomics/transcriptomics/proteomics/single-cell/ML. | bioRxiv, 2026-05-05 (v2) | https://www.biorxiv.org/content/10.64898/2026.05.05.723092v2.full |
| 9 | **Evaluating Agentic Bioinformatics through Function, Evidence, and Validation** | arXiv 2607.27556 | https://arxiv.org/pdf/2607.27556 |
| 10 | **From Research Question to Scientific Workflow: Leveraging Agentic AI for Science Automation** | arXiv 2604.21910 | https://arxiv.org/pdf/2604.21910 |
| 11 | **EMBL AI Librarian: Life-Sciences Knowledge Layer for AI Agents** | arXiv 2607.28229 | https://arxiv.org/pdf/2607.28229 |
| 12 | **PRAXIS-VirtualCell** — programmable/trustworthy framework for agentic virtual-cell experiments. | arXiv 2609.29221 | https://arxiv.org/pdf/2609.29221 |
| 13 | **BioVeil MATRIX** — vulnerabilities of agentic biological AI scientists (biosecurity). | arXiv 2605.00927 | https://arxiv.org/pdf/2605.00927 |
| 14 | **LLM4Cell** (survey, v2) — 58 foundation + agentic models for single-cell biology. | arXiv 2510.07793v2 | https://arxiv.org/html/2510.07793v2 |
| 15 | **Deep Research of Deep Research: From Transformer to Agent, From AI to AI for Science** | arXiv 2603.28361 | https://arxiv.org/pdf/2603.28361 |

---

## D. Running patterns (new since June 2026)

- **Orchestration vs. judgment is now the dominant finding.** Multiple independent studies (gene annotation, discovery, benchmarking) converge: current agents are strong at workflow orchestration and broad data exploration; they are weak at biological adjudication, interpretation, and reproducibility.
- **Benchmarks are consolidating.** PromptBio-Bench, BiomniBench, Open-Rosalind BioBench, BioWorkflow Bench, and BioDesignBench now overlap enough to enable cross-system comparison. Expect a shakeout and/or a meta-benchmark in 2027.
- **Trustworthiness / traceability frameworks are moving into peer review.** The Sept-2026 *Biology* paper ("Trustworthy Agentic AI in Bioinformatics") and the "Agentic genomics" perspective both frame claim-to-evidence traceability, not raw capability, as the next evaluation axis. This is consistent with Galaxy's CoFest design principle ("agent is never an authority; sensitive actions re-validated server-side").
- **MCP is now the de-facto integration layer.** Galaxy 26.1 + `galaxy-mcp`, EMBL AI Librarian, pyeuropepmc 4.7.0's agentic extras, and the ELIXIR biohackathon proposal all assume MCP as the wire format. The June 2026 scan's prediction that MCP would be the Galaxy-tool exposure path has materialised.

---

## E. Read-this-first list (updated)

1. **Galaxy 2026 NAR update** (§A.1) — the canonical platform reference; sets up the agentic-integration roadmap.
2. **"Trustworthy Agentic AI in Bioinformatics"** (§B, *Biology* 2026-09) — most useful single frame for evaluating anything new in this space.
3. **"AI Models Excel at Orchestration but Falter at Biological Judgment"** (§C.1) — concrete evidence for the orchestration/judgment split.
4. **Galaxy 26.1 release notes** (§A.3) + **`galaxy-mcp`** repo (§A.8) — operational substrate.
5. **arXiv 2511.01757** (§A.4) — workflow-retrieval mechanism inside Galaxy; the newest Galaxy-specific agentic preprint.

---

## F. Items to verify next scan

- Peer-review status of arXiv 2511.01757, 2607.27556, 2607.28229, 2609.29221.
- Whether the Sept-2026 "AI Models Excel at Orchestration…" bioRxiv preprint reaches a journal version.
- Galaxy 26.2 release (expected ~Nov 2026 per historical cadence) — will it ship additional agent-side features (write-mode MCP, workflow authoring agent, etc.)?
- Whether a formal paper on the Orbit + Galaxy-MCP RNA-seq reanalysis (§A.5) appears beyond the news post.

---

*Caveat (unchanged from June scan):* direct API access to PubMed eutils, Europe PMC REST, bioRxiv API, arxiv.org and biorxiv.org was denied by the sandbox network policy during this scan. The web-search front-end was usable; findings above come from search summaries, PubMed/PMC landing-page snippets, and Galaxy Project pages. DOIs, PubMed IDs, and dates should be re-verified against the primary databases before formal citation.
