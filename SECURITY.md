# Security policy

This is the organization-wide default for the public **Nucleomics-VIB** repositories.

## What lives here

These repositories hold sequencing analysis code: pipelines, toolboxes, and reporting
scripts. They are not internet-facing services and they hold no user accounts. The
realistic risks are therefore narrow but real:

- A script that expands untrusted input into a shell command or an `eval`.
- A container image or conda recipe pinning a dependency with a known vulnerability.
- A credential, token, internal hostname, or private path committed by mistake.

All three are worth reporting.

## Reporting

**Do not open a public issue for a credential leak or an exploitable command injection.**

- Where GitHub's **private vulnerability reporting** is enabled on the repository, use it:
  the *Security* tab → *Report a vulnerability*. It stays private to the maintainers.
- Otherwise, contact the VIB Nucleomics Core through
  <https://nucleomicscore.sites.vib.be/en> and say that the message concerns a security
  issue in a GitHub repository, naming the repository.

For anything non-sensitive — a flagged dependency, a hardened default you would like to
see — a normal public issue in the repository concerned is the faster route.

## What to expect

We are a sequencing facility, not a software vendor: there is no on-call rotation and no
guaranteed response window. In practice a report is read within a few working days. If a
credential is exposed we revoke first and rewrite history afterwards, so a repository may
change under you.

## Supported versions

Only the default branch of each repository is maintained. Repositories listed under
**Legacy & reference** on the [organization page](https://github.com/Nucleomics-VIB) are
kept for citation and reproducibility; they receive no security updates. Do not run them
against untrusted input.

---

**VIB Nucleomics Core** · <https://nucleomicscore.sites.vib.be/en>
