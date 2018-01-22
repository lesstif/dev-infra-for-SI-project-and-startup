# 지속적인 통합(Continuous Integration)

<!-- toc --> 

GitBook allows you to organize your book into chapters, each chapter is stored in a separate file like this one.

## Jenkins

Jenkins의 [추천 docker image인 blueocean](https://hub.docker.com/r/jenkinsci/blueocean/) 을 사용.
(LTS + blue ocean plugin)

```sh
docker run \
  -u root \
  --rm \  
  -d \ 
  -p 8080:8080 \ 
  -p 50000:50000 \ 
  -v jenkins-data:/var/jenkins_home \ 
  -v /var/run/docker.sock:/var/run/docker.sock \ 
  jenkinsci/blueocean 
```

- 참고 : https://jenkins.io/doc/book/installing/
