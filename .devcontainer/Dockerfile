FROM kalilinux/kali-rolling:latest

# ユーザ'vscode'を作成する
ARG USERNAME=vscode
ARG USER_UID=1000
ARG USER_GID=$USER_UID

RUN apt update \
    && groupadd --gid $USER_GID $USERNAME \
    && useradd -s /bin/bash --uid $USER_UID --gid $USER_GID -m $USERNAME \
    && apt install -y sudo \
    && echo $USERNAME ALL=\(root\) NOPASSWD:ALL > /etc/sudoers.d/$USERNAME \
    && chmod 0440 /etc/sudoers.d/$USERNAME

RUN apt -y install python3 python3-pip
RUN apt -y install curl git

RUN pip install --upgrade pip
RUN pip install --upgrade setuptools
RUN pip install flake8 autopep8

USER vscode

RUN echo 'alias python="python3"' >> ~/.bashrc \
    && echo 'alias pip="pip3"' >> ~/.bashrc
