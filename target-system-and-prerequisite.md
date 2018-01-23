# 목표 시스템 및 사전 필요 지식

<!-- toc --> 

# 목표 시스템

응용 서비스는 아래의 포트를 사용하도록 구성했고 각각 도메인을 부여하고 가상 호스트로 연결하여 사용합니다.

개발자 PC에서 연결할 수 있도록 hosts 파일에 도메인을 추가하거나 로컬 DNS 서버를 구성해서 사용합니다.

| 서비스                                      | App Port | Domain                                   |
| ---------------------------------------- | -------- | ---------------------------------------- |
| [gitlab](https://gitlab.com)             | 8080     | gitlab.example.com                       |
| [gogs](https://gogs.io)                  | 8180     | gogs.example.com                         |
| [gitea](https://gitea.io/)               | 8280     | gitea.example.com                        |
| [redmine(이슈 관리)](http://www.redmine.org) | 8380     | redmine.example.com, issue.example.com   |
| [JIRA(이슈 관리)](https://www.atlassian.com/software/jira) | 8480     | jira.example.com, issue.example.com      |
| [Jenkins(지속적인 통합)](https://jenkins.io/)  | 8580     | jenkins.example.com, ci.example.com      |
| [Bamboo(지속적인 통합)](https://www.atlassian.com/software/bamboo) | 8680     | bamboo.example.com, ci.example.com       |
| [nexus(저장소 관리)](http://www.sonatype.org/nexus/) | 8780     | nexus.example.com                        |
| [confluence](https://www.atlassian.com/software/confluence) | 8880     | confluence.example.com, wiki.example.com |

설치가 끝난 후에 다음 스크립트를 실행해서 가상 호스트를 추가한 후에 웹 서버와 application server 를 reverse proxy 로 연결해 줍니다.

1. [gist](https://gist.github.com/lesstif/4d162c4c8df756a65286) 다운로드

   ```sh
   curl -o serve-tomcat.sh https://gist.githubusercontent.com/lesstif/4d162c4c8df756a65286/raw 
   sudo mv serve-tomcat.sh /usr/local/bin/ 
   sudo chmod +x /usr/local/bin/serve-tomcat.sh
   ```

2. 가상 호스트 추가(*server-tomcat.sh domain port*)

   ```sh
   sudo serve-tomcat.sh  gitlab.example.com 8080
   ```

3. 정상적으로 종료되면 가상 호스트 설정이 추가된  */etc/nginx/sites-available/gitlab.example.com* 설정 파일이 생기고 nginx 도 구동됩니다.



**CentOS 계열은 */etc/nginx/nginx.conf* 의 http 블록에 다음 내용을 추가해야 합니다.**

```sh
http {
  # ....
  
  include /etc/nginx/conf.d/*.conf;
  include /etc/nginx/sites-enabled/*;
}
```



## # 사전 필요 지식



## 가상 호스트(Virtual Host)

하나의 웹 서버로 여러 가지 웹 서비스를 하기 위한 가상 호스트 지식

* https://www.lesstif.com/pages/viewpage.action?pageId=24445674



## Reverse Proxy

웹 서버와 WAS 를 연결하기 위한 reverse proxy.

* https://www.lesstif.com/pages/viewpage.action?pageId=21430345





### HTTPS(SSL, TLS)

https 를 지원하도록 웹 서버를 설정하는 방법

* https://lesstif.gitbooks.io/web-service-hardening/content/ssl-tls-https.html#%EC%9B%B9-%EC%84%9C%EB%B2%84-%EC%84%A4%EC%A0%95%ED%95%98%EA%B8%B0



