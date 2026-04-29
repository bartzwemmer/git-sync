# Readme
This is a fork of the original git-sync repo. This fork was created to be able to deploy git-sync on Portainer. 
Specifically, the line:
```sh
echo $GIT_KEY >> ~/.ssh/id_ed25519 && chmod 600 ~/.ssh/id_ed25519
```
has been added to `entrypoint.sh`, to make it possible to copy the SSH client key from a Portainer secret named git-key.

## Git sync
The git-sync container is used to sync DAG's from a repository to an Airflow deployment.

## Environmental Variables
Create a `.env` file with the following contents for local testing:
```
GIT_SSH_KEY="foo"
REPO_URL="git@github.com:org/repo.git"
GIT_URL="github.com" # Do not include https:// or .git
SUBFOLDER_PATH="dags"
GIT_BRANCH="main"
DIRECTORY_NAME="directory"
DESTINATION_PATH="/app/sync"
INTERVAL=60
GIT_PULL_REBASE="false"
```
