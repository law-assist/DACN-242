# DACN-242
This repository is a bundle of source code repositories required to run the Law-assist project and their documentation for DACN 242. It includes:
- a Node.js/Nest backend server
- a React/Next.js frontend server
- a Pytorch and FastAPI python law linking AI module

## Branches Overview
- `main` is the **stable, production-ready** version to be deployed. Its submodules' branch will also be the deployment-ready branch of its respective repository.
- `dev` is the **development** branch for the whole project. It will use docker-compose to configure a dev environment for all submodule repos, each in their own dev container, including a database container. Its submodules' branch can be any feature, development branches of its childrens.

    ‼️***For guideline on development, please check the documentation on ***`dev`*** branch or wiki page***
  
- feature branches: please go to the respective submodule repository to integrate new feature into it instead of adding it directly to the parent repo

## Clone the repository
### Clone the parent repo
Use the following command to clone the repository to the current directory and initialize its submodules
```
git clone https://github.com/law-assist/DACN-242.git --recurse-submodules
```
### Clone the children repos
You can also clone the children repos independently. However, you have to recreate each development environment and setup a database manually.

Check the development guideline on each submodule repo for more infomation.
