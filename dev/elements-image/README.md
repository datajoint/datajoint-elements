# Build instructions for `elements-image`

Change to the `elements-image` directory then build using the commands below. Change `--platform` to `linux/arm64` if you're using an ARM machine. 

```bash
cd elements-image
VERSION=v1.0.0
docker build \
    --file=Dockerfile \
    --build-arg USER_NAME=dj
    --build-arg IMAGE_CREATED=$(date -u +'%Y-%m-%dT%H:%M:%SZ') \
    --build-arg IMAGE_VERSION=$VERSION \
    --platform=linux/amd64 \
    --tag=datajoint_elements:$VERSION \
    --tag=datajoint_elements:latest \
    .
```

To start the container, use `docker run`. 

```bash
docker run --name datajoint_elements -itd --init datajoint_elements:latest bash
```
