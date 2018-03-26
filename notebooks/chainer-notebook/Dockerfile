FROM jo7ueb/scipy-notebook

# install Chainer
RUN pip install \
        chainer==3.5.0 \
	cupy==2.5.0 \
    && fix-permissions $CONDA_DIR \
    && fix-permissions /home/$NB_USER
