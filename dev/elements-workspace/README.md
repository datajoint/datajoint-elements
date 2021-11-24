# Development Workspace for DataJoint Elements

A dev container to be used primarily with Visual Studio Code, but can be built and run without it. The installation process will download each [element and workflow](../../README.md#Elements) from GitHub (from datajoint or from your own fork) and install them as a development package within the container under the `elements` conda environment.

## Setup

_Read through these instructions completely before beginning to install._

Download the [`datajoint-elements`](https://github.com/datajoint/datajoint-elements) repo content if you haven't done so already.

```bash
git clone https://github.com/datajoint/datajoint-elements.git
```

You'll also need to [install Docker](https://www.docker.com/products/docker-desktop).

**General Notes:**

1. The container may take some time to initialize (it has to download the base image, run apt-get, conda env, and startup mysql). This is done once, and it'll load faster the next time.

2. If you don't need to wait for the database to start up and accept connections, set `condition: service_started` under `depends_on` in the [`dev/elements-workspace/docker-compose.yml`](docker-compose.yml) file.

3. To reduce the size and time of build for the docker image, comment out any unnecessary packages you may not need in the file [`dev/elements-image/environment.yml`](../elements-image/environment.yml).

4. Add any additional Debian dependencies in the file [`dev/elements-image/apt_requirements.txt`](../elements-image/apt_requirements.txt). You can also do this while the container is up and running with `sudo apt-get update && sudo apt-get install [...]` (only persistent while the container exists).

### Visual Studio Code Remote - Containers

Use a docker container as a [vscode dev environment](https://code.visualstudio.com/docs/remote/containers). Make sure you have the [remote containers extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers) installed.

Edit the file [`dev/elements-workspace/.devcontainer/devcontainer.json`](.devcontainer/devcontainer.json) to add additional extensions or change the default settings.

- **Important:** You'll need to edit the `git-elements` command under the `"postCreateCommand":` setting to use your own forks of the repos (see [Usage](#git-elements) below). Otherwise, it'll clone from the `datajoint` GitHub account by default.

Navigate to the `dev/elements-workspace` subfolder and open up `elements.code-workspace`. It should prompt you to reopen the folder in the dev container.

Alternatively, you can open the remote workspace using the [`devcontainer` CLI](https://code.visualstudio.com/docs/remote/devcontainer-cli).

```bash
devcontainer open dev/elements-workspace
```

Double-clicking or running the script in [`dev/elements-workspace/.devcontainer/vscode-open-dev-container`](.devcontainer/vscode-open-dev-container) will do the above for you.

**Notes:**

1. Sometimes vscode needs things from your host's shell environment, I don't know why. It may help to have this in your vscode settings: `"terminal.integrated.inheritEnv": true`.

2. Sometimes vscode needs to clear the default python. Open the Command Palette (Shift+Ctrl/⌘+P) then select `Python: Clear Workspace Interpreter Setting`.

### Docker Compose

You can also start the container using `docker-compose`. In your terminal, change to the [dev/elements-workspace](./) folder then run,

```bash
cd dev/elements-workspace
docker-compose up --build -d
```

After it has finished building and the container is up and running, you can open a terminal from within the container by running,

```bash
docker exec -it elements-workspace_conda_1 bash
```

You can install the elements and workflows using the command `git-elements`. See [Usage](#git-elements) below.

## Usage

### git-elements

The dev container has a shell script named [`git-elements`](../elements-image/git-elements) for cloning the elements repositories and installing them as development python packages. 

See the help documentation for `git-elements`:

- From within the container,

```bash
git-elements --help
```

- After the container has started and is running, from your host machine run,

```bash
docker exec -it elements-workspace_conda_1 git-elements --help
```

**Notes:**

1. Each element/workflow is installed in 'development mode' with `conda develop --build_ext .`. To uninstall, run `conda develop --uninstall .` from within the root of the package directory.
