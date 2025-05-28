# ROS2-dev-setup

**Light Development Setup for ROS 2 Jazzy using Docker Container**

This repository provides a development environment template for ROS 2 Jazzy projects using Docker Compose.

## Features

* **Ubuntu 24.04 (Noble)**
* **ROS 2 Jazzy**
* **VNC Server** for GUI access

## Quick Start

1. **Clone the repository** and `cd` into its root directory:

   ```bash
   git clone https://github.com/your-username/ROS2-dev-setup.git
   cd ROS2-dev-setup
   ```

2. **Launch containers in detached mode**:

   ```bash
   docker compose up -d
   ```

3. **Open a shell inside the running container**:

   ```bash
   docker exec -it $(docker compose ps -q ros2-container) bash
   ```

   *Alternatively, you can access the container via VS Code (recommended).*

   * Install the **Remote Development** extension pack:
     [https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.vscode-remote-extensionpack](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.vscode-remote-extensionpack)
   * Open the workspace in VS Code.
   * Press `CMD+SHIFT+P` (Mac) or `CTRL+SHIFT+P` (Win/Linux).
   * Select **Dev Containers: Rebuild and Reopen in Container**.

   *Note: Ensure the **Remote - Containers** extension is installed.*

4. **Alternative VS Code method**

   * Open the workspace in VS Code.
   * Open the `compose.yaml` file.
   * Click the **Run All Services** button at the top of the editor.

## Shared Workspace

Inside the container, the shared project folder is mounted at:

```
/home/ubuntu/Desktop/ROS2
```

If you find yourself logged in as `root`, switch to the `ubuntu` user and navigate to the workspace:

```bash
su ubuntu
cd $HOME/Desktop/ROS2
```

## GUI Access via VNC

After running `docker compose up -d`, open your browser to:

```
http://localhost:6080
```

to view the remote desktop.

---
