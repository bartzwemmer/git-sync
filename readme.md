# Readme
This is a fork of the original git-sync repo. This fork was created to be able to deploy git-sync on Portainer. 
Specifically, the line:
```sh
cat /run/secrets/git-key >> ~/.ssh/id_ed25519 && chmod 600 ~/.ssh/id_ed25519
```
has been added to `entrypoint.sh`, to make it possible to copy the SSH client key from a Portainer secret named git-key.

## Git sync
The git-sync container is used to sync DAG's from a repository to an Airflow deployment.