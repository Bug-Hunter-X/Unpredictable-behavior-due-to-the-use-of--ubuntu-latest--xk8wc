# Dockerfile Bug: Using `latest` Tag
This repository demonstrates a common mistake in Dockerfiles: using the `latest` tag for the base image.  The `ubuntu:latest` tag pulls the newest version of Ubuntu, which might cause unexpected issues if dependencies change.

## Problem
The provided Dockerfile uses `ubuntu:latest`. This means that each time the image is built, it could pull a different version of Ubuntu, leading to build inconsistencies and application failures.  Using a specific version is highly recommended to avoid such issues.

## Solution
The solution uses a specific version of Ubuntu, ensuring consistent builds across different environments. This avoids the risk of breaking changes caused by updating the base image.

## How to Reproduce
1. Clone this repository.
2. Build the original Dockerfile: `docker build -t unstable-app .`
3. Rebuild the Dockerfile multiple times. Observe potential differences in build output.
4. Build the updated Dockerfile: `docker build -t stable-app -f Dockerfile_solution .`
5. Rebuild the updated Dockerfile multiple times. Observe consistent build output.
