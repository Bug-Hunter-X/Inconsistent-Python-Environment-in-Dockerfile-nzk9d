# Inconsistent Python Environment in Dockerfile

This repository demonstrates a common error in Dockerfiles: using an outdated base image and not specifying a precise Python version. This can lead to unpredictable behavior across different environments.

The original Dockerfile uses `ubuntu:latest`, which can change unexpectedly, and relies on system-installed Python without specifying a version.  The improved Dockerfile uses a specific Ubuntu version and specifies a Python version for better consistency.

## How to Reproduce the Bug
1. Clone the repository.
2. Build the original Dockerfile: `docker build -t inconsistent-python .`
3. Attempt to run the container: `docker run inconsistent-python` (observe any potential issues).
4. Build the corrected Dockerfile: `docker build -t consistent-python .`
5. Run the corrected container: `docker run consistent-python` (observe the more consistent output).

## How to Fix the Bug
Use a specific Ubuntu version and explicitly install the desired Python version.  This ensures that your build process is reproducible and consistent across different systems.