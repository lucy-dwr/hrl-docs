# Healthy Rivers and Landscapes Documentation Website

The [Healthy Rivers and Landscapes program](https://resources.ca.gov/Initiatives/Voluntary-Agreements-Page) (HRL) is an eight-year interagency effort to restore aquatic habitat, provide environmental flows, and adaptively manage ecosystems in the Sacramento River watershed and the Bay-Delta estuary. HRL aims to support California's native fish populations and is proposed as part of the program of implementation for the State Water Resource Control Board's Bay-Delta Water Quality Control Plan.

HRL implementation and adaptive management is guided by a comprehensive [Science Program](https://resources.ca.gov/Initiatives/Voluntary-Agreements-Page/Science) that facilitates research into the impacts of integrated environmental flows provision and habitat restoration from upper Sacramento River tributary watersheds to the Bay-Delta estuary. The HRL Science Program is governed by a [Science Committee](https://resources.ca.gov/-/media/CNRA-Website/Files/Initiatives/Support-Healthy-Rivers-and-Landscape/VASciProgramDraftCharter.pdf) composed of representatives from HRL signatory entities and other technical experts.

For more information, visit:

-   [HRL program website](https://resources.ca.gov/Initiatives/Voluntary-Agreements-Page)
-   [HRL science website](https://resources.ca.gov/Initiatives/Voluntary-Agreements-Page/Science)

## HRL Documentation Website

This repository contains code to render an overarching HRL science documentation website. The website is currently geared toward the data engineering and data science components of the HRL science program. Eventually, keystone HRL science documents, [such as the HRL science plan](https://resources.ca.gov/-/media/CNRA-Website/Files/Initiatives/Voluntary-Watershed-Agreements/Draft_VA_Science_Plan.pdf), will also be provided as interactive web documents.

The HRL science documentation website contains information about:

-   Data governance and management
-   Core data science and data engineering commitments and standards
-   Links to HRL program-wide templates and resources
-   High-level workflows for data engineering and data science tasks
-   Onboarding and learning materials
-   Links to other HRL program resources

### Technical Details

This website is built using Quarto, a scientific and technical publishing system built on Pandoc. The website is rendered using GitHub Pages. We welcome suggestions for how this documentation website can be improved. Visit our [contributing guidelines](.github/CONTRIBUTING.md) for more information on improving the HRL documentation website, and please note that contributors are expected to follow our [code of conduct](.github/CODE_OF_CONDUCT.md).

#### Rendering, Freezing, and Dependencies

- Quarto execution freezing is enabled globally (`execute.freeze: auto` in `_quarto.yml`). On render, Quarto saves cached computations for executable documents in the `_freeze/` directory. Commit those cached outputs whenever you update rendered content so GitHub Actions can publish without re-running code.
- When you edit a `.qmd` file with executable code, re-run `quarto render` locally to refresh its `_freeze` artifacts. Quarto automatically re-executes any page whose source changed; untouched pages keep their cached results.
- If you need to force a rebuild of everything (for example, after updating packages), delete `_freeze/` or run `quarto render --no-cache` before committing.
- R dependencies are managed with [`renv`](https://rstudio.github.io/renv/). After cloning the repo, run `renv::restore()` from R to install the packages pinned in `renv.lock`. When you add or update packages, use `renv::install()` / `renv::snapshot()` so the lockfile stays in sync. GitHub Actions automatically restores the `renv` environment before rendering.

With this workflow, everyday commits render locally with frozen outputs, and GitHub Actions simply republishes the already-computed site while remaining ready for future, more rigorous dependency management.
