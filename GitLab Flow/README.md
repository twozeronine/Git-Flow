# GitLab Flow

Github flow의 너무나도 간단한 배포와 환경구성, 릴리즈, 통합등의 단점을 보안하기 위해 GitLab에서 제시한 방법론

## Production branch with GitLab flow

![깃랩플로0](https://user-images.githubusercontent.com/67315288/123529259-7adf0800-d729-11eb-9baf-7b6753027bb8.png)

production 브런치가 존재하여 커밋한 내용들을 일방적으로 디플로이를 하는 형태, GitHub에서 브런치 하나를 더 구성하여 사용하는 이것도 조금은 간단한 구성이다.  
이렇게 구성하면 배포 자동화가 되어있지 않은 구성에서 어떻게 배포를 진행할 것인가에 대한 내용을 담았다.

## Environment branches with GitLab flow

![깃랩플로1](https://user-images.githubusercontent.com/67315288/123529195-060bce00-d729-11eb-8fd4-8890cf02bca7.png)

master와 production 사이에 pre-production을 두어 개발한 애용을 곧장 반영하지 않고 시간을 두고 반영을 하는 것을 말한다.  
Staging을 위한 공간을 만든다.

## Release branches with GitLab flow

![깃랩플로2](https://user-images.githubusercontent.com/67315288/123529196-073cfb00-d729-11eb-93e1-c0693cfec85a.png)

release한 브런치를 두고서 보안상 문제가 발생한 것이나 백 포트를 위해서 작업을 할 경우, cherry-pick을 이용해서 작업을 진행할 수 도 있다. 아니면 해당 릴리즈에서 발생하는 버그들을 묶어서 수정하는 방식으로 작업한다. 일반적으로 말하는 'upstream first' 정책이다.

## Merge /pull requests with GitLab flow

GitHub flow와 동일하다.

## Issues with GitLab flow

Issue 트러커와 연결하여 사용하는 것을 말한다. 긴 시간 동안 작업을 할 경우, 이슈를 생성하여 작업을 진행하는 것으로 브런치 이름에는 이슈번호를 적어 작업 중인 이슈가 어떤 것인지를 명확하게 해주는 것이 필요하다. 작업이 끝나거나 코드 공유가 필요한 시점이면 Merge/pull requests를 보낸다.
