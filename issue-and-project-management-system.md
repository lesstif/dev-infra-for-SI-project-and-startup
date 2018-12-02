Issue & Project Management System

<!-- toc --> 

GitBook allows you to organize your book into chapters, each chapter is stored in a separate file like this one.

## Atlassian JIRA

## Redmine

### docker volume 생성

Postgres 와 redmine 통신을 위한 네트웍 구성

```sh
docker network create — driver bridge redmine_network
```

```sh
$ docker volume create postgres-data
$ docker volume create redmine-data
```

# Ref
* [Setting up Redmine with Docker](https://medium.com/@gurayy/setting-up-redmine-with-docker-be110387ba1c)
* https://hub.docker.com/_/redmine/

