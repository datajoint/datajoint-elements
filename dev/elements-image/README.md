# Build instructions for `dev-image`

Change to the `dev-image` directory then build using the commands below. Change `--platform` to `linux/amd64` if you're not using an ARM machine. 

```bash
cd dev-image
VERSION=v1.0
docker build \
    --file=Dockerfile \
    --build-arg USER_NAME=dj
    --build-arg IMAGE_CREATED=$(date -u +'%Y-%m-%dT%H:%M:%SZ') \
    --build-arg IMAGE_VERSION=$VERSION \
    --platform=linux/arm64 \
    --tag=datajoint_elements:$VERSION \
    --tag=datajoint_elements:latest \
    .
```

To start the container, use `docker run`. 

```bash
docker run --name datajoint_elements -itd --init datajoint_elements:latest bash
```
