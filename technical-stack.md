# 기술 스택
<!-- toc -->

다음과 같은 기술 스택을 사용했으며 해당 내용에 대해서 자세히 알지 않아도 개발 인프라를 구성하고 운영하는 것을 목표로 하고 있지만 대략적인 이해를 하는 것이 좋습니다.



## Linux

docker 는 Windows, OS X도 지원하지만 저자는 리눅스를 사용하는 것을 권장합니다.

프로젝트에 사용할 x86/64 기반의 PC 나 개발 서버를 장만한 후에 리눅스를 설치하세요.

리눅스 배포판은 우분투 서버(Ubuntu Server)나 레드햇 엔터프라이즈 리눅스(RHEL;Red Hat Enterprise Linux)/CentOS 중 익숙한 것을 사용하면 되며 docker 가 잘 지원되는 최신 OS(CentOS7, Ubuntu 16)를 사용해야 합니다.

## Docker

### Volume

데이타 영속성을 위한 docker volume directory 생성 및 사용

* https://docs.docker.com/storage/volumes/

## PostgreSQL

데이타 저장을 위한 DBMS.
MySQL 이 익숙하지만 라이센스가 자유롭고 성능이 뛰어난 postgreSQL 권장 

## Ref
* https://medium.com/@gurayy/setting-up-redmine-with-docker-be110387ba1c
* [docker volume의 사용방법과 차이점](https://darkrasid.github.io/docker/container/volume/2017/05/10/docker-volumes.html)

