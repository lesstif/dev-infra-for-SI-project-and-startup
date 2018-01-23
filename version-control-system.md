# Version Control System

<!-- toc --> 

## gitlab

### docker
* https://docs.gitlab.com/omnibus/docker/

SELinux 를 사용하지 않는다면 context 를 지정하는 옵션인  ***:Z*** 삭제.(Ex- *gitlan:Z*)

```sh
sudo docker run --detach \
    --hostname gitlab.example.com \
    --publish 443:443 --publish 80:80 --publish 22:22 \
    --name gitlab \
    --restart always \
    --volume /srv/gitlab/config:/etc/gitlab:Z \
    --volume /srv/gitlab/logs:/var/log/gitlab:Z \
    --volume /srv/gitlab/data:/var/opt/gitlab:Z \
    gitlab/gitlab-ce:latest
```

## gogs

Gogs is a painless self-hosted Git service. https://gogs.io

## 설치

- https://gogs.io/docs/installation/install_from_binary 에서 다운로드
- 압축 해제
- 실행

```sh
./gogs

```

## Gitea 

Gitea - Git with a cup of tea : A painless self-hosted Git service.

### Install from binary

1. 다운로드(https://dl.gitea.io/gitea/)

    **Linux**

    ```sh
    wget -O gitea https://dl.gitea.io/gitea/1.3.2/gitea-1.3.2-linux-amd64
    chmod +x gitea
    ```

    **Windows**

    ```sh
    mkdir c:\gitea
    wget -O c:\gitea\gitea.exe https://dl.gitea.io/gitea/1.3.2/gitea-1.3.2-windows-4.0-amd64.exe
    ```

2. 서비스 등록

    **Linux**

     ```sh
    sudo wget -O /etc/systemd/system/gitea.service https://github.com/go-gitea/gitea/blob/master/contrib/systemd/gitea.service
    sudo systemctl enable gitea
    sudo systemctl start gitea
     ```

    **Windows**

    ```sh
    sc create gitea start= auto binPath= ""C:\gitea\gitea.exe" web --config "C:\gitea\custom\conf\app.ini""
    ```

3. 실행

    ```sh
    gitea web
    ```

4. *http://localhost:3000* 에 Browser 로 연결

### install from docker image
TODO

