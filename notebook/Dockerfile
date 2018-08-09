# Copyright (c) Siva Prasad Varma
# Distributed under terms of the Modified BSD License

# Pick your favorite docker-stacks image
FROM jupyter/datascience-notebook

USER jovyan

# Add permanent pip/conda installs, data files, other user libs here
# e.g., RUN pip install jupyter_dashboards

# install boosting packages
RUN pip install xgboost && \
    pip install lightgbm

# deep learning packages
# install tensflow non-gpu version for now
# figure out how to deal with cuda things later
# dont try to compile. compilation is taking days and days ...
RUN pip install tensorflow && \
    pip install keras && \
    conda clean -tipsy && \
    fix-permissions $CONDA_DIR && \
    fix-permissions /home/$NB_USER

USER root

# Add permanent apt-get installs and other root commands here
# e.g., RUN apt-get install npm nodejs
