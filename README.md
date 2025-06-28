```markdown
# Docker FreeCAD on Windows

This repository provides a `docker-compose.yml` file for running FreeCAD within a Docker container on Windows.  **Important Note:** This uses a Linux-based FreeCAD image, which may have compatibility issues on Windows.  A native Windows image is strongly recommended if available.

## Prerequisites

* **Docker Desktop for Windows:**  Ensure Docker Desktop is installed and running, with WSL 2 enabled.
* **Docker Compose:** Install Docker Compose.

## Usage

1. **Clone this repository:**
   ```bash
   git clone https://github.com/alexleun/docker-FreeCAD-windows.git
   ```

2. **Navigate to the repository directory:**
   ```bash
   cd docker-FreeCAD-windows
   ```

3. **Modify `docker-compose.yml` (if necessary):**
    * **Volume Mapping:**  The `volumes` section maps a directory in the container to a directory on your Windows system.  **Ensure the Windows path (`C:/Users/<YOUR_USERNAME>/docker/freecad` in the example) exists and is accessible.**  Change this path if needed.  Create the directory if it doesn't exist.
    * **Port Mapping:** The `ports` section maps ports between the container and your host.  If port 3935 is already in use, change it.

4. **Start the container:**
   ```bash
   docker compose up -d
   ```

5. **Access FreeCAD:** FreeCAD should be accessible via your browser at `http://localhost:3935` (or the port you specified).


## Troubleshooting

* **Port Conflicts:** If the specified port is in use, change the port mapping in `docker-compose.yml`.
* **Path Issues:** Verify the volume mapping points to a valid, accessible directory on your Windows system.
* **Permissions:** Ensure your user account has the necessary permissions to access the mapped volume.
* **WSL 2:**  Confirm that WSL 2 is enabled in Docker Desktop settings.  This is crucial for running Linux containers effectively on Windows.


## Disclaimer

This setup uses a Linux-based FreeCAD image.  While it might work, performance and stability may be affected.  Consider using a native Windows FreeCAD Docker image if one becomes available.  This repository is provided as-is, without guarantees of functionality or support.


## License

MIT License
```
