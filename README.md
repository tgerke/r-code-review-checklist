R code review checklist
===

Summary
---

This checklist is designed to serve as a [pull request template](https://docs.github.com/en/communities/using-templates-to-encourage-useful-issues-and-pull-requests/creating-a-pull-request-template-for-your-repository) to assist in the code review process for data wrangling/analysis projects developed in R. The focus of the checklist _is not_ R package development and review; rather, it is aimed at teams of data scientists and/or data analysts who write scripts to generate tables, listings, figures, or any other analytic output.

The checklist follows principles set forth in [the tidyverse style guide](https://style.tidyverse.org/) + [Good enough practices in scientific computing](https://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1005510), and adheres to deodorizing strategies from [Code smells and feels](https://github.com/jennybc/code-smells-and-feels).

Documentation and organization
---

- [ ] The repository contains a `readme` which includes, at minimum, the purpose of the project (e.g. deliverables) and a set of instructions for executing the project from the code in the repository
- [ ] File names succinctly describe the purpose of the file
- [ ] File names do not contain special characters other than `-` or `_`, ideally with `-` used to separate words and `_` used to separate categories
- [ ] Files that are to be run sequentially are prefixed with numbers, and single digits are padded with leading `0`s
- [ ] Within files, logically separated chunks of code are divided by commented lines of `-` and/or `=` with a chunk descriptor
- [ ] All package dependencies required for a given script are loaded at the beginning of the file
- [ ] Programs are appropriately decomposed into files/functions; ideally, each file is no more than 1 page long (approximately 60 lines)

Data management
---

- [ ] External locations of raw data (if the data are too large or are not permitted to be stored directly in the repository) are clearly annotated with written verification that the locations and raw data will not be modified
- [ ] All steps used to process data are clearly identifiable (e.g. through good file naming and organization) and reproducible
- [ ] Data are not hard-coded/manually written into any script

Syntax
---

- [ ] Variable and function names use only lowercase letters, numbers, and `_` (to separate words within a name)
- [ ] Variable names are nouns and function names are verbs
- [ ] Commas always have a space after, and not before
- [ ] A space is used before and after `()` with `if`, `for`, or `while` (and no spaces appear on either side of `(` or `)` with regular function calls)
- [ ] Infix operators `==`, `+`, `-`, `<-`, and `=` are surrounded by spaces

Change control
---

- [ ] Iterative development in the project is annotated through descriptive commits
- [ ] Major, minor, and patch modifications to the project are captured in release notes with corresponding release numbering (`major.minor.patch`)

Pitfalls
---

- [ ] No assigmnent in function calls
- [ ] No instances of `attach()` or `setwd()`
- [ ] No reliance on a system-specific startup file, such as `.Rprofile`
