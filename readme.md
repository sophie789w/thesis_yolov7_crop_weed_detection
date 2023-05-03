
<img src="https://icaerus.eu/wp-content/uploads/2022/09/ICAERUS-logo-white.svg" align="right" />

# ICAERUS Deep Learning Github Template

A basic filestructure for a Deep Learning project using Jupyter notebooks/python.
Here an explanation of the project and purpose is given, with preferably a nice image or GIF of results.

## Repo structure
The repository is with data, documentation, images, models and notebooks.

    .
    ├── data                    # location of input data for the notebooks, or dataset configurations (large datasets can be downloaded into here, using python or shell-scripts: not part of repo)
    ├── docs                    # additional documentation or reports/howto for using and explaining models
    ├── images                  # location to store output images/plots/figures from the notebooks
    ├── models                  # location of model weights (.pt files), or other model-related variables, such as settings (.yaml files)
    ├── notebooks               # jupyter notebook location, every notebook has a distinct function with a begin, middle and end, should be standalone (or order of operations should be clear), e.g. one for training, one for testing, one for plotting etc.  
    ├── LICENSE
    ├── environment.yaml        # python environment.yaml to install all the prerequisite python packages for the notebooks and/or models to work.  
    └── README.md

## More in-detail explanations
Some more details and informations about how it works, and what is done using images and short bulleted lists.

## Running the notebooks:

There are 2 different ways to get started: 1. Anaconda on bare metal or, 2. A precompiled docker-container

### 1. Anaconda on bare metal
To run on the ddal on your own machine, Mambaforge is used as a package manager.
1.  1. Please install mambaforge on your machine, [here](https://github.com/conda-forge/miniforge#mambaforge).
    2. in the installer, make sure that desktop shortcuts are enabled
   
2. Search for the newly installed Miniforge prompt application and run it

3. Download this repository on your machine, navigate to your preferred directory and run:
```
    git pull https://github.com/users/example_repo.git
```
Or download this repository as a .zip file from the top-right green button: 'Download ZIP'
and extract to the preferred directory.

4.  1. Search for the newly installed Miniforge prompt and run it
    2. `cd` to the git directory and install the `environment.yaml` file under a new python-processing environment called `dl`
```
    mamba env create -n dl -file environment.yaml 
```
Activate the environment
```
    conda activate dl
```

5. Run the jupyterlab environment to start processing and analysing data with the different notebooks:
Run in your anaconda prompt, with the dl environment activated:
```
    jupyter-lab
```
This will start the jupyter-lab instance in your browser, and you are ready to process drone data!

### 2. Docker

Not wanting to deal with anaconda and environment.yamls? Run the ddal environment in a docker container:
1. Install [Docker](https://docs.docker.com/get-docker/)
2. Start Docker
3. Start the Jupyter-lab docker
from your command-line with docker installed and ready:
this pulls the most recent ddal with all packages and libraries installed.
```
    docker run --rm -it -p 8888:8888 --shm-size=5gb -v /directory/to/this/repo/on/local/machine:/home/jovyan docker/container:tag
```
Or using GPUs: Install Docker with [NVIDIA](https://github.com/NVIDIA/nvidia-docker) runtime and run a gpu-enabled docker container:
```
    docker run --rm -it --runtime=nvidia -p 8888:8888 --gpus 1 --shm-size=5gb -v /directory/to/this/repo/on/local/machine:/home/jovyan docker/container:tag
```
