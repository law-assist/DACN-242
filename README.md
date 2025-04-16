# DACN-242 Development guideline

## Dev container
Recommended using [Visual Studio Code](https://code.visualstudio.com/) for development in container. Check this [document](https://code.visualstudio.com/docs/devcontainers/containers) for setting up a dev container.

1. Checkout to `dev` branch (in case you are not in current local branch)
```
git checkout dev
```
2. From VS Code command command palette, type "Reopen" and choose "Dev Containers: Reopen in Containers" option

  ![Dev Container option](https://github.com/law-assist/DACN-242/wiki/blob/master/image/reopen-in-container-option.png)

3. Choose "DACN-242 backend dev environment" option (You could choose frontend options first, the order is not important). Each option is a dev container for a submodule of the project

  ![Backend_dev_con_option](/documentation/backend_dev_con_option)

4. Open a new VS Code window, repeat the same steps above and choose the other options in step 3
5. Now, you can start developing normally like on your local machine for each submodule. Each dev container is able to communicate with each other, while has their dev environment seperate like an independent repo

‼️***Environment variables is already embedded in each dev container. However, if you want to custom them, create a `.env` file in each dev container and populate it according its respective guideline.***

## Local
Clone each submodule repo indenpendently and follow their own development guideline for setup
