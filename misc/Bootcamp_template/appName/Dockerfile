# Copyright (c) 2021 NVIDIA Corporation.  All rights reserved.

# To run this dockerfile you need to present port 8888 and provide a hostname. 
# For instance:
#   $ nvidia-docker run --rm -it -p "8888:8888" -e HOSTNAME=foo.example.com openacc-labs:latest
FROM nvcr.io/nvidia/nvhpc:21.3-devel-cuda_multi-ubuntu20.04

RUN apt update && \
    apt install -y --no-install-recommends python3-pip 

ADD appName_labs/ /labs
WORKDIR /labs
