# Galaxy & Agentic Tools for Biological Data Analysis — Literature Scan

**Scan date:** 2026-11-01
**Sources queried:** PubMed, Europe PMC, bioRxiv (direct APIs for eutils.ncbi.nlm.nih.gov, www.ebi.ac.uk/europepmc, and api.biorxiv.org were again blocked by the sandbox network policy — see Caveats; results below come from web search, publisher front-ends, and the Galaxy project's own site).
**Prior scan:** `galaxy-agentic-tools-2026-06-28.md` (June 2026). This file emphasizes what is **new or updated since then** (≈ July–October 2026) rather than re-listing the June catalogue.
**Query intent:** Recent papers and preprints on the Galaxy platform AND/OR new agentic / LLM-agent tools for biological data analysis.

---

## TL;DR — what changed since June

1. **Galaxy ∩ LLM agents is now a shipping thing, not a thought experiment.** A Galaxy-side MCP server is being driven in anger by multiple LLMs, with publicly reported results. See §A.
2. **The agentic-bioinformatics benchmark landscape has consolidated.** BioAgent Bench, BiomniBench, PromptBio-Bench, and BixBench3 together form a working harness; the June scan predates most of these. See §B.
3. **MCP for bioinformatics has moved from "proposal" to "peer-reviewed catalyst narrative."** MCPmed is now indexed in PubMed; a PLOS Comp Biol perspective explicitly frames MCP as the bioinformatics interoperability catalyst of the next decade. See §C.
4. **One high-signal October 2026 bioRxiv preprint** reports thousands of parallel agents recovering a whole-brain Perturb-seq paper's conclusions *without seeing the paper*, with blinded experts preferring the agent output to single-agent interpretations. See §B item 6.

---

## A. Directly Galaxy-related (new / updated since June)

1. **"Eight LLMs, one RNA-seq dataset: what we learned controlling Galaxy from Orbit"** — Galaxy Project news post, 2026-06-09.
   - URL: https://galaxyproject.org/news/2026-06-09-llm-agents-reanalyze-rnaseq/
   - Eight LLMs each reanalyzed the same *Candida auris* RNA-seq dataset through Galaxy's **Orbit** agent, connected via the **Galaxy MCP server**. Six reproduced the headline result; the failure modes are reported as the more instructive part. First concrete public write-up of the Galaxy MCP server in use.

2. **GCC2026 — "Benchmarking AI agents in Galaxy"** (Galaxy Community Conference 2026 schedule).
   - URL: https://galaxyproject.org/events/gcc2026/schedule/
   - Community talk describing a **dual evaluation framework** covering both Galaxy's native agents and external agents operating inside Galaxy. Confirms this is now an organized workstream, not a one-off project.

3. **ELIXIR BioHackathon 2026 — Project 31: "Nextflow → Galaxy with LLM-agent skills + FAIRness evaluator."**
   - URL: https://github.com/elixir-europe/biohackathon-projects-2026/blob/main/31.md
   - Proposes porting Nextflow workflows into Galaxy via LLM-agent skills, exposed through an MCP server and a **ChatGXY** plugin inside Galaxy. Interesting signal: both Nextflow and Galaxy are deliberately being made addressable by the same agent surface.

4. **Process-Reward Tactic Evolution for Long-Horizon Bioinformatics Workflows** — arXiv 2606.20839.
   - URL: https://arxiv.org/pdf/2606.20839
   - Training framework where agents learn to build and run **Galaxy workflows**; verifier scores each step; successful and failed runs feed a reusable "tactic library." Evaluated on **BioWorkflow Bench** and **BioAgent Bench**. Core thesis: without persistent process memory, long-horizon agents waste context on software recovery instead of science.

5. **GalaxyMemMD: an end-to-end Galaxy toolset for reproducible membrane embedding, molecular dynamics simulation, and analysis of membrane proteins** — bioRxiv 2026.09.28.755125, posted Sep 2026.
   - URL: https://www.biorxiv.org/content/10.64898/2026.09.28.755125v1.full
   - Not agentic, but a notable Galaxy platform addition: ToolShed-installable, end-to-end membrane-protein MD. Worth noting if any downstream agentic work needs an MD tool-call surface.

6. **Microbiology Galaxy Lab** (community gateway for microbial data, v3 on bioRxiv).
   - URL: https://www.biorxiv.org/content/10.1101/2024.12.23.629682v3.full
   - 315+ tool suites, 115+ curated workflows; the broader "domain-specific Galaxy lab" concept the agentic layer will plug into.

---

## B. Agentic AI for biology — new or newly peer-reviewed (July–Oct 2026)

| # | Title | Venue / Date | Link | Why it matters |
|---|-------|--------------|------|----------------|
| 1 | **BioAgent Bench: An AI Agent Evaluation Suite for Bioinformatics** (accepted ICML 2026) | arXiv 2601.21800 | https://arxiv.org/html/2601.21800v1 | 10 curated tasks; frontier models (Claude Opus 4.5, Gemini 3 Pro) reach near-perfect completion — raises the bar from pre-2026 BixBench's ~17% |
| 2 | **BiomniBench: Process-level Evaluation of LLM Agents for Real-world Biomedical Research** | bioRxiv 2026.05.12.724604, May 2026 | https://www.biorxiv.org/content/10.64898/2026.05.12.724604v1 | Scores full trajectory, not just outcome; 100 tasks across 17 types. Finding: **the agent harness shifts scores more than the gap between successive model generations.** |
| 3 | **PromptBio-Bench: Benchmarking LLM-based Bioinformatics Agents for End-to-End Data Analysis** (v2) | bioRxiv 2026.05.05.723092 v2 | https://www.biorxiv.org/content/10.64898/2026.05.05.723092v2.full | 244 expert-curated tasks across 3 difficulty tiers; evaluates Biomni, STELLA, ToolsGenie |
| 4 | **BixBench3: Benchmarking AI agents on research-study-scale computational biology tasks** | arXiv 2608.25286 | https://arxiv.org/pdf/2608.25286 | Scales previous BixBench up to study-sized tasks |
| 5 | **Evaluating Agentic Bioinformatics through Function, Evidence, and Validation** | arXiv 2607.27556 | https://arxiv.org/pdf/2607.27556 | Three-axis eval scheme; complements outcome-only benchmarks |
| 6 | **Distributed AI agents enable comprehensive discovery of biological insights at scale** | bioRxiv 2026.10.15.759436, Oct 2026 | https://www.biorxiv.org/content/10.64898/2026.10.15.759436v1 | **Headline result:** thousands of parallel agents applied to a whole-brain Perturb-seq atlas recovered the source paper's conclusions without access to it; blinded experts preferred the distributed output to single-agent interpretations; minutes vs estimated months |
| 7 | **biomeStat: Using Agentic AI for Scalable Genomic Epidemiology** | bioRxiv 2026.06.10.731380, Jun 2026 | https://www.biorxiv.org/content/10.64898/2026.06.10.731380v1.full | End-to-end agentic analysis of 1,000 Asian dengue virus genomes in <24h |
| 8 | **BioMedAgent: self-evolving multi-agent LLM framework for autonomous tool-aware biomedical data analysis** | *Nature Biomedical Engineering*, Mar 2026 (PubMed 41912700) | https://pubmed.ncbi.nlm.nih.gov/41912700/ | 77% success on a 327-task benchmark; self-evolving tool composition |
| 9 | **Agents for Everyone: A Workshop Framework for Building Agentic AI Capabilities in a Distributed Curation Community** | arXiv 2608.27675 | — | Social/organizational scaffolding for curation-community adoption |
| 10 | **Bioinfoysis Technical Report** | arXiv 2609.03871 | https://arxiv.org/pdf/2609.03871 | New agentic bioinformatics system; details to verify |
| 11 | **From Research Question to Scientific Workflow: Leveraging Agentic AI for Science Automation** | arXiv 2604.21910 | https://arxiv.org/pdf/2604.21910 | Broader scientific-automation framing; good context for the Galaxy workflow-generation thread |
| 12 | **Llemy: User-driven development and evaluation of an agentic framework for analysis of large pathway diagrams** | *Bioinformatics Advances*, 2026 | — (verify via journal) | Agent for molecular interaction map exploration |
| 13 | **ELISA: Interpretable Hybrid Generative AI Agent for Expression-Grounded Discovery in Single-Cell Genomics** | arXiv 2603.11872 | https://arxiv.org/pdf/2603.11872 | scGPT + BioBERT retrieval + LLM interpretation; outperforms CellWhisperer on cell-type retrieval |

---

## C. MCP for bioinformatics — now peer-reviewed

- **MCPmed: a call for Model Context Protocol-enabled bioinformatics web services for LLM-driven discovery** — *Briefings in Bioinformatics* 27(1), Jan 2026; PubMed **41729821**.
  - https://pubmed.ncbi.nlm.nih.gov/41729821/
  - https://academic.oup.com/bib/article/27/1/bbag076/8495038
  - Reference implementations across GEO, STRING, and UCSC Cell Browser; community templates for new MCP servers.
- **Model Context Protocol: The unexpected catalyst of a bioinformatics interoperability revolution** — *PLOS Computational Biology*, 2026-08-31; PMC13528949.
  - https://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1014543
  - Perspective: argues MCP is the interoperability catalyst of the coming decade; notes the **MCP 2026 revision made the protocol core stateless** and moved several capabilities into independently versioned extensions.

Combined with §A.1 (the Galaxy MCP server driving Orbit) and §A.3 (ChatGXY plugin via MCP), this is the single most actionable thread for anyone exposing Galaxy tool wrappers to agents.

---

## D. Reviews / surveys worth noting (2026)

- **From foundation models to autonomous agents in biology** — Max Press / *Genomics Communications*, 2026. https://maxapress.com/data/article/gcomm/preview/pdf/gcomm-0026-0005.pdf
- **Artificial Intelligence agents for biological research: a survey** — *Briefings in Bioinformatics* 27(1), Jan 2026 (previously catalogued in June scan).
- **LLM4Cell: A Survey of Large Language and Agentic Models for Single-Cell Biology** — arXiv 2510.07793 (previously catalogued).

---

## E. What is NOT in this update

Items from the June 2026 scan that have no new material since then are intentionally omitted here, including: Biomni, BioMaster, CellAgent, BIA, CellAtria, CellVoyager / CellVerse / scAgent / Teddy, CRISPR-GPT, Paper2Agent, TusoAI, CellForge, HeurekaBench, and the Agentomics / BioTrouble / M3A / Protein-design-benchmark cluster. See `galaxy-agentic-tools-2026-06-28.md` §E and §B for those.

---

## F. Implications / what to read first

If the goal is "**what's new at the Galaxy ∩ agentic-AI intersection**," read in this order:

1. The Galaxy "Orbit + MCP" blog post (§A.1) — this is the only item that shows the Galaxy MCP server driven by frontier LLMs with public results.
2. The Process-Reward Tactic Evolution paper (§A.4) — operationalizes a tactic library against Galaxy workflows and introduces the BioWorkflow Bench harness.
3. The MCPmed journal version (§C) and the PLOS Comp Biol MCP perspective — these frame how Galaxy tool wrappers can be exposed to any agent without bespoke integration work.
4. The distributed-agents Perturb-seq preprint (§B.6) — not Galaxy-specific, but the most striking agentic-biology discovery result in this cycle; sets a plausible ceiling for what agent swarms over Galaxy workflows could claim.

---

## Caveats

- Direct access to the NCBI eutils, Europe PMC REST, and bioRxiv APIs was again denied by the sandbox network policy (same symptom as the June scan: `CONNECT tunnel failed, response 403` on `eutils.ncbi.nlm.nih.gov`, `www.ebi.ac.uk`, `api.biorxiv.org`). Direct `WebFetch` of specific bioRxiv URLs also failed (DNS not resolved for `www.biorxiv.org`).
- Findings above come from web-search summaries, publisher front-ends, and the Galaxy project's own site. Titles, DOIs, and venues should be verified against the primary databases before formal citation.
- For a programmatic future scan, these three hosts need to be allowed in the session's network settings: `eutils.ncbi.nlm.nih.gov`, `www.ebi.ac.uk`, `api.biorxiv.org` (plus `www.biorxiv.org` for front-end reads).
