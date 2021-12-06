FROM jupyter/base-notebook:2021-11-20

COPY --chown=${NB_UID} helloworld.ipynb data.txt ${HOME}/

ENV JUPYTER_ENABLE_LAB=YES
