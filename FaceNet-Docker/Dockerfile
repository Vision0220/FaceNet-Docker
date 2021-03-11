FROM tensorflow/tensorflow:1.7.0-gpu-py3
RUN apt update
RUN apt install vim -y
RUN apt install libgl1-mesa-glx -y
RUN apt install net-tools
RUN apt install wget
RUN pip install --upgrade pip
RUN pip install opencv-python
RUN pip install django==2.2
EXPOSE 8000

# 解决中文乱码
# solve chinese display issue
ENV LANG C.UTF-8

# set these the same as system
ARG GROUPNAME=asep
ARG USERNAME=asep
ARG USER_ID=1004
ARG GROUP_ID=1003
# set up group and user
RUN groupadd -g ${GROUP_ID} $GROUPNAME
RUN useradd -u ${USER_ID} ${USERNAME} -g ${GROUPNAME}
RUN usermod -G sudo ${USERNAME}
USER ${USERNAME}
WORKDIR /home/${USERNAME}

USER root
COPY ./cuda/include/cudnn.h /usr/local/cuda/include/
COPY ./cuda/lib64/libcudnn* /usr/local/cuda/lib64/
RUN chmod a+r /usr/local/cuda/include/cudnn.h
RUN chmod a+r /usr/local/cuda/lib64/libcudnn*