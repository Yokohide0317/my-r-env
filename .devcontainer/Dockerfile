FROM yokohide0317/my-irkernel-env:0.1.0

ARG USERNAME=vscode
ARG USER_UID=1000
ARG USER_GID=$USER_UID

ENV CONDA_DIR=/opt/conda
ENV LANG=C.UTF-8 LC_ALL=C.UTF-8
ENV PATH=${CONDA_DIR}/bin:${PATH}

RUN groupadd --gid $USER_GID $USERNAME

RUN useradd -s /bin/bash --uid $USER_UID --gid $USER_GID -m $USERNAME \
    && echo $USERNAME ALL=\(root\) NOPASSWD:ALL > /etc/sudoers

#RUN localedef -f UTF-8 -i ja_JP ja_JP.UTF-8

# その他環境変数など
ENV LANG ja_JP.UTF-8
ENV LANGUAGE ja_JP:ja
ENV LC_ALL ja_JP.UTF-8
ENV TZ JST-9
ENV TERM xterm

USER $USERNAME
WORKDIR /home/$USERNAME

RUN pip install --no-cache-dir \
    autopep8 \
    flake8


RUN echo "conda activate r431_env" >> ~/.bashrc