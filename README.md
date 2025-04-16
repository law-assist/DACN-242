# DACN-242
This repository is a bundle of source code repositories required to run the Law-assist project and their documentation for DACN 242. It includes:
- a Node.js/Nest backend server
- a React/Next.js frontend server
- a Pytorch and FastAPI python law linking AI module

## Branches Overview
- `main` is the **stable, production-ready** version to be deployed. Its submodules' branch will also be the deployment-ready branch of its respective repository.
- `dev` is the **development** branch for the whole project. It will use docker-compose to configure a dev environment for all submodule repos, each in their own dev container, including a database container. Its submodules' branch can be any feature, development branches of its childrens.

    ‼️***For guideline on development, please check the documentation on ***`dev`*** branch***
  
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

## Convention
- `docker-compose.yml` file in `main` branch must be for deployment, while on `dev` branch is for dev container.
- Submodules' branch on `main` must be their respective stable branch (i.e `main` or `master`). Therefore, don't commit any change in submodule folder directly to parent repo, including checkout to other branch.
    * Don't change any thing in submodule directly from the parent repo. Instead, go to that submodule and commit change to its respective repo (follow its own development guideline)

## Development
Recommended using [Visual Studio Code](https://code.visualstudio.com/) for development in container. Check this [document](https://code.visualstudio.com/docs/devcontainers/containers) for setting up a dev container.

‼️***Please check the documentation on ***`dev`*** branch***

## Deployment

Move to branch `main`

For the arm architecture, move to branch: `arm-main`

### Verify Docker Compose File

```
cat docker-compose.yml
```

### Crate env file and add content

```
sudo nano .env
```

#### BE

**MONGODB_URI**: Uri connect to the database contain the database name

**AI_HOST**: AI service running host

**JWT_SECRET**: Secret string when generating jwt token

#### FE

**NEXTAUTH_URL**: Web client call web server for authentication

**NEXT_SERVER_API_HOST**: Web server call BE API server

**NEXT_PUBLIC_API_HOST**: Web client call BE API server

**API_HOST**: Is like the NEXT_PUBLIC_API_HOST, when NEXT_PUBLIC_API_HOST is inaccessible

### Pull and deploy images

```
sudo docker compose up
```

### AI service compose

#### Move to AI folder

```
cd AI
```

#### Verify Docker Compose File

```
cat docker-compose.yml
```

#### Crate env file and add content

```
sudo nano .env
```

**DATABASE_URI**: Uri connect to the database without the database name

**DATABASE_NAME**: The database name

#### Pull and deploy images

```
sudo docker compose up
```

### Login with web with admin role after deploy successfully

```
  {
    "email": "qnvn2101@gmail.com",
    "password": "123456Ab"
  }
```

### Note

#### Port:

    fe port: 29000

    be port: 29001

    ai port: 29002

#### Expect host

    fe host: https://pl.thuanle.me

    be host: https://api-pl.thuanle.me
