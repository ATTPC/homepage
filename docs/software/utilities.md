# Software Utilities

These are tools which are supplementary to the data acqusition and the analysis.

- [spyral_notebooks](https://github.com/ATTPC/spyral_notebooks) This is a repository 
of Jupyter notebooks that can be used to examine the Spyral analysis pipeline step by 
step. It is useful for tuning the analysis parameters.
- [attpc_polaris_template](https://github.com/ATTPC/attpc_polaris_template) This is a 
template repository for using Spyral at the [Polaris](https://www.alcf.anl.gov/polaris) 
cluster at the Argonne Leadership Computing Facility at Argonne National Laboratory.
- [spyral-utils](https://attpc.github.io/spyral-utils) spyral-utils is a Python 
package with useful tools that were originally part of Spyral, but were separated into 
their own package because they were so darn useful. Includes things like nuclear masses,
histogramming, gating, etc. The repo can be found 
[here](https://github.com/ATTPC/spyral-utils).
- [electron_correction](https://github.com/ATTPC/electron_correction) A C++ application
for calculating Garfield calculations of the electron drift corrections due to the 
electric field distortion of the Active Target Time Projection Chamber (AT-TPC). 
electron_correction is a cli application for generating correction files to be used in 
AT-TPC analysis.
- [event_toolkit](https://github.com/ATTPC/event_toolkit) This repository contains 
utilities for handling issues with raw AT-TPC data. Currently, it contains a script 
for correcting mismatched event numbers between the FRIBDAQ and GETDAQ data and 
correcting the HDF5 files in place. But more utilities will be added as need arises!
- [harmonizer](https://github.com/ATTPC/harmonizer) This is a Rust based tool to
re-organize AT-TPC run data files to make for better balanced workloads at HPC
environments like ALCF Polaris.
- [synchronizer](https://github.com/ATTPC/synchronizer) This is a Rust based tool to
fix runs where the synchronization between the GET and FRIB DAQ failed using the data
timestamps.
