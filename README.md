# DACN-242
This repository is a bundle of source code repositories require to run the Law-assist project for DACN 242. It includes:
- a Node.js/Nest backend server
- a React/Next.js frontend server
- a Pytorch and FastAPI python law linking AI module

## Branches Overview
- `main` is the stable, production-ready version to be deployed. Its submodules' branch will also be the deployment-ready branch of its respective repository.
- `dev` is the development branch for the whole project. It will use docker-compose to configure a dev environment for all submodule repos, each in their own dev container, including a database container. Its submodules' branch can be any feature, development branches of its childrens.
- feature branches: please go to the respective submodule repository to integrate new feature into it instead of add it directly to the parent repo

## Clone the repository
### Clone the parent repo
Use the following command to clone the repository to the current directory
```
git clone https://github.com/law-assist/DACN-242.git
```
Initialize submodule repo and fetch all data from its respective remote
```
git submodule init
git submodule update
```
### Clone the children repos
You can also clone the children repos independently to create a local dev or deployment environment. However, you have to create each environment and setup a database manually.

## Development in container
Recommended using [Visual Studio Code](https://code.visualstudio.com/) for development in container. Check this [document](https://code.visualstudio.com/docs/devcontainers/containers) for setting up a dev container.

Checkout to `dev` branch
