## What this changes

<!-- One or two sentences. What behaviour is different after this merges? -->

## Why

<!-- Link the issue if there is one: Fixes #123 -->

## How it was tested

<!-- The command you ran and the data you ran it on. "Ran the pipeline on a Revio 16S run,
     4 samples" is enough — we mainly need to know it was executed, not just written. -->

## Checklist

- [ ] Scoped to one concern — no drive-by reformatting alongside the functional change.
- [ ] No data committed (FASTQ, BAM, references), and no credentials, tokens, internal
      hostnames, or VIB-internal paths.
- [ ] Site-specific paths stay configurable at the top of the script, not hard-coded.
- [ ] Matches the surrounding style; no new dependency unless the change needs one.
