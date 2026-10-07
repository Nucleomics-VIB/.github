<div align="center">

# VIB Nucleomics Core

**Sequencing, analysis, and the code in between.**

We run long- and short-read sequencing for the VIB research community and build the
pipelines, toolboxes, and web tools that turn raw instrument output into answers.
This organization holds that code — from one-line `awk` helpers to containerised
Nextflow pipelines.

[![repos](https://img.shields.io/badge/public_repos-29-1f6feb)](https://github.com/orgs/Nucleomics-VIB/repositories)
[![platforms](https://img.shields.io/badge/platforms-PacBio_·_ONT_·_AVITI_·_MGI-2da44e)](#families)
[![licence](https://img.shields.io/badge/licence-GPL--3.0-8250df)](https://www.gnu.org/licenses/gpl-3.0)

</div>

---

## Start here

You almost certainly arrived holding data. Find the row that matches it.

| You have… | Start with | Then reach for |
|---|---|---|
| PacBio Revio / Kinnex HiFi reads | [pacbio-tools](https://github.com/Nucleomics-VIB/pacbio-tools) | [Kinnex_16S_decat_demux_bash](https://github.com/Nucleomics-VIB/Kinnex_16S_decat_demux_bash) → [hifi-16s-workflow-nc](https://github.com/Nucleomics-VIB/hifi-16s-workflow-nc) |
| Oxford Nanopore reads | [nanopore-tools](https://github.com/Nucleomics-VIB/nanopore-tools) | [ngs-tools](https://github.com/Nucleomics-VIB/ngs-tools) |
| Element **AVITI** output | [aviti-tools](https://github.com/Nucleomics-VIB/aviti-tools) | [variant-analysis](https://github.com/Nucleomics-VIB/variant-analysis) |
| Full-length **16S** amplicons | [hifi-16s-workflow-nc](https://github.com/Nucleomics-VIB/hifi-16s-workflow-nc) | [benchmarks](https://github.com/Nucleomics-VIB/benchmarks) |
| Fungal / eukaryote **ITS** amplicons | [nextits-nc](https://github.com/Nucleomics-VIB/nextits-nc) | [create-fungi-rdna-database](https://github.com/Nucleomics-VIB/create-fungi-rdna-database) |
| Bulk RNA-seq (BRB-seq) | [brbseq-tools](https://github.com/Nucleomics-VIB/brbseq-tools) | — |
| A plot to make or an app to share | [plotting-tools](https://github.com/Nucleomics-VIB/plotting-tools) | [shiny-apps](https://github.com/Nucleomics-VIB/shiny-apps) |
| A server to wrangle, files to move | [admin-tools](https://github.com/Nucleomics-VIB/admin-tools) | [cloud-dl-plus](https://github.com/Nucleomics-VIB/cloud-dl-plus) |

## How the code fits together

```mermaid
flowchart LR
  I["🧬 Instrument<br/>PacBio · ONT · AVITI · MGI"]
  P["Platform toolkits<br/><i>pacbio-tools · nanopore-tools<br/>aviti-tools · ngs-tools</i>"]
  A["Assay pipelines<br/><i>16S · ITS · exome · shotgun</i>"]
  V["Variants & genomes<br/><i>variant-analysis · chimericseq-nc</i>"]
  R["Figures & apps<br/><i>plotting-tools · shiny-apps</i>"]
  D["📦 Delivery to the researcher"]

  I --> P --> A --> R --> D
  P --> V --> R
  O["Core operations<br/><i>admin-tools · cloud-dl-plus</i>"] -.-> P
  O -.-> A
  O -.-> D
```

Platform toolkits do the demultiplexing and QC that every project needs. Assay
pipelines take it from there. Reporting code is deliberately separate, so the same
figures can be regenerated years later.

<a name="families"></a>
## Families

Each family has its own index with a repo-by-repo breakdown.

| Family | What lives there | Index |
|---|---|---|
| 🧪 **Sequencing platform toolkits** | Per-instrument toolboxes: demultiplexing, QC, run parsing, format wrangling | [browse →](https://github.com/Nucleomics-VIB/.github/blob/main/profile/families/sequencing-platforms.md) |
| 🦠 **Amplicon & metabarcoding** | 16S, ITS and Kinnex pipelines from raw reads to taxonomy tables | [browse →](https://github.com/Nucleomics-VIB/.github/blob/main/profile/families/amplicon-metabarcoding.md) |
| 🧫 **Genomes & variants** | Variant calling, assembly QC, chimera and transcript analysis | [browse →](https://github.com/Nucleomics-VIB/.github/blob/main/profile/families/genomes-variants.md) |
| 📊 **Visualization & reporting** | Publication-quality figures, interactive Shiny apps, method benchmarks | [browse →](https://github.com/Nucleomics-VIB/.github/blob/main/profile/families/visualization-reporting.md) |
| ⚙️ **Core operations** | Sysadmin helpers, data movement, day-to-day glue | [browse →](https://github.com/Nucleomics-VIB/.github/blob/main/profile/families/core-operations.md) |
| 🏛️ **Legacy & reference** | Stable, still-cited, no longer actively developed | [browse →](https://github.com/Nucleomics-VIB/.github/blob/main/profile/families/legacy.md) |

Prefer to browse rather than be routed?
**[All repositories on GitHub →](https://github.com/orgs/Nucleomics-VIB/repositories?sort=updated)**
— ordered by last push. Note that org-wide maintenance batches (licence and template
sweeps) count as pushes, so recent dates there do not always mean recent work.

## Reading a repo name

Names are lowercase words joined by `-`, with no prefix. A name says what the repo is
for. What kind of thing it is (pipeline, container, web tool) is in its topics, below.
A few suffixes carry a meaning:

| Suffix | Meaning | Example |
|---|---|---|
| `-tools` | A toolbox of many small, independent scripts for one platform or domain | `pacbio-tools` |
| `-nc` | Our version of code whose name belongs to someone else: a fork, or a wrapper around an upstream tool | `nextits-nc` |
| `-plus` | A later, extended version of a sibling repo that keeps the plain name | `cloud-dl-plus` |
| `-engine` | The compute half of a pipeline that also has a web front end | *(mostly internal)* |

Other words in a name, such as `-analysis` or `-study`, are part of what the repo is for.

Most repos took these names in September 2026. GitHub redirects the old names
(for example `NC_HiFi-16S-workflow` or `Shiny-apps`), so old links and clones still
work. To update a clone, run `git remote set-url origin` with the new URL.

## Filter by topic

Every repository carries topics on four axes. These are curated, not guessed — filtering
on one gives you a real shortlist:

| Axis | Pick one | |
|---|---|---|
| **Platform** | [pacbio](https://github.com/orgs/Nucleomics-VIB/repositories?q=topic%3Apacbio) · [nanopore](https://github.com/orgs/Nucleomics-VIB/repositories?q=topic%3Ananopore) · [aviti](https://github.com/orgs/Nucleomics-VIB/repositories?q=topic%3Aaviti) · [mgi](https://github.com/orgs/Nucleomics-VIB/repositories?q=topic%3Amgi) | which instrument made the data |
| **Assay** | [16s](https://github.com/orgs/Nucleomics-VIB/repositories?q=topic%3A16s) · [its](https://github.com/orgs/Nucleomics-VIB/repositories?q=topic%3Aits) · [amplicon](https://github.com/orgs/Nucleomics-VIB/repositories?q=topic%3Aamplicon) · [shotgun](https://github.com/Nucleomics-VIB/.github/blob/main/profile/families/amplicon-metabarcoding.md) · [rnaseq](https://github.com/orgs/Nucleomics-VIB/repositories?q=topic%3Arnaseq) · [assembly](https://github.com/Nucleomics-VIB/.github/blob/main/profile/families/genomes-variants.md) · [variant-calling](https://github.com/orgs/Nucleomics-VIB/repositories?q=topic%3Avariant-calling) | what was done to it |
| **Shape** | [pipeline](https://github.com/orgs/Nucleomics-VIB/repositories?q=topic%3Apipeline) · [toolbox](https://github.com/orgs/Nucleomics-VIB/repositories?q=topic%3Atoolbox) · [container](https://github.com/orgs/Nucleomics-VIB/repositories?q=topic%3Acontainer) · [shiny-app](https://github.com/orgs/Nucleomics-VIB/repositories?q=topic%3Ashiny-app) · [visualization](https://github.com/orgs/Nucleomics-VIB/repositories?q=topic%3Avisualization) · [benchmark](https://github.com/orgs/Nucleomics-VIB/repositories?q=topic%3Abenchmark) | what kind of thing it is |
| **Lifecycle** | [legacy](https://github.com/orgs/Nucleomics-VIB/repositories?q=topic%3Alegacy) | stable, no longer developed |

Language topics (`bash`, `python`, `r`, `nextflow`) are there too, but they describe how
it is written rather than what it does.

`shotgun` and `assembly` link to a family page rather than a filter: the repos carrying
those topics are internal, so the filter would return nothing to a visitor.

> **A note on what you can see.** A good part of the Core's code is internal:
> LIMS-adjacent web tools, instrument dashboards, pricing calculators, and
> infrastructure that only makes sense inside our network. Those repos are private
> and deliberately absent from this page. Everything indexed here is public and
> usable outside VIB.

## Using our code

Our code is licensed **[GPL-3.0](https://www.gnu.org/licenses/gpl-3.0)**: use it, adapt it,
redistribute it — credit **VIB Nucleomics Core** and licence derived work under the same
terms. Documentation and tutorial repos carry
**[CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/)** instead, and each repo's
`LICENSE` is authoritative — the few repos forked from upstream projects keep the upstream
licence. Everything was relicensed on 2026-08-27 from CC BY-SA 3.0, which no licence scanner
could read and which Creative Commons does not recommend for source code; copies obtained
before that date remain available under the old terms.

The code is written to be read, mostly Bash and R with comments rather than frameworks. A few
caveats before you clone:

- **Pipelines assume our reference layout.** Paths and reference genome locations are
  usually configurable at the top of the script; check there first.
- **Container images beat manual installs.** Where a `-engine` sibling exists, use it.
- **Issues are welcome**, including from outside VIB. We read them.

## Credits

Created and maintained by **Stephane Plaisance** — **VIB Nucleomics Core**.

Contributions from the Core's bioinformatics and lab teams across the repos listed above.

<sub>Org profile v1.3.1 · 2026-10-07 · <a href="https://www.nucleomics.be">nucleomics.be</a></sub>
