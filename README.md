## Generic Workflow Template for systemPipeR WMS

![R](https://img.shields.io/badge/R-%3E%3D4.2-blue)
![Bioconductor](https://img.shields.io/badge/Bioc-release-green)
![Workflow Version](https://img.shields.io/badge/workflow-wf--1.1.1-orange)
<p align="right">
  <a href="https://systempipe.org/sprwf-new/new.html">
    <img src="https://img.shields.io/badge/TUTORIAL-blue?style=for-the-badge&logo=gitbook&logoColor=white" alt="Tutorial Badge">
  </a>
</p>

This is a lightweight, versioned workflow template for conducting data analyses
with the [systemPipeR Workflow Management
System](https://systempipe.org/about/project/) (WMS). It ensures consistency
through centrally maintained parameter and data packs, which are defined in
`manifest.yml` and downloaded and installed during the setup process.

Detailed information about this specific `sprwf-new` workflow is available 
[here](https://systempipe.org/sprwf-new/new.html).

__Documentation__

To design, set up, and run workflows using systemPipeR, please consult:
  + [systemPipeR Manual](https://bioconductor.org/packages/devel/bioc/html/systemPipeR.html)
  + [systemPipeRdata Manual](https://www.bioconductor.org/packages/devel/data/experiment/html/systemPipeRdata.html)

A complete list of workflow templates and project information is available at [systempipe.org](https://systempipe.org/about/project/).

__Version dependencies defined in `manifest.yml`__

| Field                    | Value            |
| ------------------------ | ---------------- |
| Workflow name            | `sprwf-new`      |
| Version                  | `wf-1.1.1`       |
| Required systemPipeR     | `>= 2.17.1`      |
| Required systemPipeRdata | `>= 2.15.4`      |
| Parameter repository     | `sprwfcmp-param` |
| Data repository          | `sprwfcmp-data`  |


__Quick Start (Recommended)__

The following will:

  + Clone the workflow (no Git CLI required)
  + Enforce minimum package versions
  + Install the exact tagged param/ and data/ releases
  + Create a reproducible local workflow environment

```
library(systemPipeRdata)
genWorkenvir_gh(url = "https://github.com/systemPipeR/sprwf-new.git", mydirname = "sprwf-new")
setwd("sprwf-new")
getParam_gh()
getData_gh()
```


__Download of Workflow__

To obtain this workflow, run one of the following commands. The `<download_link>`
is located under the green "Code" button on the top right of the repository,
with the HTTPS option generally being the most straightforward for most users.

From the command-line:

```
git clone <download_link>
```

From R (no Git CLI required):

```
gert::git_clone("<download_link>")
```

Alternative R-based setup that populates the `param` and `data` directories of
the downloaded workflow environment in separate steps (no Git CLI required). 
For more information, consult the help pages: `?genWorkenvir_gh`, `?getParam_gh`, and `?getData_gh`.

```
library(systemPipeRdata) 
if (packageVersion("systemPipeRdata") < "2.14.5") { stop("systemPipeRdata >= 2.14.5 is required.", call. = FALSE) }
genWorkenvir_gh(url="https://github.com/systemPipeR/sprwf-new.git", "sprwf-new", force_min_version=FALSE)
setwd("sprwf-new)
getParam_gh(param_repo="https://github.com/systemPipeR/sprwfcmp-param.git")
getData_gh(data_repo="https://github.com/systemPipeR/sprwfcmp-data.git")
```

