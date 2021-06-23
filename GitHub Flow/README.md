# GitHub Flow

![github-flow](https://user-images.githubusercontent.com/67315288/123096386-0296ef00-d46a-11eb-9768-250ef577cc9c.png)

Git-flow가 Github에서 사용하기에는 복잡하다고 나온 브랜칭 전략입니다. 흐름이 단순한 만큼 role도 단순합니다. master 브랜치에 대한 role만 정확하다면 나머지 브랜치들에 대해서는 관여하지 않습니다. 즉, hotfix 브랜치나 feature 브랜치를 구분하지 않습니다. 다만 우선순위가 다릅니다.

Github의 기능 중 pull request 기능을 적극 활용하기를 권장합니다.

---

## 사용법

![순서 1](https://user-images.githubusercontent.com/67315288/123100400-0dec1980-d46e-11eb-9e7f-4f693995468e.png)

### 1. master 브랜치는 어떤 때든 배포가 가능하다

- master 브랜치는 항상 최신 상태며, stable 상태로 product에 배포되는 브랜치
- 이 브랜치에 대해서는 엄격한 role과 함께 사용한다
- merge하기 전에 충분히 테스트를 해야한다. 테스트는 로컬에서 하는 것이 아니라 브랜치를 push 하고 Jenkins로 테스트 한다.

![순서 2](https://user-images.githubusercontent.com/67315288/123100403-0f1d4680-d46e-11eb-8068-f472cc438b2a.png)

---

### 2. master에서 새로운일을 시작하기 위해 브랜치를 만든다면, 이름을 명확히 작성하자

- 브랜치는 항상 master 브랜치에서 만든다
- Git-flow와는 다르게 feature 브랜치나 develop 브랜치가 존재하지 않음
- 새로운 기능을 추가하거나, 버그를 해결하기 위한 브랜치 이름은 자세하게 어떤 일을 하고 있는지에 대해서 작성해주도록 하자
- 커밋메세지를 명확하게 작성하자

---

### 3. 원격지 브랜치 (default 값으로 origin )로 수시로 push 하자

- Git-flow와는 상반되는 방식
- 항상 원격지에 자신이 하고 있는 일들을 올려 다른 사람들도 확인할 수 있도록 해준다
- 이는 하드웨어 ( 로컬 환경 )에 문제가 발생해 작업하던 부분이 없어지더라도, 원격지에 있는 소스를 받아서 작업할 수 있도록 해준다.

![순서 3](https://user-images.githubusercontent.com/67315288/123100407-0f1d4680-d46e-11eb-888d-a81443484bf0.png)

---

### 4. 피드백이나 도움이 필요할 때, 그리고 merge 준비가 완료되었을때는 pull request를 생성한다

- pull request는 코드 리뷰를 도와주는 시스템
- 이것을 이용해 자신의 코드를 공유하고, 리뷰받자
- merge 준비가 완료되었다면 master 브랜치로 반영을 요구하자

![순서 4](https://user-images.githubusercontent.com/67315288/123100411-0fb5dd00-d46e-11eb-9354-b4a23875dba2.png)

---

### 5. 기능에 대한 리뷰와 논의가 끝난 후 master로 merge 한다

- 곧장 product로 반영이될 기능이므로, 이해관계가 연결된 사람들과 충분한 논의 이후 반영하도록 한다
- 물론 CI도 통과해야한다 !

![순서 5](https://user-images.githubusercontent.com/67315288/123100412-0fb5dd00-d46e-11eb-83b6-a305c27fe753.png)

---

6. master로 merge되고 push 되었을 때는, 즉시 배포되어야한다

- GitHub-flow의 핵심
- master로 merge가 일어나면 자동으로 배포가 되도록 설정해놓는다
