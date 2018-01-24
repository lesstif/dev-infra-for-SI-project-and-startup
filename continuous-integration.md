# 지속적인 통합(Continuous Integration)

<!-- toc --> 

GitBook allows you to organize your book into chapters, each chapter is stored in a separate file like this one.

## Jenkins

### install from docker

* 참고 : https://jenkins.io/doc/book/installing/

Jenkins의 [추천 docker image인 blueocean](https://hub.docker.com/r/jenkinsci/blueocean/) 을 사용.
(LTS + blue ocean plugin)

```sh
docker run \
  -u root \
  --rm \  
  -d \ 
  -p 8580:8080 \ 
  -p 50000:50000 \ 
  -v jenkins-data:/var/jenkins_home \ 
  -v /var/run/docker.sock:/var/run/docker.sock \ 
  jenkinsci/blueocean 
```
* *-p 50000:50000"* : JNLP 기반 jenkins agent 를 사용하지 않을 경우 제외 가능.

설치가 완료되었으면 [serve script](target-system-and-prerequisite.md#h5) 를 사용하여 nginx 가상 호스트 추가

```sh
sudo serve-tomcat.sh  jenkins.example.com 8580
```

### install from WAR



## Post instalation
* https://jenkins.io/doc/book/installing/#setup-wizard
