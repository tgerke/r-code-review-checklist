---
name: Code review template
about: This template provides a checklist for code review of data wrangling/analysis
  projects in R
title: "[REVIEW]"
labels: review
assignees: ''

---

R code review checklist
===

Summary
---

This checklist is designed to serve as an [issue template](https://docs.github.com/en/communities/using-templates-to-encourage-useful-issues-and-pull-requests/configuring-issue-templates-for-your-repository) to assist in the code review process for data wrangling/analysis projects developed in R. The focus of the checklist _is not_ R package development and review; rather, it is aimed at teams of data scientists and/or data analysts who write scripts to generate tables, listings, figures, or any other analytic output.

The checklist follows principles set forth in [the tidyverse style guide](https://style.tidyverse.org/) + [Good enough practices in scientific computing](https://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1005510), and adheres to deodorizing strategies from [Code smells and feels](https://github.com/jennybc/code-smells-and-feels).

General
---

- [ ] The code is readable / easy to understand
- [ ] The project executes / produces the intended deliverable on an independent machine (i.e. not the developer's computer) using only the code and resources embedded in the repository
- [ ] All code is necessary; e.g. functions are not written which accomplish tasks already covered by other approved code bases
- [ ] Run-time is not prohibitively long / is appropriate given the nature of the project

Documentation and organization
---

- [ ] The repository contains a `readme` which includes, at minimum, the purpose of the project (e.g. deliverables) and a set of instructions for executing the project from the code in the repository
- [ ] File names succinctly describe the purpose of the file
- [ ] File names do not contain special characters other than `-` or `_`, ideally with `-` used to separate words and `_` used to separate categories
- [ ] Files that are to be run sequentially are prefixed with numbers, and single digits are padded with leading `0`s
- [ ] Within files, logically separated chunks of code are divided by commented lines of `-` and/or `=` with a chunk descriptor
- [ ] Comments within chunks begin with `#` and a single space, and are in sentence case ending in `.` only when they contain at least 2 sentences
- [ ] All package dependencies required for a given script are loaded at the beginning of the file
- [ ] Programs are appropriately decomposed into files/functions; ideally, each file is no more than 1 page long (approximately 60 lines)

Data management
---

- [ ] External locations of raw data (if the data are too large or are not permitted to be stored directly in the repository) are clearly annotated with written verification that the locations and raw data will not be modified
- [ ] All steps used to process data are clearly identifiable (e.g. through good file naming and organization) and reproducible
- [ ] Data are not hard-coded/manually written into any script
- [ ] Appropriate policy for data storage and access, particularly PHI, is followed

Syntax
---

- [ ] Variable and function names use only lowercase letters, numbers, and `_` (to separate words within a name)
- [ ] Variable names are nouns and function names are verbs
- [ ] Commas always have a space after, and not before
- [ ] A space is used before and after `()` with `if`, `for`, or `while` (and no spaces appear on either side of `(` or `)` with regular function calls)
- [ ] Infix operators `==`, `+`, `-`, `<-`, and `=` are surrounded by spaces
- [ ] `{` and `}` are the last and first characters on lines and nested contents are indented by two spaces
- [ ] The first `%>%` in a series is followed by a new line which is indented two spaces
- [ ] Styling for `+` in ggplot layers follows the styling format of `%>%`
- [ ] Code is limited to 80 characters per line, and multiple commands are not combined into one line with `;`
- [ ] If arguments to a function don't all fit on one line, each argument is on its own indented line
- [ ] Assignment is made with `<-` not `=`
- [ ] Text is quoted with `"` not `'`, unless text already contains `"`
- [ ] `TRUE` and `FALSE` are used, not `T` and `F`

Change control
---

- [ ] Iterative development in the project is annotated through descriptive commits
- [ ] Major, minor, and patch modifications to the project are captured in release notes with corresponding release numbering (`major.minor.patch`)

Pitfalls
---

- [ ] No redundant code blocks or comments
- [ ] Extraneous data are not stored in the repository or loaded in the project
- [ ] No assignment in function calls
- [ ] `else` is used sparingly, if at all (i.e. for readability, it is avoided in favor of `if` with a guard clause or `case_when` when the logic is needed in a `mutate`)
- [ ] No instances of `attach()` or `setwd()`
- [ ] No reliance on a system-specific startup file, such as `.Rprofile`
- [ ] No use of magrittr shortcuts `%<>%` and omission of `()` on functions that don’t have arguments
