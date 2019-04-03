### Running the repast-hpc using the docker file eze1981/repast-hpc

### Changing the env file to complete Demo_00
When using the eze1981/repast-hpc docker file, ```/project/SRC/work/env``` needs to be changed like the below:
* The names of boost library need to be matched, so '-s' should be deleted from the BOOST_LIBS entries
* The name of repast library need to be matched, REPAST_HPC_LIB was set to lrepast_hpc-2.2.0.
* It is recommended that the library files are statically linked (i.e., using libXXX.a files instead of libXXX.so files). To do so, -static flag was added in the REPAST_HPC_LIB field. 
* After these changes, Demo_00_Step_01 was successful: https://repast.github.io/hpc_tutorial/RepastHPC_Demo_00_Step_01.html
  * Compiling Demo00.exe: ```make RepastHPC_Demo_00```
  * Running the single Demo00.exe: ```./Demo_00.exe```
  * Running four instances of Demo00.exe: ```/usr/local/bin/mpirun -n 4 ./Demo_00.exe```
* The REPAST_HPC_INCLUDE should be set to ```/root/sfw/repast_hpc-2.2.0/include/``` to run https://repast.github.io/hpc_tutorial/RepastHPC_Demo_00_Step_05.html --> The compile was successful with a few warnings.
  

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
REPAST_HPC_LIB=-static -lrepast_hpc-2.2.0
```


