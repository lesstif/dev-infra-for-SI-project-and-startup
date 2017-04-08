# SI 프로젝트와 스타트업을 위한 개발 인프라 구성하기

SI(System Integration) 프로젝트나 스타트업 기업을 위한 개발 인프라 구축.

[**github**](https://github.com/lesstif/web-service-hardening)에 공개되어 있으며 EBook은 **[gitbook](https://lesstif.gitbooks.io/web-service-hardening/content/)** 에서 읽으실 수 있으며 다음 포맷으로 다운로드 가능합니다.

- [PDF](https://www.gitbook.com/download/pdf/book/lesstif/web-service-hardening)
- [EPub](https://www.gitbook.com/download/epub/book/lesstif/web-service-hardening)
- [Mobi](https://www.gitbook.com/download/mobi/book/lesstif/web-service-hardening)

로컬에서 gitbook 을 설치하고 볼 경우는 다음 명령어로 gitbook-cli 를 설치(node 와 npm 필요)합니다.

```sh
npm install gitbook-cli -g
gitbook install
gitbook serve
```

설치가 완료되면 브라우저로 http://localhost:4000/ 에 연결하면 됩니다.

## 목적

IT 프로젝트의 복잡도가 증대하면서 체계적으로 수행하기 위한 개발 인프라(형상관리, 이슈 관리, 저장소 관리, 지속적인 통합등) 구성은 필수 요소가 되었습니다.

하지만 개발 인프라의 구축은 TA(Technical Architect)나 

* 각 구성 요소별로 다양한 제품들이 많아서 선택이 어려움
* 설치가 어려워서  

이를 위해 도커




## 독자
개발자와 운영자, 아키텍트등 서비스를 개발하고 운영하는 기술자들을 대상으로 합니다.

## 제안과 기여

본 문서에서 틀린 부분이나 수정/추가되어야 할 부분이 있으면 Fork 후에 [PR](https://github.com/lesstif/dev-infra-for-SI-project-and-startup/pulls) 을 날려주시기 바라며 제안은 [issue](https://github.com/lesstif/dev-infra-for-SI-project-and-startup/issues) 를 통해서 해주시면 됩니다.

## 기여자

본 문서에 기여하신 분들입니다.
