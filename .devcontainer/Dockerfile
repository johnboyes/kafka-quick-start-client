# Based on the example Dockerfile at:
# https://github.com/microsoft/vscode-dev-containers/blob/master/containers/debian/.devcontainer/Dockerfile

# Update the VARIANT arg in devcontainer.json to override the Debian version below
ARG VARIANT=buster
FROM mcr.microsoft.com/vscode/devcontainers/base:${VARIANT}

ARG GIT_EDITOR_SCRIPT_SOURCE="https://raw.githubusercontent.com/microsoft/vscode-dev-containers/master/containers/codespaces-linux/.devcontainer/git-ed.sh"

# Adapted from https://github.com/microsoft/vscode-dev-containers/blob/master/containers/codespaces-linux/.devcontainer/Dockerfile
RUN mkdir -p /tmp/git-ed \
    && wget -qO /tmp/git-ed/git-ed.sh ${GIT_EDITOR_SCRIPT_SOURCE} \
    && install -m 755 /tmp/git-ed/git-ed.sh /usr/local/bin/git-ed.sh \
    && git config --global core.editor "/usr/local/bin/git-ed.sh" \
# Clean up
    && rm -rf /tmp/git-ed
