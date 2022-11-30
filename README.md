# CI with github

## 1. Exploration

- Clone the repository on your machine

```cmd
git clone https://github.com/KHEfreiIntervenant/CI-with-github.git
```

- Install the necessary librairies :

```cmd
pip install -r requirements.txt
```

- Launch the application :

```python
python app.py
```

> it runs on <http://127.0.0.1:5000>

- Test the app :

```python
python -m unittest 
```

## 2. Implement a github action

### 2.1  Push the code to your own repo

- Delete the __.git__ inside the __CI-with-github__ folder

- Initialize the local directory as a Git repository

```cmd
git init -b main
```

- Stage and commit all the files in your project

```cmd
git add . && git commit -m "initial commit"
```

- Create a repository on github (_without initializing it_)

- Copy the remote https URL  and execute :

```cmd
git remote add origin REMOTE_URL_LINK
```

- Push the code

```cmd
 git push origin main
```

### 2.2 Set up a python workflow on github actions

- Click "New workflow" on your "Actions" section within your Github repo

- Search "Python application" and click on "Configure"

- configure the yml file

## 3 Implement a job to build and push a docker file on docker hub from github action

- [create a docker hub account]("https://hub.docker.com/")

Note : You must have verified your email before proceeding

- Add in your github repo secrets :
  
DOCKER_HUB_USER_NAME your _docker hub username_

DOCKER_HUB_ACCESS_TOKEN your _docker hub access token_

- create a repository in docker hub

- Add a new job in your python workflow .yml file which will build and push your docker file on docker hub

[> tutorial to build and push a docker file to docker hub from github]("https://docs.docker.com/build/ci/github-actions/")
