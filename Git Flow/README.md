# Git Flow

1. 기본 브런치를 5가지로 나눈다 feature > develop > release > hotfix > master
2. 머지 순서는 앞에서 뒤로 진행된다.
3. release 브런치와 hotfix 브런치의 경우, develop 브런치의 오른쪽에 존재하기에 모두 develop 브런치도 머지를 하도록 구성이 되어있다.

Git-Flow 전략은 주기적으로 배포를 해야하는 프로젝트에는 적합하지만, 브랜치가 많아 복잡하고 어떤 프로젝트에 따라서는 몇몇 브랜치가 애매한 포지션을 가질 수 있습니다.

![깃플로우](https://user-images.githubusercontent.com/67315288/123093588-d463e000-d466-11eb-9fd4-1093ec41822f.png)

## 메인 브랜치 ( Main branch)

master 브랜치와 develop 브랜치, 이 두 종류의 브랜치를 보통 메인 브랜치로 사용합니다.  
mater 브랜치와 develop 브랜치를 병행으로 유지합니다.

![깃플로우 메인 브랜치](https://user-images.githubusercontent.com/67315288/123093921-3b819480-d467-11eb-808c-c7f7b2e54df7.png)

- master
  -- 배포 가능한 상태만을 관리하는 브랜치
- develop
  -- 다음에 배포할 것을 개발하는 브랜치
  -- develop 브랜치는 통합 브랜치의 역할을 하며, 평소에는 이 브랜치를 기반으로 개발을 진행

## 보조 브랜치 ( Supporting branch )

피처 브랜치(feature branch) 또는 토픽 브랜치(topic branch)

![깃플로우 보조 브랜치](https://user-images.githubusercontent.com/67315288/123094059-6a980600-d467-11eb-9afc-7dde645eedee.png)

- 기능을 개발하는 브랜치로, develop 브랜치로부터 분기
- feature 브랜치는 그 기능을 다 완성할 때까지 유지하고, 다 완성되면 develop 브랜치로 merge ( 다음 배포에 확실히 넣을거라고 판단될 때 merge하고, 결과가 실망스러우면 바로 버린다. )
- feature 브랜치는 보통 개발자의 로컬 저장소에만 있는 브랜치이고 origin에는 push 하지 않는다

> develop 브랜치와 feature 브랜치
> 기존에 잘 작동하는 개발 코드 (develop 브랜치)와 새로 변경될 개발코드(feature 브랜치)를 분리하고 각각 보존하는 것
> feature 브랜치는 Git-flow 전략에서 지칭하는 단위 개발 브랜치의 의미를 갖는다

## 릴리즈 브랜치 ( release branch )

![깃플로우 릴리즈 브랜치](https://user-images.githubusercontent.com/67315288/123094602-06c20d00-d468-11eb-8a12-638a53a90dfa.png)

- 브런치 나오는 곳 : develop
- 브런치가 들어가는 곳 : develop, master
- 이름 지정 : release-\*
- develop 브랜치에 이번 버전에 포함되는 기능이 merge 되었다면 QA를 위해 develop 브랜치에서부터 release 브랜치를 생성
- 배포를 위한 최종적인 버그 수정 등의 개발을 수행
- 배포 가능한 상태가 되면 master 브랜치로 병합시키고, 출시된 master 브랜치에 버전 태그를 추가
- release 브랜치에서 기능을 점검하며 발견한 버그 수정 사항은 develop 브랜치에도 적용해 주어야함! 그러므로 배포 완료 후 develop 브랜치에 대해서도 merge 작업을 수행

## 핫픽스 브랜치 ( hotfix branch )

![깃플로우 핫픽스 브랜치](https://user-images.githubusercontent.com/67315288/123095903-82708980-d469-11eb-8d38-a2dcf31f7895.png)

- 배포한 버전에서 긴급하게 수정을 해야 할 필요가 있을 경우, master 브랜치에서 분기하는 브랜치
- 버그를 잡는 사람이 일하는 동안에도 다른 사람들은 develop 브랜치에서 하던 일을 계속할 수 있다
- 이 때 만든 hotfix 브랜치에서의 변경 사항은 develop 브랜치에도 merge하여 문제가 되는 부분을 처리해 주어야함

## 장점과 단점

- 장점

  - 명령어가 나와있다.
  - 웬만한 에디터와 IDE에는 플러그인으로 존재한다.

- 단점
  - 브런치가 많아 복잡하다. 러닝커브가 높다
  - 안 쓰는 브런치가 있다. 그리고 몇몇 브런치는 애매한 포지션이다.

---

# 참고 링크

[우아한 형제들 Git-flow](https://woowabros.github.io/experience/2017/10/30/baemin-mobile-git-branch-strategy.html)
