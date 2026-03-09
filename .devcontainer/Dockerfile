FROM tensorflow/tensorflow:latest-gpu-jupyter

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update \
    apt-get upgrade
    && apt-get install -y \
        libcudnn9-cuda-12 \
    && apt clean \
    && rm -rf /var/lib/apt/lists/*

RUN pip install pip -U \
    && pip install \
        opencv-python-headless pandas \
        ipython ipykernel scipy matplotlib notebook tqdm scikit-learn uv

RUN echo 'export CUDA_VISIBLE_DEVICES=-1' >> ${HOME}/.bashrc \
    && echo 'export TF_CPP_MIN_LOG_LEVEL=3' >> ${HOME}/.bashrc
