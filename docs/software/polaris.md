# AT-TPC Analysis at ALCF Polaris

Using the [Spyral](https://attpc.github.io/Spyral) framework on a local machine can be a
challenge. AT-TPC datasets can be several terabytes, and cost a lot of time to run even 
in a parallel environment. To overcome this limitation, AT-TPC has requested time on the
Argonne Leadership Computing Facility's (ALCF) Polaris high-performance computing environment
and successfully deployed Spyral to this system. Below are the steps necessary to run 
your analysis at ALCF.

## Get some compute hours

First and foremost, you need some compute hours from the Polaris facility. There are a
few options; if you are a memeber of the FRIB AT-TPC group, we have an allocation already
and you should reach out to Daniel Bazin for access to that allocation. If you are a
collaborator, you can request an allocation for your group from the [ALCF website](https://my.alcf.anl.gov/#/).
Either way, you will also need an account to log into the ALCF system, which again you
can create at the [ALCF site](https://my.alcf.anl.gov/#/). 

## Manage your data

With hours on an ALCF machine, the next task is to get your data from a local disk onto
the ALCF systems. ALCF systems use [Globus](https://globus.org), which is a data transfer
and management system for science. You can create a Globus account, and should check if
your institution has a license (the license allows you to access more advanced features).
You can then use Globus to transfer your data to your allocation on the ALCF systems.

### Harmonizing your data

Generally, AT-TPC's unit of compute work is a single data file in HDF5 format. We can only
parallelize up to the number of files your data is stored in i.e., if you have 5 files the
maximum amount of parallelization is 5 cores. Raw data is stored in units of what we call
"runs". Each run is typically an hour or so of data taken with the TPC. However, this is
not ideal when running in high-performance environments. A hour of data does not mean each
file contains the same amount of data, for various experimental reasons. This means that
one of your parallel work units might complete much earlier than the others, resulting in
inefficient use of resources and longer total runtimes.

To combat this, you should utilize the [harmonizer](https://github.com/ATTPC/harmonizer).
The harmonizer allows you to reformat the data files to be a uniform size in terms of bytes.
It also allows you to divide your data into more files, allowing you to perform more analysis
in parallel, and take advantage of all of the resources at your disposal.

### AT-TPC Group Users

At FRIB, we have access to a local Globus endpoint where you can store your data and
transfer to Argonne using the high-speed network. This is much faster than using a local
Globus client over say Wifi. Contact Daniel Bazin for more info on getting access to the
AT-TPC FRIB Globus account and moving your data to this endpoint.

## Spyral @ Polaris

To run Spyral at Polaris, it is recommended to use the [template](https://github.com/ATTPC/attpc_polaris_template).
This template repository has a tool for creating and running jobs at Polaris, as well as
scripts for installing Spyral and it's HPE runtime, [dragonhpc](https://pypi.org/project/dragonhpc/).
Checkout the README in the template for information on changes you need to make  to your
Spyral scripts for HPE systems.

## Visualizing results

Once your analysis has been run, you will want to do post-Spyral analysis of spectra and 
other results. These post-Spyral analyses should *not* be run on systems like Polaris. In
particular, running notebooks like [spyral_notebooks](https://github.com/ATTPC/spyral_notebooks)
is not a good idea on systems like Polaris; they will count against your allocation hours
and cost you money! You should copy your output files from Spyral from Polaris to a local
machine/workstation where you can run this downstream analysis without needing to pay for
compute hours. Again, you can use Globus to facilitate this transfer of data.
