# Docker PySpark

This image contains Spark/PySpark 3.0.1 and Python 3.7 (based on python:3.6-slim).

The Dockerfile is heavily based on [NeowayLabs/docker-spark](https://github.com/NeowayLabs/docker-spark).

Usage example:
```
FROM ...

# Show Python version on build step
RUN python -V

# Build application
ARG APP_DIR=/app
WORKDIR ${APP_DIR}
ADD requirements.txt .
ADD test_requirements.txt .
RUN python3 -m pip install -r requirements.txt
RUN python3 -m pip install -r test_requirements.txt
COPY . ${APP_DIR}

# Define default command
CMD ["/bin/bash"]
```
