# docker-StaticJinjaPlus
Ported StaticJinjaPlus to docker for different builds. Source code: [StaticJinjaPlus](https://github.com/MrDave/StaticJinjaPlus)

## Available versions

| Tag                  | Description                                        | Base Image     | File       |
|----------------------|----------------------------------------------------|----------------|------------|
| `0.1.0`              | StaticJinjaPlus v0.1.0                             | `ubuntu`       | `ubuntu/Dockerfile.ver` |
| `0.1.1`              | StaticJinjaPlus v0.1.1                             | `ubuntu`       | `ubuntu/Dockerfile.ver`, `ubuntu/Dockerfile.latest` |
| `0.1.0-slim`         | StaticJinjaPlus v0.1.0                             | `python:slim`  | `python-slim/Dockerfile.ver` |
| `0.1.1-slim`         | StaticJinjaPlus v0.1.1                             | `python:slim`  | `python-slim/Dockerfile.ver`, `python-slim/Dockerfile.slim` |
| `develop`            | Latest commit from `main` branch (unstable)       | `ubuntu`       | `ubuntu/Dockerfile.develop` |
| `develop-slim`       | Latest commit from `main` branch (unstable)       | `python:slim`  | `python-slim/Dockerfile.develop` |
| `latest`             | Same as latest stable tag (currently `0.1.1`)     | `ubuntu`       | `ubuntu/Dockerfile.latest` |
| `slim`               | Same as latest stable slim version                | `python:slim`  | `python-slim/Dockerfile.slim` |

## How to use
To follow all the instructions you must have docker installed in advance: [Docker](https://www.docker.com/)

### Build the latest stable version (Ubuntu-based)
I recommend you use `Dockerfile.latest`, this is the newest and most stable version on Ubuntu.
```bash
docker build -f ubuntu/Dockerfile.latest -t image-name .
docker run -it image-name
```
### Build with Specific Version (parameterized)
If you want to choose version of StaticJinjaPlus.
Ubuntu base:
```bash
docker build -f ubuntu/Dockerfile.ver --build-arg VERSION=0.1.0 -t image-name .
docker run -it image-name
```
For the slim version:
```bash
docker build -f python-slim/Dockerfile.ver --build-arg VERSION=0.1.0 -t image-name .
docker run -it image-name
```
### Build develop Version (Latest main Commit)
This version uses the latest code from the GitHub main branch and may be unstable.
Ubuntu base:
```bash
docker build -f ubuntu/Dockerfile.develop -t -t image-name .
docker run -it image-name
```
For the slim version:
```bash
docker build -f python-slim/Dockerfile.develop -t -t image-name .
docker run -it image-name
```
