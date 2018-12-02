# On-Premise 환경에서 docker로 개발 인프라 구성하기

SI(System Integration) 프로젝트등 On-Premise 환경에서 개발 인프라 구성하기.

소스는 [**github**](https://github.com/lesstif/dev-infra-for-SI-project-and-startup)에 있으며 온라인 EBook은 [gitbook](https://lesstif.gitbooks.io/on-premise-docker/content/) 또는 **[gitbook v2](https://lesstif.gitbooks.io/dev-infra-for-si-project-and-startup/content/)** 에서 읽으실 수 있으며 다음 포맷으로 다운로드 가능합니다.

- [PDF](https://www.gitbook.com/download/pdf/book/lesstif/dev-infra-for-si-project-and-startup)
- [EPub](https://www.gitbook.com/download/epub/book/lesstif/dev-infra-for-si-project-and-startup)
- [Mobi](https://www.gitbook.com/download/mobi/book/lesstif/dev-infra-for-si-project-and-startup)

로컬에서 gitbook 을 설치하고 볼 경우는 다음 명령어로 gitbook-cli 를 설치(node 와 npm 필요)합니다.

```sh
npm install gitbook-cli -g
gitbook install
gitbook serve
```

설치가 완료되면 브라우저로 http://localhost:4000/ 에 연결하면 됩니다.

## 목적

IT 프로젝트의 복잡도가 증대하면서 체계적으로 수행하기 위한 개발 인프라(형상관리, 이슈 관리, 저장소 관리, 지속적인 통합등) 구성은 필수 요소가 되었습니다.

하지만 프로젝트에서 개발 인프라의 구축을 하려면 다음과 같은 어려움이 있었습니다. 

* 바쁜 일정 및 해당 업무를 수행할 전문가가 프로젝트 내에 없는 경우가 많음
  - TA, AA, SA,DA 등 다양한 Architect 가 있지만 개발 인프라 구성에 적합한 Architect 가 없습니다.
* 각 구성 요소별로 다양한 제품들이 많아서 선택이 어려움 
  * 이슈  및 프로젝트 관리 제품만 해도 redmine, trac, JIRA, trello 등 다양한 제품이 있어서 선택이 어렵습니다.
* 솔루션마다 설치와 설정이 제각각이며 경험이 없으면 설치가 어려움
  * 특히 ruby on rails 기반의 제품들 - gitlab, redmine 등은 설치가 매우 까다롭습니다)

위와 같은 이유때문에 개발 인프라를 사내에 설치형으로 사용하는 것 보다는 SaaS 기반으로 사용하는 것을 권장하지만 SaaS 로 제공되지 않는 제품을 사용해야 하거나 인터넷이 안 되는 SI 프로젝트등일 경우 설치형을 사용해야 합니다.  

위와 같은 환경에서 설치에 드는 시간과 비용을 최소화하기 위해 docker container 를 기반으로 개발 인프라를 구성하고 이를 기반으로 프로젝트를 진행하도록 도와주는 것이 이 문서의 목적입니다.

> **Info**  각 스택별 제품은 저자의 경험과 선호도에 따라 주관적으로 선정했습니다.  



## 망 분리 환경에서 사용

공공 SI 등의 보안 요건이 강화되면서 상당수 SI 프로젝트들이 물리적인 네트워크 망 분리 환경에서 작업을 하고 있습니다.

이로 인해 개발자가 google과 stackoverflow 에 연결할 수 없는 열악한 환경에서 프로젝트를 진행하는 경우가 많습니다.

인터넷이 되지 않을 경우 생산성이 매우 크게 떨어지며 개발 인프라 구성을 할 수 없는 문제가 있으므로 망 분리 환경에 들어가기 전에 개발 인프라 구성을 권장합니다.

## 제안과 기여

본 문서에서 틀린 부분이나 수정/추가되어야 할 부분이 있으면 Fork 후에 [PR](https://github.com/lesstif/dev-infra-for-SI-project-and-startup/pulls) 을 날려주시기 바라며 제안은 [issue](https://github.com/lesstif/dev-infra-for-SI-project-and-startup/issues) 를 통해서 해주시면 됩니다.

## 기여자

본 문서에 기여하신 분들입니다.
