# Getting started

Project Jupyter provides a number of pre-built Docker images. These can be used directly from the command line:

```
docker run -p 8888:8888 quay.io/jupyter/base-notebook:2025-01-28
```

The `-p 8888:8888` makes sure to map the port 8888 within the container (where Jupyter is typically running)
to port 8888 on the outside of the container. `quay.io/jupyter/base-notebook` is one of several images provided
by Jupyter. All of these images are tagged with dates or hashes to be able to pin specific versions.

# Available images

For a list of available images and tags, you can check:

* The [Selecting an Image section](https://jupyter-docker-stacks.readthedocs.io/en/latest/using/selecting.html) of the documentation
* [Jupyter Quay.io page](https://quay.io/organization/jupyter)
* The [repository that provides the build recipes](https://github.com/jupyter/docker-stacks) for these images

# Switching between Jupyter Notebook and JupyterLab

All the images contain both frontends. You can switch between them using an environment variable:

```
docker run -p 8888:8888 -e JUPYTER_ENABLE_LAB=YES quay.io/jupyter/base-notebook:2025-01-28
```

If you want to hardcode this decision into your derived image, you can use the `ENV` command in the `Dockerfile`:

```
ENV JUPYTER_ENABLE_LAB=YES
```
