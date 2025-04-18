# Dockerhub

Note: The target only can use user password, PAT is not allowed by DockerHub.

## Create docker hub target
```
export DH_ADMIN_USER=
export DH_ADMIN_PWD=
akeyless target create dockerhub \
--name /devops/dockerhub/dh_admin_target \
--dockerhub-username $DH_USER \
--dockerhub-password $DH_PWD \
--profile devopsapi
A new target named /devops/dockerhub/dh_admin_target was successfully created
```

##
```
export AKL_GW_URL=https://gw-gke.wz.cs.akeyless.fans
akeyless dynamic-secret create dockerhub \
--name /devops/dockerhub/dh_dynamic_user \
--target-name  /devops/dockerhub/dh_admin_targe \
--gateway-url $AKL_GW_URL  \
--dockerhub-token-scopes 'repo:admin,repo:write,repo:read,repo:public_read' \
--profile devopsapi

```
