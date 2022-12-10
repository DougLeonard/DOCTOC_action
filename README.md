# DOCTOC_action

An auto table of contents generator action for github wikis and repos.

It just runs ```doctoc .``` to autogenerate tables of contents for all .md files in the repo, ignoring files starting with  \<!--DOCTOC SKIP-->.  Presently no other filters or controls exist. 

The other action I found seemingly using DOCTOC failed to recognize \<!--DOCTOC SKIP--> (maybe fixed now), and one using an alternative engine produced broken TOC's in some cases.  Anyway, this is a very simple and transparent implementation directly using thlorenz/doctoc with all two commands (install and excute) directly in the action.yml file.

## Usage:
This can be used simply by committing the following to .github/workflows/toc.yml and pushing to github:  
```
on: push
name: DSL TOC Action

jobs:
  doDOCTOC:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - name: "Call DOCTOC_action"
        uses: DougLeonard/DOCTOC_action@v1      

```

