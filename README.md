# docker-jenkins-infraci

[![](https://img.shields.io/docker/pulls/jenkinsciinfra/ldap?label=jenkinsciinfra%2Fjenkins-infraci&logo=docker&logoColor=white)](https://hub.docker.com/r/jenkinsciinfra/jenkins-infraci/tags)

A docker image for the (private) service infra.ci.jenkins.io.

## Updating Plugins

```shell
bash ./bin/update-plugins.sh
```

This script uses the [Jenkins Plugin Manager Tool command line](https://github.com/jenkinsci/plugin-installation-manager-tool) under the hood to update the plugins.

## Update Jenkins Version

```shell
VERSION=$(jv get --version-identifier latest)
SUFFIX=jdk21
FULL_VERSION=jenkins/jenkins:${VERSION}-${SUFFIX}
sed -i 's|FROM .*|FROM '"${FULL_VERSION}"'|' Dockerfile
```
