# Running the repast-hpc using the docker file eze1981/repast-hpc

# Changing the env file
Do successfully run https://repast.github.io/hpc_tutorial/RepastHPC_Demo_00_Step_01.html

When using the eze1981/repast-hpc docker file, ```/project/SRC/work/env``` needs to be changed like the below:
* The names of boost library need to be matched, so '-s' should be deleted from the BOOST_LIBS entries
* The name of repast library need to be matched, so librepast_hpc-2.2.0.a, librepast_hpc-2.2.0.so were symlinked to librepast_hpc.a and librepast_hpc.so, respectively
* It is recommended that the library files are statically linked (i.e., using libXXX.a files instead of libXXX.so files). To do so, -static flag was added in the REPAST_HPC_LIB field. 

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
BOOST_LIBS=-lboost_mpi-mt -lboost_serialization-mt -lboost_system-mt -lboost_filesystem-mt

REPAST_HPC_INCLUDE=-I/root/sfw/repast_hpc-2.2.0/
REPAST_HPC_LIB_DIR=-L/root/sfw/repast_hpc-2.2.0/lib/
REPAST_HPC_LIB=-static -lrepast_hpc
```


