# DOCTOC_action

An auto table of contents generator action for github wikis and repos.

This is in testing. Forced pushes, changed tags etc are possible for now. Others are warned.  

It runs DOCTOC to autogenerate table of contents for all .md files in the repo ignoring files starting with  
\<!--DOCTOC SKIP-->.  Presently no other filters exist or control exists. 

The other action I found using DOCTOC failed to recognize \<!--DOCTOC SKIP-->, and one using an alternative engine produced broken TOC's in some cases.  

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
However forking it, and changing the uses line, could be wise, in case I break things ;)  
Presently it does not use the package-lock.json file, so speed-ups are possible (maybe easy, untested).

