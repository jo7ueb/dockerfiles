FROM jupyter/scipy-notebook

# install Chainer
RUN pip install \
        chainer==3.4.0 \
    && fix-permissions $CONDA_DIR \
    && fix-permissions /home/$NB_USER
