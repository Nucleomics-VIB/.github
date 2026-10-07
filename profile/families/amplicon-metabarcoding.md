# 🦠 Amplicon & metabarcoding

Long-read amplicon sequencing is one of the Core's signature services: full-length
16S rRNA for bacterial community profiling, and full-length ITS for fungi and other
eukaryotes. Both benefit enormously from PacBio HiFi accuracy — you get
species-level resolution that short-read V3–V4 sequencing cannot reach.

These repos take you from a raw Kinnex or HiFi run to a taxonomy table you can
analyse.

| Repo | What it does | Language | Last active |
|---|---|---|---|
| [hifi-16s-workflow-nc](https://github.com/Nucleomics-VIB/hifi-16s-workflow-nc) ⭐1 | The Core's production Nextflow pipeline for full-length 16S from PacBio HiFi reads: primer trimming, denoising, ASV/OTU construction, taxonomic assignment, and a report. Start here for any 16S project | Nextflow | 2026-03 |
| [nextits-nc](https://github.com/Nucleomics-VIB/nextits-nc) | Metabarcoding of fungi and other eukaryotes using full-length ITS on PacBio. Nextflow, with Docker and Singularity profiles for HPC | Nextflow, R | 2026-05 |
| [create-fungi-rdna-database](https://github.com/Nucleomics-VIB/create-fungi-rdna-database) ⭐1 | A reproducible pipeline that builds a fungal rDNA reference database from NCBI genomes, for the taxonomic assignment of ITS reads | Shell | 2025-09 |
| [Kinnex_16S_decat_demux_bash](https://github.com/Nucleomics-VIB/Kinnex_16S_decat_demux_bash) | The step *before* analysis: takes a raw Kinnex 16S run, concatenates and deconcatenates the MAS-Seq array, demultiplexes by barcode, and emits per-sample FASTQ ready for the pipeline above | Bash | 2025-06 |

## The usual route

```
Raw Kinnex run
  └─ Kinnex_16S_decat_demux_bash   → per-sample FASTQ
       └─ hifi-16s-workflow-nc      → ASV table + taxonomy + report
            └─ plotting-tools / shiny-apps  → figures the researcher can explore
```

For ITS, `nextits-nc` handles demultiplexing itself — go straight there.

## Choosing between them

- **Bacterial 16S, PacBio HiFi** → `hifi-16s-workflow-nc`. No real alternative.
- **Fungal or mixed-eukaryote ITS** → `nextits-nc`.
- **A fungal reference database to classify against** → `create-fungi-rdna-database`.
- **Just need the reads split by sample** → `Kinnex_16S_decat_demux_bash`, stop there.
- **Wondering whether a method is worth it** → [benchmarks](https://github.com/Nucleomics-VIB/benchmarks) holds our head-to-head comparisons.

## Related

- Containerised and extended variants of these pipelines are internal.
- **Shotgun metagenomics** (whole-community, no amplicon step) is a service we run, but the pipeline is internal — ask the Core rather than looking for a public repo.
- Earlier short-read and tutorial-stage work → [Legacy & reference](./legacy.md)
