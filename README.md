# Repast-HPC

Docker image for [Repast-HPC](https://repast.github.io/repast_hpc.html) based on Alpine Linux.

# Usage

To download updated images:

```docker pull eze1981/repast-hpc```

To run repast-hpc mapping your current directory into the container:

```docker run --rm -it -v $(pwd):/project repast-hpc```

# Build 

To build the image from this Dockerfile

```docker build --squash -t repast-hpc .```


