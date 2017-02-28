# Repast-HPC

Docker image for [Repast-HPC](https://repast.github.io/repast_hpc.html) based on Alpine Linux.

# Usage

To download updated images:

```docker pull eze1981/repast-hpc```

To run repast-hpc container mapping a host directory into the container:

```docker run --rm -it -v $(pwd):/project repast-hpc```

