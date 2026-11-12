# Dockerized Nginx — Build Verification Lab
## Overview
A small infrastructure learning project that serves a static page from Nginx in Docker and builds the image in GitHub Actions. It demonstrates a basic container build, not a production deployment pipeline.

## Problem and Features
Package one HTML page into a repeatable web-server image. The workflow checks out the repository, reads the HTML file, and runs `docker build`. Reading the file is not HTML validation or a functional service test.

## Technologies and Structure
| Path | Purpose |
| --- | --- |
| `Dockerfile` | Uses nginx:alpine and copies the page to the Nginx web root |
| `index.html` | Static sample page |
| `.github/workflows/ci-pipeline.yml` | Build-verification workflow |

## Installation and Usage
With Docker available, run from the repository root:
```sh
docker build -t hello-albarq:local .
docker run --rm -p 8080:80 hello-albarq:local
```
Visit `http://localhost:8080/`. No credentials or environment variables are required. Runtime verification was not performed during this documentation update.

## Future Improvements
Add an HTTP smoke test, validate HTML, pin the base image for reproducibility, and review workflow dependency versions. Do not describe this lab as a full CI/CD deployment.

## Author
[Albarq-CS](https://github.com/Albarq-CS)
