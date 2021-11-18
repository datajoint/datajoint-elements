# Dev Workspace for DataJoint Elements

A dev container to be used primarily with Visual Studio Code, but can be built and run without it. The installation process will download each [element and workflow](../../README.md#Elements) from GitHub (from datajoint or from your own fork) and install them as a development package within the container under the `elements` conda environment.

## Setup

Read through these instructions completely before beginning to install.

Download the `datajoint-elements` repo content if you haven't already. 

```bash
git clone https://github.com/datajoint/datajoint-elements.git
```

You'll also need to [install docker](https://www.docker.com/products/docker-desktop). 

**Notes:**

1. The container may take some time to initialize (it has to download the base image, run apt-get, conda env, and startup mysql). After this is done once it'll load faster next time.

2. Make sure you have this in your vscode settings: `"terminal.integrated.inheritEnv": true`.

3. If you don't need to wait for the database to start up and accept connections, set `condition: service_started` under `depends_on` in the `dev/elements-workspace/docker-compose.yml` file.

4. Edit the file `dev/elements-workspace/.devcontainer/devcontainer.json` to add additional extensions or change the default settings. You'll also want to edit the `git-elements` command to use your own forks (see [Usage](#git-elements) below).

### vscode

Make sure you have this extension installed: `https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers`

Navigate to `dev/elements-workspace` and open up `elements.code-workspace`. It should prompt you to reopen the folder in the dev container.

Alternatively, you can open the remote workspace using the [`devcontainer` CLI](https://code.visualstudio.com/docs/remote/devcontainer-cli).

```bash
devcontainer open dev/elements-workspace
```

### docker-compose

You can also start the container with `docker-compose`, assuming you're already in the `datajoint-elements` folder, run:

```bash
docker-compose -f dev/elements-workspace/docker-compose.yml up --build -d
```

After it has finished loading, you can open a terminal in the container by running,

```bash
docker exec -it elements-workspace_conda_1 bash
```

You can install the elements using the command `git-elements`. See [Usage](#git-elements).

## Usage

### git-elements

The dev container has a script called `git-elements` for initializing the elements repositories. See the help documentation for more details.

From within the container,

```bash
git-elements --help
```

After container is starting and running, from your host machine, run,

```bash
docker exec -it elements-workspace_conda_1 git-elements --help
```
