This repository contains files which are used to manage infrastructure on AWS.

#### Jump into the project working directory via Docker

Jump into the docker container

```sh
docker run \
  -it \
  --rm \
  -v $(pwd):/root/project \
  --workdir=/root/project \
  --env AWS_ACCESS_KEY_ID=YOUR_AWS_ACCESS_KEY \
  --env AWS_SECRET_ACCESS_KEY=YOUR_AWS_SECRET_KEY \
  --env SAM_CLI_TELEMETRY=0 \
  amazon/aws-sam-cli-build-image-python3.9 \
  bash
```

## Deploying a template

```bash
sam build --config-file samconfig-production.toml && \
sam deploy --config-file samconfig-production.toml
```