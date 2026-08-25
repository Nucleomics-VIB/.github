# 🏛️ Legacy & reference

Repos that are stable, occasionally still cited, and **no longer actively developed**.
Nothing here is deleted — some of it is the most-referenced code in the organization
— but expect no new commits, and expect dependencies to have moved on.

Kept because someone still clones it, or because a current repo grew out of it.

| Repo | Why it is still here | Superseded by | Last active |
|---|---|---|---|
| [bionano-tools](https://github.com/Nucleomics-VIB/bionano-tools) ⭐34 | Our most-starred repo by a wide margin. Custom tools for BioNano Genomics optical-mapping data, from the era when we ran that platform. Still the reference implementation for several BioNano file formats | — (platform retired) | 2018-10 |
| [InSilico_PCR](https://github.com/Nucleomics-VIB/InSilico_PCR) ⭐6 | Extract long-read subsequences from a primer pair — pull amplicons out of existing reads without touching the bench. Genuinely useful and still works | — | 2022-02 |
| [16S_analysis_pipeline](https://github.com/Nucleomics-VIB/16S_analysis_pipeline) ⭐1 | Our first automated 16S pipeline, covering paired short reads and early long reads. Historical interest; the current route is far better | [NC_HiFi-16S-workflow](https://github.com/Nucleomics-VIB/NC_HiFi-16S-workflow) | 2023-01 |
| [pb-16S-nf_tutorial](https://github.com/Nucleomics-VIB/pb-16S-nf_tutorial) | Walkthrough of PacBio 16S analysis with `pb-16S-nf`, the upstream pipeline our own workflow descends from | [NC_HiFi-16S-workflow](https://github.com/Nucleomics-VIB/NC_HiFi-16S-workflow) | 2023-01 |
| [Nanopore_Pinfish_Analysis](https://github.com/Nucleomics-VIB/Nanopore_Pinfish_Analysis) ⭐1 | Customised reporting of ONT `pinfish` transcript-annotation results, with R Markdown and Snakemake | — (`pinfish` deprecated upstream) | 2019-09 |
| [nanopore-tools_wiki](https://github.com/Nucleomics-VIB/nanopore-tools_wiki) | Companion notes and documentation for [nanopore-tools](https://github.com/Nucleomics-VIB/nanopore-tools), which is still current | — (reference for an active repo) | 2019-08 |
| [mgi-tools](https://github.com/Nucleomics-VIB/mgi-tools) | Parsers and wrappers for MGI/BGI sequencer output | — (platform retired) | 2023-06 |
| [Opentrons](https://github.com/Nucleomics-VIB/Opentrons) | Early protocols and utilities for our Opentrons liquid-handling robots. Lab automation continues internally | *(continues internally)* | 2022-12 |
| [cloud-dl](https://github.com/Nucleomics-VIB/cloud-dl) ⭐1 | First Nextcloud command-line manager | [NC_cloud-dl](https://github.com/Nucleomics-VIB/NC_cloud-dl) | 2021-05 |
| [mplotter](https://github.com/Nucleomics-VIB/mplotter) ⭐1 | Publication-quality dot plots from MUMmer alignments via `ggplot2`. Small, focused, still functional | [plotting-tools](https://github.com/Nucleomics-VIB/plotting-tools) | 2020-03 |
| [circos-tools](https://github.com/Nucleomics-VIB/circos-tools) ⭐1 | Helpers for building Circos circular-genome figures | [plotting-tools](https://github.com/Nucleomics-VIB/plotting-tools) | 2018-02 |
| [genepattern-tools](https://github.com/Nucleomics-VIB/genepattern-tools) | Scripts and wrappers for GenePattern modules, from when we hosted a GenePattern server | — (service retired) | 2019-01 |

## Before you clone something from this list

- **Pinned dependencies have rotted.** Perl and R code from 2018 will need a
  contemporary environment; a container is your friend.
- **Check the successor column first.** If a current repo is listed, use it.
- **Issues here may go unanswered.** Open one anyway if you find a real bug in
  something you depend on — `bionano-tools` and `InSilico_PCR` still get attention.
