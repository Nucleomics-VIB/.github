# 📊 Visualization & reporting

Analysis code and figure code are kept apart on purpose. A pipeline should emit
tables; something else should turn tables into pictures. That separation is why we
can regenerate a figure for a paper three years after the run.

| Repo | What it gives you | Language | Last active |
|---|---|---|---|
| [plotting-tools](https://github.com/Nucleomics-VIB/plotting-tools) | Shareable plotting code produced at the Core on request or to support data re-analysis. Publication-quality `ggplot2` output with sensible defaults already applied | R | 2025-04 |
| [Shiny-apps](https://github.com/Nucleomics-VIB/Shiny-apps) ⭐1 | Interactive R/Shiny applications for exploring result tables — the version we hand to a researcher when a static PDF is not enough | R | 2025-06 |
| [benchmarks](https://github.com/Nucleomics-VIB/benchmarks) | Head-to-head comparisons of bio-apps and workflows on real Core data, with the code and the verdict. Consult this before adopting a new tool | Bash, R | 2025-10 |

## Why benchmarks live here

A benchmark is a report with code attached, so it belongs with the reporting family
rather than with the pipelines it judges. If you are choosing between two aligners,
two classifiers, or two amplicon strategies, look here before running your own
comparison — we may have already paid that cost.

## Related

- Figures generated *inside* a pipeline stay with that pipeline; this family is for reporting that outlives a single run.
- Older single-purpose plotting utilities → [Legacy & reference](./legacy.md)
