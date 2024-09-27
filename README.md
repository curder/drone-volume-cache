# drone-volume-cache
[![drone-volume-cache on Docker Hub](https://img.shields.io/docker/automated/curder/drone-volume-cache.svg)](https://hub.docker.com/r/curder/drone-volume-cache/)

This is a pure Bash [Drone](https://github.com/drone/drone) 0.5+ plugin to cache files and/or folders to a locally mounted volume.

For more information on how to use the plugin, please take a look at [the docs](https://github.com/curder/drone-volume-cache/blob/master/DOCS.md).

## Docker
Build the docker image by running:

```bash
docker build --rm=true -t ghcr.io/curder/drone-volume-cache:latest .
```

For Apple Silicon or other arm-based CPUs, use the `--platform linux/arm64` option.

## Usage
Execute from the working directory:

```bash
docker run --rm \
  -e PLUGIN_REBUILD=true \
  -e PLUGIN_MOUNT="./node_modules" \
  -e DRONE_REPO_OWNER="foo" \
  -e DRONE_REPO_NAME="bar" \
  -e DRONE_JOB_NUMBER=0 \
  -v $(pwd):$(pwd) \
  -v /tmp/cache:/cache \
  -w $(pwd) \
  ghcr.io/curder/drone-volume-cache:latest
```

## Mirrors

- Aliyun

  `registry.cn-hangzhou.aliyuncs.com/curder/drone-volume-cache`
  
- Github

    `ghcr.io/curder/drone-volume-cache`
