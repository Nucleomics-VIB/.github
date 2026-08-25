# 🧪 Sequencing platform toolkits

Every sequencing platform arrives with its own file formats, barcode schemes, and
run-metadata quirks. These repos absorb that: they are toolboxes of small,
independent scripts you call one at a time, not pipelines you run end to end.

If you are new to a platform, start here before reaching for an assay pipeline.

| Repo | What it gives you | Language | Last active |
|---|---|---|---|
| [pacbio-tools](https://github.com/Nucleomics-VIB/pacbio-tools) ⭐8 | The largest instrument-specific toolbox we have, ~70 scripts: Sequel/Revio run parsing, HiFi read QC, subread and CCS statistics, barcode and adapter inspection, SMRT Link report extraction | Bash, R | 2026-06 |
| [ngs-tools](https://github.com/Nucleomics-VIB/ngs-tools) ⭐3 | Platform-agnostic wrappers and parsers used across every project — FASTQ/BAM manipulation, coverage summaries, annotation and format conversion. ~90 scripts; the most-reused repo we have | Bash, Python, R | 2026-03 |
| [aviti-tools](https://github.com/Nucleomics-VIB/aviti-tools) ⭐1 | Element Biosciences AVITI support: run-folder parsing, per-flowcell QC, index and demultiplexing checks, plus small Shiny views over run metrics | Bash, Python, R | 2026-07 |
| [nanopore-tools](https://github.com/Nucleomics-VIB/nanopore-tools) ⭐4 | Oxford Nanopore (MinION / PromethION) processing: basecall summary parsing, read-length and quality QC, alignment helpers, and reporting. Companion notes live in [nanopore-tools_wiki](https://github.com/Nucleomics-VIB/nanopore-tools_wiki) | Bash, R | 2024-01 |

## How to use these

Each script is standalone and self-documenting — run it with `-h` for usage. Nothing
here needs installing beyond the tool it wraps (`samtools`, `minimap2`, `seqkit`, …);
where a conda environment helps, the repo says so in its README.

## Related

- Platform-specific *pipelines* rather than tools → [Amplicon & metabarcoding](./amplicon-metabarcoding.md) and [Genomes & variants](./genomes-variants.md)
- Older platforms we no longer sequence on (BioNano, MGI) → [Legacy & reference](./legacy.md)
