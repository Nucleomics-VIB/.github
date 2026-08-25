# 🧫 Genomes & variants

Everything downstream of alignment that is *not* amplicon work: calling and filtering
small variants, checking assemblies, and the specialised analyses that come up when a
library type does something unusual.

| Repo | What it does | Language | Last active |
|---|---|---|---|
| [variant_analysis](https://github.com/Nucleomics-VIB/variant_analysis) | Practical small-variant analysis on a server: alignment, GATK-style calling, filtering, and annotation, written as readable steps rather than a black box. The starting point for exome and targeted-panel work | Bash, Python | 2026-02 |
| [ChimericSeq](https://github.com/Nucleomics-VIB/ChimericSeq) | Detection and characterisation of chimeric reads — integration sites, vector–genome junctions, and library artefacts. Ships with test reads so you can verify behaviour before trusting it on your data | Python | 2025-03 |
| [BRBseq-tools](https://github.com/Nucleomics-VIB/BRBseq-tools) | Processing for BRB-seq bulk RNA-seq libraries: demultiplexing by well barcode, UMI handling, and count-matrix assembly | Bash, R | 2024-02 |

## Where the reads come from

These repos start from FASTQ or BAM and assume demultiplexing and QC already
happened. That is the job of the [platform toolkits](./sequencing-platforms.md) — run
those first.

## Related

- Assembly QC and long-read transcript work sits mostly in internal repos.
- Older transcript-analysis reporting → [Legacy & reference](./legacy.md)
