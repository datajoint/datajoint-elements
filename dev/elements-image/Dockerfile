# DataJoint Elements Dev Image =========================================================
FROM iamamutt/conda_base:latest

ARG USER_NAME=dj
ARG IMAGE_CREATED=2021-11-11T11:11:11Z
ARG IMAGE_VERSION=v0.0
LABEL org.opencontainers.image.authors="Joseph Burling"
LABEL org.opencontainers.image.title="DataJoint Elements"
LABEL org.opencontainers.image.created="$IMAGE_CREATED"
LABEL org.opencontainers.image.version="$IMAGE_VERSION"
LABEL org.opencontainers.image.description="A dev image for each element and workflow"

# directory where default apt_requirements.txt and environment.yml are located
WORKDIR /srv/conda
COPY ["nodeps.txt", "apt_requirements.txt*", "environment.yml*", "./"]

# initialize new user, install debian packages, setup conda environment
RUN init-env

# add sudo support for new user
RUN echo ${USER_NAME} ALL=\(root\) NOPASSWD:ALL > /etc/sudoers.d/${USER_NAME} && \
    chmod 0440 /etc/sudoers.d/${USER_NAME}

# switch to newly created username
USER ${USER_NAME}

# add workspace and vscode folders to home directory
RUN \
    mkdir -p \
        /home/${USER_NAME}/datajoint-elements/elements \
        /home/${USER_NAME}/datajoint-elements/workflows \
        /home/${USER_NAME}/.vscode-server/extensions \
        /home/${USER_NAME}/.vscode-server-insiders/extensions && \
    chown -R ${USER_NAME} \
        /home/${USER_NAME}/datajoint-elements \
        /home/${USER_NAME}/.vscode-server \
        /home/${USER_NAME}/.vscode-server-insiders

# copy script to download and install each element/workflow on container start
COPY --chown=${USER_NAME} git-elements /usr/local/bin/
RUN chmod 770 /usr/local/bin/git-elements

# finalize
WORKDIR /home/${USER_NAME}/datajoint-elements
ENTRYPOINT ["conda-run"]
CMD ["tail", "-f", "/dev/null"]
