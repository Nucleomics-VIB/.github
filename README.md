# Nucleomics-VIB / .github

This repository holds the **organization profile page** rendered at
<https://github.com/Nucleomics-VIB>, plus org-wide GitHub configuration.

```
profile/
  README.md              ← the org landing page (this is what visitors see)
  families/
    sequencing-platforms.md
    amplicon-metabarcoding.md
    genomes-variants.md
    visualization-reporting.md
    core-operations.md
    legacy.md
```

## Maintaining the landing page

The landing page is intentionally short. It routes visitors — by the data they hold —
to a *family index*, and the family index carries the repo-by-repo detail. When
something changes, edit the family file, not the landing page.

**Editing rules that matter:**

- **Use absolute URLs.** Relative links in an org profile README do not reliably
  resolve from the org page. Every link here is a full `https://github.com/...` URL.
- **Public repos only.** This page is world-readable. Private repos are indexed in
  the internal org index (see below), never here.
- **Recency gate.** A repo drops from its family into `families/legacy.md` once it has
  had no commits for roughly three years, unless a current repo depends on it. Legacy
  entries name their successor.
- **Keep the version footer current** when the structure changes.

## Refreshing the repo inventory

The families were built from the live org listing:

```bash
gh repo list Nucleomics-VIB --limit 300 \
  --json name,description,primaryLanguage,isArchived,isPrivate,pushedAt,stargazerCount,repositoryTopics \
  > repos.json

# public, active (pushed within ~3 years)
jq -r '[.[]|select(.isPrivate==false and (.pushedAt >= "2023-08-25"))]
       | sort_by(.pushedAt) | reverse
       | .[] | "\(.pushedAt[0:7])  \(.stargazerCount)*  \(.name)"' repos.json
```

Re-run that when adding a family or auditing what has gone stale.

## Internal index

A companion index covering **all** repos, public and private, across eight families
lives in a private repo — it is the members' view of the same map. Keep the two in
step when a repo is created, renamed, or made public.

---

Created and maintained by **Stephane Plaisance** — **VIB Nucleomics Core**.
Org profile v1.0.0 · 2026-08-25
