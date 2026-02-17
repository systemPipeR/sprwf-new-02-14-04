## Generic Workflow Template for systemPipeR WMS

<p align="right">
  <a href="https://systempipe.org/sprwf-new/new.html">
    <img src="https://img.shields.io/badge/TUTORIAL-blue?style=for-the-badge&logo=gitbook&logoColor=white" alt="Tutorial Badge">
  </a>
</p>

__Overview__

This is a versioned workflow template for conducting data analyses
with the [systemPipeR Workflow Management
System](https://systempipe.org/about/project/) (WMS). It ensures consistency
through centrally maintained [param]() and [data]() packs, which are defined in
`manifest.yml` and downloaded and installed during the setup process.

Detailed information about this specific `sprwf-new` workflow is available 
[here](https://systempipe.org/sprwf-new/new.html).

> Note: The data pack includes sample data useful for testing certain workflows. Users who do not require this sample data can skip the download step under the getData_gh section below. 

__Documentation__

To design, set up, and run workflows using systemPipeR, please consult:
  + [systemPipeR Manual](https://bioconductor.org/packages/devel/bioc/html/systemPipeR.html)
  + [systemPipeRdata Manual](https://www.bioconductor.org/packages/devel/data/experiment/html/systemPipeRdata.html)

👉 A complete list of workflow templates and project information is available at [systempipe.org](https://systempipe.org/about/project/).


__Quick Start (Recommended)__

The following will:

  + Clone the workflow using `gert` internally, which eliminates the need to install the Git CLI
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

Version dependencies defined in `manifest.yml`:

| Field                    | Value            |
| ------------------------ | ---------------- |
| Workflow name            | `sprwf-new`      |
| Version                  | `wf-1.1.1`       |
| Required systemPipeR     | `>= 2.17.1`      |
| Required systemPipeRdata | `>= 2.15.4`      |
| Parameter repository     | `sprwfcmp-param` |
| Data repository          | `sprwfcmp-data`  |


The version enforcement (not recommended) can be overwritten via the `force_min_version` argument:

```
genWorkenvir_gh(..., force_min_version = TRUE)
```

For more information, consult the help pages: `?genWorkenvir_gh`, `?getParam_gh`, and `?getData_gh`.

__Advanced Setup Options__

The URLs of the `param` and `data` repos can be provided under the corresponding `*_repos` arguments. 

```
getParam_gh(param_repo = "https://github.com/systemPipeR/sprwfcmp-param")
getData_gh(data_repo  = "https://github.com/systemPipeR/sprwfcmp-data")
```

__Command-line Option__

Alternatively, the workflow repos can be cloned with the standard `git clone`
command. This requires the install of the Git CLI. The `<download_link>` is
located under the green "Code" button on the top right of the repository, with
the HTTPS option generally being the most straightforward for most users.
Downloading the repos a zip file is another option.

From the command-line:

```
git clone <download_link>
```

After this the `param` and `data` directories need to be populated as shown above, or 
manually by copying the corresponding directories of the `sprwfcmp-param` and `sprwfcmp-data` 
repos into the workflow repository.  

