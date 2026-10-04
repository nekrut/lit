# Galaxy & Agentic Tools for Biological Data Analysis — Literature Scan

**Scan date:** 2026-10-04
**Previous scan:** 2026-06-28 (`galaxy-agentic-tools-2026-06-28.md`)
**Window emphasized:** July 2026 – early October 2026 (what's new since the prior scan)
**Sources queried:** PubMed, Europe PMC, bioRxiv. *(Direct APIs for `eutils.ncbi.nlm.nih.gov`, `www.ebi.ac.uk`, `api.biorxiv.org`, and `www.biorxiv.org` were all blocked by the sandbox network egress policy, so results below are reconstructed from web-search summaries and accessible HTML pages. DOIs/PMIDs should be verified against the originals before formal citation.)*
**Query intent:** Recent papers on the Galaxy platform AND/OR new agentic / LLM-agent tools for biological data analysis.

---

## TL;DR — what moved since the June 28 scan

1. **Galaxy itself is now an AI-native platform** — the GCC2026 CoFest (July 2026) materialized a concrete `Agent Operations` layer, an `Agent Framework` registry with intent-based routing, and a built-in MCP server, formally building on the standalone `galaxy-mcp` project.
2. **MCP is consolidating as the integration substrate** — `Rhea` (arXiv 2508.18489) and `BioinfoMCP` (arXiv 2510.02139) both argue that static tool registries don't scale and propose retrieval-based tool discovery over thousands of bioinformatics tools. This is directly convergent with the Galaxy Toolshed.
3. **Benchmarks are maturing** — PromptBio-Bench (244 expert-curated tasks) and BixBench put real floors under "agentic bioinformatics" claims.
4. **The first *Science* multi-agent therapeutics paper landed** — "The Virtual Biotech" (Sept 2026 ish).
5. **Review-of-reviews phase has begun** — three distinct 2026 *Briefings in Bioinformatics* survey articles now map the field.

---

## A. Directly Galaxy-related (new or updated since 2026-06-28)

1. **Building an AI-Native Galaxy: Agent Operations, Agent Framework, and MCP** — GCC2026 presentation, July 2026.
   - Authors: Baker Dannon, Chilton John, Van Den Beek Marius.
   - Delivers (a) a shared operations layer for tools / histories / datasets / workflows / jobs / IWC integration exposed via a built-in MCP server; (b) a registry of specialized agents with intent-based routing, handoffs, and multi-agent orchestration; (c) an evaluation framework for end-to-end computational biology analyses *inside* Galaxy.
   - URL: https://galaxyproject.org/news/2026-07-20-gcc2026-cofest-outcomes/

2. **`galaxy-mcp` (GitHub)** — Model Context Protocol server for Galaxy; lets any MCP-compatible client connect to Galaxy instances, search and execute tools, manage workflows, and access the Galaxy ecosystem.
   - https://github.com/galaxyproject/galaxy-mcp

3. **Rhea: a scalable MCP tool framework to serve thousands of biomedical tools to LLMs** — arXiv 2508.18489.
   - Replaces static registries with retrieval-based discovery; the paper's framing of "thousands of tools" is a natural fit for the Galaxy Toolshed.
   - URL: https://arxiv.org/pdf/2508.18489

4. **Evaluating open LLMs for agentic analysis orchestration in a typical biomedical lab** — bioRxiv May 2026 (carried forward from prior scan; now also indexed as **PMC13228249**).
   - URL: https://pmc.ncbi.nlm.nih.gov/articles/PMC13228249/
   - Still the single most Galaxy-tooling-specific agentic-bioinformatics paper in the literature.

---

## B. New agentic AI preprints for biology (bioRxiv, July–October 2026)

| # | Title | Date | Link |
|---|-------|------|------|
| 1 | **Detailed curation of biological samples and experimental designs for genomics using LLM-supported agentic workflows** | 2026-07-30 | https://www.biorxiv.org/content/10.64898/2026.07.30.741874v1 |
| 2 | **PromptBio-Bench: Benchmarking LLM-based Bioinformatics Agents for End-to-End Data Analysis** (v2) | 2026 (updated) | https://www.biorxiv.org/content/10.64898/2026.05.05.723092v2.full |
| 3 | **biomeStat: Using Agentic AI for Scalable Genomic Epidemiology — End-to-End Analysis of 1,000 Asian Dengue Virus Genomes** | 2026-06-10 | https://www.biorxiv.org/content/10.64898/2026.06.10.731380v1.full |
| 4 | **GroundAnnot: a closed-vocabulary contract for grounding LLM gene-set annotation in live enrichment backends** | 2026-10-02 | (bioRxiv — resolve via title) |
| 5 | **A gated agentic AI QSP workflow applied to healthy ageing interventions** | 2026-10-01 | (bioRxiv — resolve via title) |
| 6 | **A Biosecurity Agent for Lifecycle LLM Biosecurity Alignment** | 2025-09-17 | https://www.biorxiv.org/content/10.1101/2025.09.17.676717v1 |
| 7 | **Out-of-the-box bioinformatics capabilities of large language models (LLMs)** | 2025-08-22 | https://www.biorxiv.org/content/10.1101/2025.08.22.671610v1 |

Items 4 and 5 surfaced only via bioRxiv's October 2026 directory listing — titles should be re-verified before citation.

---

## C. New peer-reviewed journal articles (2026)

- **The Virtual Biotech: A multi-agent AI framework for therapeutic discovery and development** — *Science* (2026). First *Science*-tier multi-agent framework for drug discovery. https://www.science.org/doi/10.1126/science.aeg6779
- **When intelligence begins to act: a thoughtful appraisal of agentic AI in biomedicine** — *Briefings in Bioinformatics* (2026). PMID 42089750. https://pubmed.ncbi.nlm.nih.gov/42089750/
- **Agentic AI integrated with scientific knowledge: laboratory validation in systems biology** — PMID 42413936. https://pubmed.ncbi.nlm.nih.gov/42413936/
- **Large language model agents for biological intelligence across genomics, proteomics, spatial biology, and biomedicine** — *Briefings in Bioinformatics* 27(2), bbag110 (2026). Also indexed under PMID 41883029. https://academic.oup.com/bib/article/27/2/bbag110/8540361
- **The next paradigm in bioinformatics: a review of multi-agent systems and foundational models for end-to-end scientific discovery** — *Briefings in Bioinformatics* (May 2026).
- **Streamline automated biomedical discoveries with agentic bioinformatics** — *Briefings in Bioinformatics* 26(5), bbaf505. PMC12476841. https://academic.oup.com/bib/article/26/5/bbaf505/8266996
- **Rise and potential opportunities of large language model agents in bioinformatics and biomedicine** — *Briefings in Bioinformatics* 26(6), bbaf601. https://academic.oup.com/bib/article/26/6/bbaf601/8320153
- **A data-intelligence-intensive bioinformatics copilot system for large-scale omics research and scientific insights** — *Briefings in Bioinformatics* (2025).

---

## D. New / updated MCP-for-bioinformatics work

- **Rhea** — arXiv 2508.18489 (retrieval-based discovery over thousands of biomedical tools). https://arxiv.org/pdf/2508.18489
- **BioinfoMCP** — arXiv 2510.02139. Auto-generates MCP servers from tool documentation using LLMs; benchmark reports 94.7% successful execution of complex workflows across three agent platforms on 38 converted tools. https://arxiv.org/abs/2510.02139
- **Experiences with Model Context Protocol Servers for Science and HPC** — arXiv 2508.18489 (overlaps the Rhea framing). https://arxiv.org/pdf/2508.18489
- **MCPmed** — PMC12927880. Community proposal with lightweight "breadcrumbs" for services not yet fully MCP-enabled; implementations across GEO, STRING, UCSC Cell Browser. (carried from prior scan). https://www.ncbi.nlm.nih.gov/pmc/articles/PMC12927880/

**Why this cluster matters for Galaxy:** Rhea's RAG-over-tool-descriptions approach and BioinfoMCP's auto-converter are both plausible blueprints for exposing the Galaxy Toolshed to arbitrary agents without per-tool bespoke integration — the same architectural bet the GCC2026 Agent Operations work is making.

---

## E. New arXiv work worth tracking

- **Evaluating Agentic Bioinformatics through Function, Evidence, and Validation** — arXiv 2607.27556. https://arxiv.org/pdf/2607.27556
- **Bioinfoysis Technical Report** — arXiv 2609.03871. https://arxiv.org/pdf/2609.03871
- **From Research Question to Scientific Workflow: Leveraging Agentic AI for Science Automation** — arXiv 2604.21910. https://arxiv.org/pdf/2604.21910
- **BixBench3: Benchmarking AI agents on research-study-scale computational biology tasks** — arXiv 2608.25286. https://arxiv.org/pdf/2608.25286
- **Mimosa: Toward Evolving Multi-Agent Systems for Scientific Research** — arXiv 2603.28986. https://arxiv.org/pdf/2603.28986
- **Public-Sharing Labels and Verbatim Field Egress in an MCP-to-A2A Agent Configuration** — arXiv 2609.01693. https://arxiv.org/pdf/2609.01693

---

## F. Named agents / systems (delta since 2026-06-28)

| Agent | Status | What's new |
|-------|--------|------------|
| **Galaxy Agent Operations + Agent Framework** | Announced at GCC2026 CoFest (Jul 2026) | *New entry in this scan.* First-class Galaxy-internal agentic layer. |
| **Rhea** | arXiv 2508.18489 | *New entry.* MCP-based RAG tool discovery for biomedical tools at Toolshed scale. |
| **BioinfoMCP** | arXiv 2510.02139 | *New entry.* Auto-converter from tool docs → MCP server. |
| **biomeStat** | bioRxiv Jun 2026 | *New entry.* Autonomous phylodynamics on 1,000 dengue genomes end-to-end. |
| **The Virtual Biotech** | *Science* 2026 | *New entry.* Multi-agent therapeutic-discovery framework. |
| **Biomni** (Stanford) | Still active | 150 tools / 105 packages / 59 databases; now also surfaced in general-audience press. |
| **BioMaster** | Jan 2025 | Still cited as the reference multi-agent bioinformatics pipeline. |
| **CellAgent / CellAtria / CellVoyager / scAgent / Teddy** | Carried from prior scan | No major 2026-Q3 updates surfaced. |
| **CRISPR-GPT / Paper2Agent / TusoAI / CellForge** | Carried from prior scan | Unchanged. |

Community tracker: https://github.com/aristoteleo/awesome-bioagent-papers

---

## G. What to read first

If reading just one thing this cycle, start with the **GCC2026 CoFest outcomes write-up** — it's the clearest statement to date of how the Galaxy project itself is positioning for the agentic era.

The highest-leverage external pairing is **Rhea (arXiv 2508.18489) + BioinfoMCP (arXiv 2510.02139)** read back-to-back: together they bracket the design space for scaling MCP to a Toolshed-sized tool catalogue.

For the strongest end-to-end agentic-biology demonstration this quarter, **biomeStat** (dengue phylodynamics on 1,000 genomes) is the clearest "the agent actually did the whole thing" result; **PromptBio-Bench v2** is the complementary evaluation story.

---

## H. Caveats

1. Direct API access to PubMed eutils (`eutils.ncbi.nlm.nih.gov`), Europe PMC REST (`www.ebi.ac.uk`), and the bioRxiv API/front-end (`api.biorxiv.org`, `www.biorxiv.org`) were all **blocked by the sandbox network egress proxy** during this scan. The entries above come from WebSearch summaries and the accessible HTML pages the proxy did allow (e.g., `pmc.ncbi.nlm.nih.gov`, `academic.oup.com`, `arxiv.org`, `galaxyproject.org`, `nature.com`, `science.org`).
2. For the two October 2026 bioRxiv items (GroundAnnot; the gated QSP agentic workflow) only titles were recoverable — DOIs still need to be looked up directly on bioRxiv.
3. PubMed PMIDs in the 42-million range (e.g., 42089750, 42413936) were surfaced via Google-indexed PubMed pages; worth sanity-checking against the live PubMed record once the egress proxy allows `pubmed.ncbi.nlm.nih.gov` again.
