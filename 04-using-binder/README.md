# Using MyBinder.org

mybinder.org is a free web service to run Jupyter notebooks in the cloud.
Binder does automatically create a Docker image from a Git repository by
e.g. recognizing files like `requirements.txt`, `environment.yml` etc.

One way of enabling complex setups on Binder is to provide a `Dockerfile`
that inherits from one of the Jupyter Docker stack images. Here is a link
to our previously defined image: [![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/ssciwr/jupyter-docker-stacks-example/main)