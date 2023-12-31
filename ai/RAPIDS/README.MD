# RAPIDS_Bootcamp

## GPU Bootcamp for RAPIDS AI

This repository contains mini applications for GPU Bootcamps. This repository consists of GPU Bootcamp material for RAPIDS AI. The RAPIDS suite of open source software libraries gives you the freedom to execute end-to-end data science and analytics pipelines entirely on GPUs. In this series you can access RAPIDS learning resources in the form of labs. The modules covered in this Bootcamp are CuDF, CuML, Dask and Challenge.

- Introduction to RAPIDS
- Lab 1: Using RAPIDS CuDF
- Lab 2: Using RAPIDS CuML
- Lab 3: Using RAPIDS Dask ( Multi-GPU )
- Mini-challenge: Gene Expression Classification/Bike Rental Prediction


## Tutorial Duration

The overall Bootcamp should take approximate 3.5 hours. There is an additional mini-challenge provided at the end of Bootcamp.  

## Prerequisites
To run this tutorial you will need a machine with NVIDIA GPU.

- Install the latest [Docker](https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/install-guide.html#docker) or [Singularity](https://sylabs.io/docs/).

- The base containers required for the Bootcamp may require users to create a NGC account and generate an API key (https://docs.nvidia.com/ngc/ngc-catalog-user-guide/index.html#registering-activating-ngc-account)

## Creating containers
To start with, you will have to build a Docker or Singularity container.

### Docker Container
To build a docker container, run:
`sudo docker build --network=host -t <imagename>:<tagnumber> .`

For instance:
`sudo docker build -t myimage:1.0 .`

and to run the container, run:
`sudo docker run --rm -it --gpus=all --network=host -p 8888:8888 myimage:1.0`

Then, open the jupyter lab in browser: http://localhost:8888
Start working on the lab by clicking on the `Start_Here.ipynb` notebook.

### Singularity Container

To build the singularity container, run: 
`sudo singularity build --sandbox <image_name>.simg Singularity`

and copy the files to your local machine to make sure changes are stored locally:
`singularity run --writable <image_name>.simg cp -rT /workspace ~/workspace`

Then, run the container:
`singularity run --nv --writable <image_name>.simg /opt/conda/envs/rapids/bin/jupyter lab --no-browser --allow-root --ip=0.0.0.0 --port=8888 --NotebookApp.token="" --notebook-dir=/workspace/jupyter_notebook`

Then, open the jupyter lab in browser: http://localhost:8888
Start working on the lab by clicking on the `Start_Here.ipynb` notebook.

## Troubleshooting

Q. Cannot write to /tmp directory

A. Some notebooks depend on writing logs to /tmp directory. While creating container make sure /tmp director is accesible with write permission to container. Else the user can also change the tmp directory location

Q. Out of memory Error

A. The bootcamp is designed considering a GPU with minimum 16 GB memory. The users can reduce the overall size of the array sizes to reduce the overall memory footprint if required based on GPU card RAM .

## For more information about RAPIDS applications and Docker, please refer to <a href="https://hub.docker.com/r/rapidsai/rapidsai/"> here</a>

## Known issues
- Please go through the list of exisiting bugs/issues or file a new issue at [Github](https://github.com/gpuhackathons-org/gpubootcamp/issues).