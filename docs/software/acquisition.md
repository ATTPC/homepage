# Data Acquisition Software and Friends

The AT-TPC runs a hybrid GETDAQ/FRIBDAQ data acquisition. GETDAQ controls the GET 
electronics chain (MuTaNT/CoBo/AsAd/AGET), while the FRIBDAQ system controls the many 
auxiliary detectors acqusition, as well as maintains active scalars. 

Here we provide some brief descriptions and links to the data acquisition software 
frameworks/libraries for AT-TPC, as well as related tools.

- GETDAQ: The data acquisition library and applications used with the General 
Electronics for TPCs (GET). GETDAQ is used to control the MuTaNT/CoBo/AsAd/AGET 
electronics, as well as readout data from the electronics. GETDAQ was developed by the 
GET collaboration.
- [FRIBDAQ/NSCLDAQ](https://github.com/FRIBDAQ): The data acquisition library used for 
auxiliary detectors in the AT-TPC scheme. FRIBDAQ is a general use data acquisition 
library that supports many different module types. FRIBDAQ/NSCLDAQ is developed by the 
FRIB Data Acquisition Group.
- [attpc_envoy](https://attpc.github.io/attpc_envoy): A Rust-based interface for the 
GETDAQ system. GETDAQ provides the server/client infrastructure for controlling the 
GET electronics, but doesn't provide a complete interface for those controls. 
attpc_envoy is an [eframe/egui](https://github.com/emilk/egui) GUI with an 
asynchronous backend which monitors and manipulates the state of all of the 
independent GETDAQ systems. The repository for attpc_envoy can be found 
[here](https://github.com/ATTPC/attpc_envoy). attpc_envoy is actively developed and 
used by the AT-TPC Group and collaborators.
- [attpc_merger](https://attpc.github.io/attpc_merger): A Rust-based event building 
software for AT-TPC data. The various data acquisition components of the AT-TPC 
generate many separate data files of incompatible formats with chunks of data from 
different detector components. attpc_merger takes these data files and merges the data 
into a unified (time-based) event structure. attpc_merger serves as a conversion step, 
preparing data for analysis by tools like Spyral and ATTPCROOT. The repository for 
attpc_merger can be found [here](https://github.com/ATTPC/attpc_merger). attpc_merger 
is actively developed and used by the AT-TPC Group and collaborators.
