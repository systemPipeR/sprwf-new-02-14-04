## systemPipeRdata: Generic Workflow Template

<p align="right">
  <a href="https://systempipe.org/sprwf-new/new.html">
    <img src="https://img.shields.io/badge/TUTORIAL-blue?style=for-the-badge&logo=gitbook&logoColor=white" alt="Tutorial Badge">
  </a>
</p>


This is a workflow template of the [systemPipeR Workflow Management System](https://systempipe.org/about/project/) (WMS).
Detailed information about this specific workflow is available [here](https://systempipe.org/sprwf-new/new.html).

To learn how to design, set up, and run workflows using systemPipeR, users want to consult the official user manuals:

  + [systemPipeR Manual](https://bioconductor.org/packages/devel/bioc/html/systemPipeR.html)
  + [systemPipeRdata Manual](https://www.bioconductor.org/packages/devel/data/experiment/html/systemPipeRdata.html)

A list of all available workflow templates and additional project information
can be found on the project's dedicated website:
[systempipe.org](https://systempipe.org/about/project/).

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

