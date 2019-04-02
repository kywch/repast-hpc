# Running the repast-hpc using the docker file eze1981/repast-hpc

# Changing the env file
Do successfully run https://repast.github.io/hpc_tutorial/RepastHPC_Demo_00_Step_01.html

When using the eze1981/repast-hpc docker file, ```/project/SRC/work/env``` needs to be changed like the below:

```
#*******************************
#
# Repast HPC Tutorial
# ENVIRONMENT DEFINITIONS
#
#*******************************

MPICXX=/usr/local/bin/mpicxx -std=c++11

BOOST_INCLUDE=-I/root/sfw/Boost/Boost_1.61/include/
BOOST_LIB_DIR=-L/root/sfw/Boost/Boost_1.61/lib/
BOOST_LIBS=-lboost_mpi-mt-s -lboost_serialization-mt-s -lboost_system-mt-s -lboost_filesystem-mt-s

REPAST_HPC_INCLUDE=-I/root/sfw/repast_hpc-2.2.0/
REPAST_HPC_LIB_DIR=-L/root/sfw/repast_hpc-2.2.0/lib
REPAST_HPC_LIB=-lrepast_hpc_gcc
```


