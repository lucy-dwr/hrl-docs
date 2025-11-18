# Contributing to hrl-docs

We welcome contributions for improving the HRL documentation website. To make contributing accessible to collaborators at all stages of proficiency and career development, we are committed to teaching contributors about our development process and mentoring new contributors in open source practices.

This document outlines how to propose a change to hrl-docs. For a general discussion on contributing to open source projects, check out the [tidyverse development contributing guide](https://rstd.io/tidy-contrib) and [code review principles](https://code-review.tidyverse.org/). Eventually, the HRL program will produce our own guidance on contributing to our open source materials, but we haven't had a chance to put that together yet!

## Type of Contributions

You can contribute to HRL program documentation in two main ways:

-   Opening issues to provide feedback, stimulate discussion, and share ideas
-   Submitting pull requests to fix bugs, address open issues, add features, or improve documentation

## Fixing Typos

You can fix typos, spelling mistakes, or grammatical errors in the documentation directly using the GitHub web interface, as long as the changes are made in the source file. This generally means you'll need to edit [roxygen2 comments](https://roxygen2.r-lib.org/articles/roxygen2.html) in an `.R` file, not a `.Rd` file. You can find the `.R` file that generates the `.Rd` by reading the comment in the first line of the `.Rd` file.

## Bigger Changes

If you want to make a bigger change, it's a good idea to first file an issue and make sure someone from the core maintenance team agrees that the change is helpful. If you’ve found a bug, please file an issue that illustrates the bug with a minimal reproducible example, also called a [reprex](https://www.tidyverse.org/help/#reprex). This will also help you write a unit test, if needed. See the tidyverse guide on [how to create a great issue](https://code-review.tidyverse.org/issues/) for more advice.

### Pull Request Process

-   Fork the package and clone onto your computer. If you haven't done this before, we recommend using `usethis::create_from_github("lucy-dwr/hrl-docs", fork = TRUE)` or using command line git.

-   Install all development dependencies with `devtools::install_dev_deps()` and then make sure the package passes R CMD check by running `devtools::check()`. If R CMD check doesn't pass cleanly, it's a good idea to ask for help before continuing.

-   Create a Git branch for your pull request (PR). We recommend using `usethis::pr_init("brief-description-of-change")`, using command line git, or using the git graphical user interface of your choice.

-   Make your changes, commit to git, and then create a PR by running `usethis::pr_push()` or using your git graphical user interface of choice and following the prompts in your browser. The title of your PR should briefly describe the change. The body of your PR should contain `Fixes #issue-number`, where the issue number matches that of the issue you opened on the repository.

-   For user-facing changes, add a bullet to the top of `NEWS.md` (i.e. just below the first header) so that it's added to the changelog. Follow the style described in <https://style.tidyverse.org/news.html>.

### Code style

-   New code should follow the tidyverse [style guide](https://style.tidyverse.org) until HRL has published its own forthcoming style guide. You can use [Air](https://posit-dev.github.io/air/) to apply this style, but please don't restyle code that has nothing to do with your PR.

-   We use [roxygen2](https://cran.r-project.org/package=roxygen2) with [Markdown syntax](https://cran.r-project.org/web/packages/roxygen2/vignettes/rd-formatting.html) for documentation.

-   We use [testthat](https://cran.r-project.org/package=testthat) for unit tests. Contributions with test cases included are easier to accept.

## Code of Conduct

Please note that the hrl-docs project is released with a [Contributor Code of Conduct](CODE_OF_CONDUCT.md) to support respectful, equitable collaboration and foster a welcoming environment for learning. By contributing to this project you agree to abide by its terms.

## Getting Help

Want to contribute but don't know how or where to start? Feel free to get in touch with Lucy Andrews at [lucy.andrews\@water.ca.gov](mailto:lucy.andrews@water.ca.gov).

## Acknowledgments

This contributing guide was adapted from the [tidyverse contributing guide](https://tidyverse.tidyverse.org/CONTRIBUTING.html), generated using `usethis::use_tidy_contributing()`.