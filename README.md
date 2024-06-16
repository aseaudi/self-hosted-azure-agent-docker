# Self hosted Azure Pipelines Agent Docker

This project has a self hosted azure agent docker, which supports the following features:
* Ubuntu 22.04 LTS
* Powershell
* Terraform
* Docker-in-Docker for building images

How to build the docker image for the azure agent

docker build --tag "azp-agent:linux" --file "./azp-agent-linux.dockerfile" .

How to run the agent

docker run -d -e AZP_URL="https://dev.azure.com/aseaudi" -e AZP_TOKEN="<PERSONAL TOKEN>" -e AZP_AGENT_NAME="Docker Agent - Linux" --name "azp-agent-linux" azp-agent:linux

Go to your organization in dev.azure.com, then Project Settings, Agent Pools, Default, you should find your docker agent online.

Use the name of the agent, e.g. "Docker Agent - Linux", in your azure pipelines yaml file


