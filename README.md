# CORE Compose

Just a small Docker Compose file to run the [CORE](https://github.com/coreemu/core) with a GUI.

## Requirements

Official CORE images are not available on any public registry, so you need to build the image yourself:

```bash
git clone git@github.com:coreemu/core.git
cd core
docker build -t emane-python -f dockerfiles/Dockerfile.emane-python .
docker build -t core -f dockerfiles/Dockerfile.ubuntu .
```

## Usage

```bash
xhost +local:root && docker compose up
```
