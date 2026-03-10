# qr-code-generator
docker qr code generator assignment

## Required Links
* **GitHub Repository:** [https://github.com/Reyesfrancisp/qr-code-generator](https://github.com/Reyesfrancisp/qr-code-generator)
* **DockerHub Image:** [https://hub.docker.com/r/reyesfrancisp/qr-code-generator-app](https://hub.docker.com/r/reyesfrancisp/qr-code-generator-app)

## Screenshots

### 1. Container Application Running
![Container Application Running](container-application-running.png)

### 2. Docker Logs Proof
![Docker Logs Proof](docker-proof-of-logs.png)

## Reflection: Dockerization Experience & Challenges

**1. Key Experiences**
Dockerizing this QR Code Generator demonstrated how easily we can eliminate the "it works on my machine" problem. By packaging the Python script alongside its dependencies (`qrcode`, `Pillow`, `validators`) inside a single container, the application can run identically on any host machine without needing to configure local Python environments.

**2. Challenges Faced**
The biggest hurdle was configuring volume mounts on a Windows 11 machine using Git Bash. When attempting to map the local `qr_codes` directory to the container's `/app/qr_codes` directory, the terminal environment automatically attempted to translate the path, resulting in a mangled folder name (`qr_codes;C`). This was resolved by either switching to a PowerShell terminal or prefixing the Docker run command with `MSYS_NO_PATHCONV=1` to bypass the terminal's path conversion bug. The other hardest part was just trying to get everything working with docker since I haven't used it before. Making sure all the settings and everything was connected to ensure smoother usage was key.