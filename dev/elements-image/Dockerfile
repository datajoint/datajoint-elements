# DataJoint Elements Dev Image =========================================================
FROM ghcr.io/iamamutt/conda_base:latest

ARG NEW_USER_NAME=dj
ARG NEW_USER_GROUP=dj
ARG NEW_USER_SUDO=true
ARG IMAGE_CREATED=2021-11-11T11:11:11Z
ARG IMAGE_VERSION=v0.0.0a

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

SHELL ["/bin/bash", "--login", "-c"]

# copy script to download and install each element/workflow on container start
COPY --chown=${NEW_USER_NAME}:condauser git-elements /usr/local/bin/

# add workspace and vscode folders to home directory
RUN chmod 775 /usr/local/bin/git-elements && \
    mkdir -p -m 2775 \
        /home/${NEW_USER_NAME}/.vscode-server/extensions \
        /home/${NEW_USER_NAME}/.vscode-server-insiders/extensions \
        /home/${NEW_USER_NAME}/datajoint-elements/elements \
    /home/${NEW_USER_NAME}/datajoint-elements/workflows && \
        chown -R ${NEW_USER_NAME}:condauser \
        /home/${NEW_USER_NAME}/.vscode-server* \
        /home/${NEW_USER_NAME}/datajoint-elements

RUN mamba clean -qya
USER ${NEW_USER_NAME}:condauser
WORKDIR /home/${NEW_USER_NAME}/datajoint-elements
ENTRYPOINT ["sudo-run"]
CMD ["tail", "-f", "/dev/null"]
