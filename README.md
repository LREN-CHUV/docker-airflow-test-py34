[![CHUV](https://img.shields.io/badge/CHUV-LREN-AF4C64.svg)](https://www.unil.ch/lren/en/home.html) [![License](https://img.shields.io/badge/license-Apache--2.0-blue.svg)](https://github.com/LREN-CHUV/docker-airflow-test-py34/blob/master/LICENSE) [![DockerHub](https://img.shields.io/badge/docker-hbpmip%2Fairflow-test-py34-008bb8.svg)](https://hub.docker.com/r/hbpmip/airflow-test-py34/) [![ImageVersion](https://images.microbadger.com/badges/version/hbpmip/airflow-test-py34.svg)](https://hub.docker.com/r/hbpmip/airflow-test-py34/tags "hbpmip/airflow-test-py34 image tags") [![ImageLayers](https://images.microbadger.com/badges/image/hbpmip/airflow-test-py34.svg)](https://microbadger.com/#/images/hbpmip/airflow-test-py34 "hbpmip/airflow-test-py34 on microbadger") [![Codacy Badge](https://api.codacy.com/project/badge/Grade/e558dd428eda47c4a0ef76235841416d)](https://www.codacy.com/app/hbp-mip/docker-airflow-test-py34?utm_source=github.com&amp;utm_medium=referral&amp;utm_content=LREN-CHUV/docker-airflow-test-py34&amp;utm_campaign=Badge_Grade) [![CircleCI](https://circleci.com/gh/LREN-CHUV/docker-airflow-test-py34/tree/master.svg?style=svg)](https://circleci.com/gh/LREN-CHUV/docker-airflow-test-py34/tree/master)

# docker-airflow-test-py34

Base image to test Airflow using nosetests and Python 3.4.

## Install

This docker image is available as an automated build on [the docker registry hub](https://registry.hub.docker.com/u/hbpmip/airflow-test-py34/), so using it is as simple as running:


```console
$ docker run hbpmip/airflow-test-py34:1.8.2-2
```

## How to use this image

Create a new image including the source code and the unit tests to execute.

### Dockerfile

```dockerfile
FROM hbpmip/airflow-test-py34:1.8.2-2

COPY your_pkg/ /src/your_pkg/
COPY your/tests/ /src/tests/
```

then fill the database with tables and data, using something you want to test.

### Execute the tests

```dockerfile

WORKDIR /src/tests/
ENTRYPOINT ["nodetests", "your_tests.py"]

```

## Build

Run: `./build.sh`

## Test

Run: `./tests/test.sh`

## Publish on Docker Hub

Run: `./publish.sh`

## License

Copyright (C) 2017 [LREN CHUV](https://www.unil.ch/lren/en/home.html)

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

# Acknowledgements

This work has been funded by the European Union Seventh Framework Program (FP7/2007­2013) under grant agreement no. 604102 (HBP)

This work is part of SP8 of the Human Brain Project (SGA1).
