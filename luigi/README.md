
# Background

Home page is https://luigi.readthedocs.io

# Setup

```
source conda-install/etc/profile.d/conda.sh
conda create -n luigi -c conda-forge luigi
conda activate luigi
```

## Specific to this pipeline

* need to add CASA at the end of PATH
* conda install -c conda-forge python-casacore matplotlib
* apt-get install texlive-latex-base texlive-fonts-recommended texlive-fonts-extra texlive-latex-extra

# How it works

You need to write a pipeline.py and run it with:

```
PYTHONPATH='.' luigi --module pipeline LatexReport --local-scheduler
```

where `LatexReport` is one of the `Tasks` defined in pipeline.py.

Relevant comments from the docs:

* Note that unlike Makefile, the output will not be recreated when any of the input files is modified. You need to delete the output file manually.

* Make sure your Task.run method is idempotent.


# Evaluation (1:bad, 5:good)

## Installation

Score: 5
Comments: There is a conda-forge package!

## Documentation

Score: 5
Comments: Great! Including examples to get started and diving deep into what's required to use it.

## Management of software dependencies

Score: 3
Comments: By default, no easy integration is provided neither with Conda packages nor containers. However, luigi is built to be extended and people contribute their plugins: https://luigi.readthedocs.io/en/stable/api/luigi.contrib.html (e.g. there is a Docker plugin)

## Visualize workflows

Score: 5
Comments: It comes with built-in functionality to plot the workflow to be executed.

## Interoperability

Score: 0
Comments: It doesn't seem to provide integration with CWL.

## HPC support

Score: 3
Comments: By default, no easy integration is provided through DRMAA. However, luigi is built to be extended and people contribute their plugins: https://luigi.readthedocs.io/en/stable/api/luigi.contrib.html (e.g. there is a SGE plugin)


## Cloud support

Score: 3
Comments: By default, no easy integration is provided with Kubernetes. However, luigi is built to be extended and people contribute their plugins: https://luigi.readthedocs.io/en/stable/api/luigi.contrib.html (e.g. there is Kubernetes plugin)

