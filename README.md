# CORE Compose

Just a small Docker Compose file to run the [CORE](https://github.com/coreemu/core) with a GUI.

This setup was tested with CORE 9.2.0.

## Requirements

Official CORE images are not available on any public registry, so you need to build the image yourself:

```bash
git clone git@github.com:coreemu/core.git && \
cd core && \
git checkout tags/release-9.2.0 -b 9.2.0 && \
docker build -t emane-python -f dockerfiles/Dockerfile.emane-python . && \
docker build -t core:9.2.0 -f dockerfiles/Dockerfile.ubuntu .
```

## Usage

```bash
xhost +local:root && docker compose up
```
