# Contributing to VIB Nucleomics Core repositories

Thanks for looking. This file is the organization-wide default: it applies to every
public **Nucleomics-VIB** repository that does not carry its own `CONTRIBUTING.md`.
Where a repository has its own, that one wins.

Start at the [organization page](https://github.com/Nucleomics-VIB) if you are not yet
sure which repository you need — it routes by the data you are holding.

## Before you open anything

**Check which kind of repository you are in.** The name tells you:

| Pattern | What it is | What to expect |
|---|---|---|
| `*-tools` | A toolbox of many small, independent scripts for one platform or domain | Scripts evolve independently; a fix to one rarely affects the others |
| `NC_*` | A Core-operated pipeline or application | Production-facing and versioned — the most likely to accept a change |
| `*_docker` / `*_nf` | A containerised or Nextflow implementation of a sibling pipeline | Fix the behaviour in the implementation you actually ran |

Repositories listed under **Legacy & reference** on the organization page are stable and
no longer actively developed. Issues there are read, but a fix may not ship.

## Reporting a problem

Open an issue in the repository the problem is in — not in this one. A report we can act
on names:

- **The repository and the exact script or pipeline** you ran.
- **The commit or release tag** (`git rev-parse --short HEAD`, or the release you cloned).
- **The command line**, verbatim, with paths anonymised if you must.
- **What happened and what you expected**, with the error text rather than a paraphrase.
- **Your data**: platform (PacBio / ONT / AVITI / MGI), read type, and roughly how much.
- **Your environment**: OS, and whether you ran natively, in conda, or in a container.

Sequencing bugs are usually data-shaped. Telling us the assay and the instrument saves a
full round trip.

## Proposing a change

1. Open an issue first for anything beyond a typo — it costs you nothing and may save you
   a rewrite. Most of this code encodes lab conventions that are not visible in the source.
2. Fork, branch from the default branch, and keep the change to one concern.
3. **Match the surrounding code.** These repositories are mostly Bash and R, written to be
   read by biologists: explicit variable names, comments over cleverness, no new framework
   or dependency unless the change is impossible without it.
4. **Do not commit data.** No FASTQ, BAM, or reference genomes — not even small ones. Do not
   commit credentials, internal hostnames, or paths inside the VIB network.
5. Say in the PR description **how you tested it**, and on what data.

## Things that are usually declined

- Reformatting or restyling a whole file alongside a functional change — split them.
- New dependencies that replace a working handful of shell lines.
- Changes that hard-code a path or reference layout specific to your own site. Make it
  configurable at the top of the script instead, the way the existing options are.

## Licence

Contributions are accepted under the repository's licence — for most of our code, the
[Creative Commons Attribution-ShareAlike 3.0](http://creativecommons.org/licenses/by-sa/3.0/)
licence. By opening a pull request you agree your contribution may be redistributed under
those terms, with attribution to **VIB Nucleomics Core** and to you.

---

Maintained by **Stephane Plaisance** — **VIB Nucleomics Core**.
<https://nucleomicscore.sites.vib.be/en>
