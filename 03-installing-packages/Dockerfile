FROM quay.io/jupyter/base-notebook:2025-01-28

# Installing Debian/Ubuntu packages into the Docker image
USER root
RUN apt update && \
    apt install --no-install-recommends --yes \
      gnuplot && \
    apt clean && \
    rm -rf /var/lib/apt/lists/*
USER ${NB_USER}

# Install Conda packages - Conda is already present in all
# Jupyter Docker stacks
RUN conda install -c conda-forge \
      jupyter-resource-usage && \
    conda clean -a -q -y

# To avoid duplication of the dependency list, an alternative
# implementation is to copy and install an external environment
# file.
COPY --chown=${NB_UID} environment.yml ${HOME}/
RUN conda env update -n base --file ${HOME}/environment.yml && \
    conda clean -a -q -y && \
    rm ${HOME}/environment.yml
