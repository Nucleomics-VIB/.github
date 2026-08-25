# ⚙️ Core operations

The unglamorous code that keeps a sequencing facility running: moving terabytes
around, keeping servers tidy, and automating the chores nobody wants to do twice.

| Repo | What it does | Language | Last active |
|---|---|---|---|
| [admin-tools](https://github.com/Nucleomics-VIB/admin-tools) ⭐4 | Sysadmin tasks made easier — server housekeeping, reference-data and index management, tool installation helpers, FileSender command-line transfers, and wrappers around `samtools`, `picard`, and GATK setup | Bash, Python, R | 2026-07 |
| [NC_cloud-dl](https://github.com/Nucleomics-VIB/NC_cloud-dl) | Manage sequencing data on Nextcloud from the command line: scripted upload, download, and share-link handling for delivering results to researchers | Bash | 2024-07 |

## Why this family is small in public

Most operations code is network-specific and lives in private repos: SLURM cluster
configuration, authentication for internal web tools, mail relaying, and the
deployment plumbing behind our Dockerised services. What is public here is the part
that transfers to any facility.

## Related

- Its predecessor `cloud-dl`, superseded by `NC_cloud-dl` → [Legacy & reference](./legacy.md)
