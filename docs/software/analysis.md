# Analysis Software

Here we provide some brief descriptions and links to the analysis software 
frameworks/libraries for AT-TPC data.

- [Spyral](https://attpc.github.io/Spyral): A Python analysis framework developed with 
performance and ease-of-use in mind. Spyral supports massively-parallel analysis and 
uses advanced techniques such as Just-In-Time compilation to achieve competitive 
performance with other frameworks on this list. Spyral is actively developed and used 
by the AT-TPC group and collaborators. The Spyral repository can be found 
[here](https://github.com/ATTPC/Spyral/) as well. Some useful Spyral tools are 
described in the [utilities section](./utilities.md).
- [ATTPCROOT](https://github.com/ATTPC/ATTPCROOTv2): ATTPCROOT is a 
[ROOT](https://root.cern/)-based framework to analyze data of active target detectors 
including the ATTPC (Active Target Time Projection Chamber) detector and the p-ATTPC 
(Prototype). The framework allows the end user to unpack and analyze the data, as well 
as perform realistic simulations based on a Virtual Monte Carlo (VMC) package. The 
framework needs external libraries (FairSoft and [FairRoot](https://fairroot.gsi.de/)) 
to be compiled and executed, which are developed by other groups and not directly 
supported by the AT-TPC Group. Documentation for ATTPCROOT can be found 
[here](https://github.com/ATTPC/ATTPCROOTv2/wiki). ATTPCROOT is actively used 
throughout the AT-TPC collaboration.
- [attpc_engine](https://attpc.github.io/attpc_engine): A Python Monte Carlo 
simulation framework developed alongside Spyral. attpc_engine allows for the 
calculation of multi-step reaction kinematics and the simulation AT-TPC detector 
effects over that kinematics sample. Engine data can then be given to Spyral to test 
the efficiency of both the detector and the analysis. The attpc_engine repository can 
be found [here](https://github.com/ATTPC/attpc_engine). attpc_engine is actively 
developed and used by the AT-TPC Group.
- [Igor-Pro](https://github.com/ATTPC/Igor-Pro): A collection of extensions for the 
[IgorPro](https://www.wavemetrics.com/) analysis package to analyze AT-TPC data.
