# Don't forgot to put a star on this.

If you want to pull my image from docker hub, you can use the following command:

### For Python Docker Image

```bash
docker pull 0prashantyadav0/python-docker-demo:0.0.1.RELEASE
docker run -d -p 8000:8000 0prashantyadav0/python-docker-demo:0.0.1.RELEASE
```

### For Node Docker Image

```bash
docker pull 0prashantyadav0/node-docker-demo:0.0.1.RELEASE
docker run -d -p 3000:3000 0prashantyadav0/node-docker-demo:0.0.1.RELEASE
```

**Creating Custom Docker Images**

This section serves as a comprehensive reference for building tailored Docker images using the current repository as a foundation. By following these steps, you'll be equipped to create images that encapsulate your unique application requirements:

**1. Prerequisites:**

- **Docker Installation:** Ensure Docker is installed and running on your system. Refer to the official Docker documentation for installation instructions specific to your operating system: [https://docs.docker.com/engine/install/](https://docs.docker.com/engine/install/)
- **Dockerfile Familiarity:** Possess a basic understanding of Dockerfiles, the text files defining image creation instructions. A wealth of resources are available online to delve deeper into Dockerfiles: [https://docs.docker.com/reference/dockerfile/](https://docs.docker.com/reference/dockerfile/)

**2. Building Your Image:**

Navigate to the root directory of your project or to the directory containing your Dockerfile using your terminal. Then, execute the following command to initiate the image building process:

```bash
docker build -t <username>/<image-name>:version .
```

**Explanation:**

- `docker build`: This command triggers the Docker image building process.
- `-t <username>/<image-name>:version`:
  - `<username>`: Replace this with your Docker Hub username or a private registry address.
  - `<image-name>`: Provide the desired name for your image. Choose a descriptive and meaningful name.
  - `:version`: Specify a version tag for your image. You can utilize a versioning scheme that aligns with your project's release cycle (e.g., `0.1.0`, `1.2.3-beta`).

**3. (Optional) Tagging and Pushing (for Sharing):**

If you intend to share your image with others on Docker Hub or a private registry, you'll need to tag and push it. Here's the process:

**a. Tagging:**

- Assign a more specific tag (e.g., `latest`) using the `docker tag` command:

```bash
docker tag <username>/<image-name>:version <username>/<image-name>:latest
```

**b. Pushing (Assuming Docker Hub Authentication):**

- Log in to Docker Hub using the `docker login` command before pushing:

```bash
docker login
```

- Push the image to your repository:

```bash
docker push <username>/<image-name>:version
docker push <username>/<image-name>:latest
```

**4. Running the Container:**

Once your image is built, you can create a container from it and execute your application within it. Here's the command, assuming your Dockerfile exposes port 8000:

```bash
docker container run -d -p 8000:8000 <username>/<image-name>:version
```

**Explanation:**

- `docker container run`: This command launches a container based on the specified image.
- `-d`: This option runs the container in detached mode, allowing you to interact with your terminal promptly after starting the container.
- `-p 8000:8000`: This option maps the container's port 8000 (exposed by your Dockerfile) to port 8000 on your host machine. This enables you to access your application from the host at `http://localhost:8000/` (assuming your application listens on this port).

**5. Managing Containers:**

**Listing Running Containers:**

```bash
docker container ls
```

This command displays all running containers on your system, providing details like container IDs, images, ports, and names (if assigned).

**Stopping a Container:**

```bash
docker stop <container_name_or_id>
```

This command gracefully stops a running container. Replace `<container_name_or_id>` with the name you assigned to the container (if any) or its container ID. You can find container IDs from the output of `docker container ls`.

**Additional Considerations:**

- **Dockerfile Customization:** Adapt the Dockerfile instructions within this repository to cater to your specific application's needs. This may involve installing required dependencies, copying your application code, and exposing the appropriate ports.
- **Best Practices:** Refer to Docker best practices for creating efficient and secure images. Explore resources like the Docker documentation for in-depth guidance: [https://docs.docker.com/](https://docs.docker.com/)

By following these steps and leveraging the provided explanations, you'll be well-equipped to construct custom Docker images for your projects!

#### Note

Docker ignore file is not working .....
