# R-Docker-Jupyter-Guide
 Guide for starting and using R with Docker and Jupyter

# Install Docker

## For Windows

1. Download Docker Desktop from [Docker's official website](https://www.docker.com/products/docker-desktop/).

2. Run the installer.

4. You can verify Docker is installed by opening terminal/command and using:

```
docker --version
```

## For macOS:

1. Download Docker Desktop (see link above).

2. Drag Docker to your Applications folder. 

3. Launch Docker from the applications folder. 

4. You can verify Docker is installed by opening terminal and running the version command:

```
docker --version
```

# Install Python and Jupyter

## Install Python:

1. [Download Python](https://www.python.org/downloads/)

2. Run the installer and ensure you add Python to PATH before installing. 

3. Again you can verify Python is installed using terminal 

```
python --version
```

## Install Jupyter

1. You can install Jupyter Notebook or Jupyter Lab using `pip` in terminal:

```
pip install notebook
```

or

```
pip install jupyterlab
```

2. Again, verify installation:

```
jupyter --version
```

**Note**: If you are using Anaconda for Python, you will need to use the Anaconda prompt to check versions of your Jupyter Notebook/Lab installation.

## Set up R an R Kernel

1. Install the `IRkernel` package :

```{r}
devtools::install_github("IRkernel/IRkernel")
IRkernel::installspec(user = FALSE)
```

This should make the R kernel available to Jupyter Notebook. 

You can check to verify by navigating to a new jupyter notebook and see if you can switch from a Python kernel to an R kernel.

To do this simply run the following in terminal (or Anaconda prompt if needed):

```
jupyter notebook 
```

Navigate to a new note book. In the upper right side of the window you should be able to change the kernel to R.

## Create a Dockerized Environment for Jupyter Notebooks for R

1. Write your Dockerfile (or edit a previous file).

You can view a **Dockerfile** is a file that contains a set of instructions used to create a Docker image. It sets up the environment and includes the necessary dependencies of that environment based on what you include in the file. Once established you can run your desired application in the Docker container.

A Dockerfile that clones and installs the `matilda` R package from GitHub looks like this:

```
# Use the official Jupyter R notebook image as the base image
FROM jupyter/r-notebook:2022-05-03

# Switch to the root user to install system packages
USER root

# Clone the matilda repository from GitHub
RUN git clone --branch main https://github.com/JGCRI/matilda.git /home/jovyan/matilda 

# Install the matilda R package
RUN R -e 'library("devtools"); devtools::install("/home/jovyan/matilda")'

```

In this Dockerfile you can make many changes including adding more packages and dependencies or changing the specific branch of a repo you are cloning from Github. 

The Dockerfile should be saved as `Dockerfile` with no extension in a directory of the users choice. You will need to open terminal from this directory when you are ready to build and run the docker container.



