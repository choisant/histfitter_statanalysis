# HistFitter

[![stable-release-python2](https://img.shields.io/badge/StablePython2-v0.66.0-green)](https://gitlab.cern.ch/HistFitter/HistFitter/-/releases/v0.66.0)
[![stable-release-python3](https://img.shields.io/badge/StablePython3-v1.0.1-green)](https://gitlab.cern.ch/HistFitter/HistFitter/-/tree/v1.0.1)
[![Documentation](https://img.shields.io/badge/Documentation-blue)](https://twiki.cern.ch/twiki/bin/viewauth/AtlasProtected/SusyFitter)
[![Tutorial](https://img.shields.io/badge/Tutorial-orange)](https://twiki.cern.ch/twiki/bin/viewauth/AtlasProtected/HistFitterTutorial)

[![pre-commit.ci status](https://results.pre-commit.ci/badge/github/histfitter/histfitter/master.svg)](https://results.pre-commit.ci/latest/github/histfitter/histfitter/master)

## Contact

The HistFitter Group mailing-list, for **any** of your questions: <atlas-phys-susy-histfitter@cern.ch>

## Acquire
HistFitter has 2 stable versions, one complient with Python2 (v0.66.0) and one with Python3 (v1.x.y).
If you're going to be using HistFitter directly as a standalone application, clone the latest stable release.  The Python2 version is no longer being updated.

```
git clone https://github.com/histfitter/histfitter
git checkout vX.XX.X -b vX.XX.X
```

If you're using HistFitter as a submodule in a project, specify the latest stable release while adding the submodule

```
# Relative path gives nicer clones in CI if parent project on CERN's GitLab
git submodule add ../../HistFitter/HistFitter.git
cd HistFitter && git checkout vX.XX.X -b vX.XX.X && cd ..
git add HistFitter && git commit -m "Add HistFitter submodule"
```


### Recommended Root version

Recommended Root version is 6.26.08.  This version of HistFitter is not compatible with ROOT versions < 6.26.

## Setup

The environment can be set by activating the setup script in the root folder

```
source setup.sh
```


## Build
From the root folder do
```
cd src
make
cd ..
```
or with cmake:
```
cmake -S . -B lib -DCMAKE_BUILD_TYPE=Release
cmake --build lib --clean-first --parallel 8
```

## Directory structure

- `analysis`: Contains all files related to an analysis. E.g. `ZeroLepton/`
- `config`: Contains HistFactory schema
- `data`: Contains data text files, provided externally, used to create workspaces for analysis
- `doc`: Documentation
- `examples`: Example scripts that use the libraries in `python/`
- `lib`: Location shared library
- `macros`: Macros for making plots, testing the fit, ongoing work, etc
- `python`: Python base classes
- `results`: Where root files with workspaces generated by HistFactory get stored
- `scripts`: Scripts for making workspaces based on text files in data/ . Scripts for submitting batch jobs.
- `src`: Source code to make workspaces, do toys.
- `test`: pytest tests

## Contributing

To contribute to development please first fork HistFitter and do all of your development on a feature branch that is **not** `master`.
If you are planning on making feature changes please first [open up an Issue](https://github.com/histfitter/histfitter/issues) and outline your plans so that development can be discusses with the maintainer team, streamlining the process as your MR is written.

When you make a MR, include a summary in the body of the MR of your changes that can be easily found and incorporated into Changelog for the next release.
