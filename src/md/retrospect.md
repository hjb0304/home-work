# 🧐 1,2주차 회고

## CLI와 Git

### ✏ 학습 내용

#### Shell

> 운영 체제와 사용자 간의 인터페이스 역할을 하는 프로그램. 터미널에서 CLI를 제공하여 사용자가 컴퓨터와 상호작용할 수 있게 한다.

<br>

#### CLI

> Command Line Interface  
> 디렉토리 생성 및 이동, 복사, 이름 변경, 삭제 등을 미리 약속된 명령어를 사용하여 실행하는 환경

<br>

#### CLI 명령어

- `pwd` 현재 작업중인 폴더 확인

- `mkdir` 폴더 생성

- `cd` 디렉토리 이동

  - `cd ..` 상위 디렉토리로 한 단계 이동

- `ls` 디렉토리 및 파일 목록 출력

- `touch` 빈 파일 생성

- `echo` 간단한 내용이 들어있는 파일 생성

- `cat` 파일 내용 확인

- `rm` 파일/디렉토리(비어있지 않은) 삭제

  - `rm -r <폴더>` 폴더 내부 하위 디렉토리까지 모두 삭제

- `rmdir` 디렉토리 제거

- `mv` 파일/디렉토리 이동, 이름 변경

- `cp` 파일/디렉토리 복사

<br>

#### Git

> 협업과 소프트웨어 개발에 사용되는 분산형 **버전 관리 **시스템

- **버전관리**
  파일 변화를 시간에 따라 기록했다가 나중에 특정 시점의 버전을 다시 꺼내올 수 있는 시스템

<br>

##### Git의 세 가지 상태

- `Committed` 데이터가 로컬 데이터베이스에 안전하게 저장됐다는 것을 의미한다.
- `Modified` 수정한 파일을 아직 로컬 데이터베이스에 커밋하지 않은 것을 말한다.
- `Staged` 현재 수정한 파일을 곧 커밋할 것이라고 표시한 상태를 의미한다.
  <br>

##### Git 프로젝트의 세 가지 단계

![](https://velog.velcdn.com/images/hjb0304/post/cf8b33a2-59e5-44e1-8c1b-13529c434902/image.png)

- `Working Directory`
  프로젝트의 특정 버전을 Checkout 한 것. 실제 파일들이 존재하고 **수정**할 수 있다.
- `Staging Area(Index)`
  곧 **커밋**할 파일에 대한 정보를 **저장**하는 영역. 수정한 파일 중 원하는 파일을 stage해서 **일시적**으로 저장한다.
- `git directory(Repository)`
  Git이 프로젝트의 메타데이터와 객체 데이터베이스를 **저장**하는 곳. 다른 컴퓨터의 저장소를 clone할 때 만들어진다.
  <br>

##### 참고 자료

> https://git-scm.com/book/ko/v2 > <br>

#### Git CLI와 GUI

Git은 CLI와 GUI 방식으로 사용할 수 있다.
Git GUI는 VS Code에도 내장되어 있어 손쉽게 사용할 수 있지만, Git의 모든 기능을 이용하고 싶다면 **CLI**를 사용하는 것이 좋다.
나는 VS Code의 Terminal을 이용해 Git CLI를 사용하고 있다. 이 글에서는 Git을 처음 설치한 뒤 해야 하는 환경 설정에 대해 정리해 보았다.
<br>

#### VS Code terminal 기본 쉘 설정

Command Palette(`Ctrl+Shift+P`) => Select Default Profile => Git Bash 선택
<br>

#### 사용자 정보 설정

git 사용자에 대한 정보를 설정한다. 이처럼 `--global` 옵션으로 하는 설정은 최초 한 번만 하면 된다.

- 사용자 이름
  `git config --global user.name "John Doe"`
- 사용자 이메일 주소
  `git config --global user.email johndoe@example.com`
  <br>

#### Git 기본 에디터 설정

`git config --global core.editor "code --wait"`
<br>

#### 공백 문자 설정

`git config --global core.autocrlf true`

- 줄바꿈 관련 경고 메시지 숨김
  `git config --global advice.ignoreCrLfWarning true`
  <br>

#### 기본 브랜치 이름 변경

기본 브랜치 이름을 master에서 main으로 변경한다.
`config --global init.defaultBranch main`
<br>

#### Git log 간결하게 보기

`git config --global core.pager "less -F -X"`
<br>

#### Git Config 설정 확인

Git 설정값을 확인할 수 있다.
`git config --list`

#### Git init

현재 디렉토리를 git 저장소로 생성한다. .git 폴더(숨김 폴더)가 생성된다.
<br>

#### Git status

현재 상태를 확인할 수 있다.

- 변경된 파일명(빨강): Working Directory 상태
- 변경된 파일명(초록): Staging Area 상태
- nothing to commit, working tree clean: 변경 내용 없음
  <br>

#### Git diff

파일의 변경 내용을 비교할 수 있다.
<br>

#### Git add

Working Directory에 있는 파일의 변경사항을 Staging Area에 추가할 수 있다.

- 특정 파일 추가

```
git add <file>
```

- 모든 파일 추가

```
git add .
```

<br>

#### Git restore

작업한 내용을 되돌릴 수 있다.

- Working Directory의 변경 내용을 되돌릴 경우

```
git restore <file>
```

- Staging Area의 변경 내용을 Working Directory로 되돌릴 경우

```
restore --staged <file>
```

<br>

#### Git commit

파일의 변경 사항에 대한 내역을 생성한다.

- 커밋

```
git commit -m "커밋 메시지"
```

- 마지막 커밋 메시지 수정
  명령어 입력 후 커밋 메시지 수정 창이 뜨면 수정하고 닫는다.

```
git commit --amend
```

<br>

#### Git rebase

특정 커밋을 수정한다. hash에는 git log를 입력했을 때 뜨는 특정 커밋의 고유 번호를 입력한다. 또는 HEAD~ 뒤에 원하는 커밋의 순서를 입력한다. (HEAD에 있는 커밋이 1)

명령어 입력 후 뜨는 창에서 **pick**을 다른 명령어로 수정해 원하는 방식을 선택한다.

```
git rebase -i <hash>
git rebase -i HEAD~<숫자>
```

<br>

#### Git log

커밋 이력을 확인할 수 있다.

- 커밋 이력 한 줄로 보기

```
git log --oneline
```

- 커밋 이력 그래프로 보기

```
git log --graph
```

<br>

#### Git checkout

과거 커밋 이력을 확인할 수 있다.

- 특정 커밋으로 이동

```
git checkout <hash>
```

- 이전 n개의 커밋으로 이동

```
git checkout HEAD~<숫자>
```

- 마지막 커밋으로 복귀

```
git checkout main
```

<br>

#### Git reset

이전 커밋으로 복원할 수 있다.

- `--mixed(default)`: 커밋 기록은 삭제되지만 Working Directory에 변경 사항은 남긴다.

```
git reset HEAD~<숫자>
```

- `--soft`: 커밋 기록은 삭제되지만 Working Directory와 Staging Area에 변경 사항은 남긴다.

```
git reset --soft HEAD~<숫자>
```

- `--hard`: HEAD~<숫자> 커밋으로 복원되며 이후에 변경된 커밋 기록은 모두 삭제된다.

```
reset --hard HEAD~<숫자>
```

<br>

#### Git branch

브랜치를 생성, 삭제, 수정한다.

- 브랜치 생성

```
git branch <이름>
```

- 브랜치 삭제

```
git branch -d <이름>
```

- 브랜치 이름 변경

```
git branch -m <이름> <수정된 이름>
```

<br>

#### Git switch

브랜치를 이동할 수 있다.

- <이름> 브랜치로 이동

```
git switch <이름>
```

- <이름> 브랜치를 만들고 바로 이동

```
git switch -c <이름>
```

<br>

#### Git remote

remote 브랜치를 담당하는 명령어

- 리모트 브랜치 조회

```
git remote -v
```

- 리모트 브랜치 추가

```
git remote add origin <https://github.com/ID/REPOSITORY>
```

- 리모트 브랜치 삭제

```
git remote rm origin
```

<br>

#### Git push

로컬 브랜치의 변경 이력을 리모트 브랜치로 전송한다.

```
git push origin <브랜치>
```

- 최초 push할 때
  -u: --set-upstream의 약자

```
git push -u origin <브랜치>
```

<br>

#### Git pull

리모트 브랜치의 변경 이력을 로컬 브랜치로 가져온다. git fetch와 git merge를 합친 것이다.

```
git pull origin <브랜치>
```

<br>

#### Git merge

브랜치를 병합한다.

- <브랜치> 브랜치를 현재 브랜치에 병합한다.

```
git merge <브랜치>
```

- fast forward merge
- 3-way merge
  <br>

#### Git stash

git에서 변경된 파일을 임시로 보관하고 나중에 다시 적용한다.
<br>

### 🤔 느낀점

평소에 자주 사용하면서도 쓰는 명령어만 썼던 git에 대해서 처음부터 차근차근 익힐 수 있었다. git이 어떤 원리로 돌아가는지부터 다양한 명령어의 쓰임새까지 많은 내용을 배우고 나니 앞으로 좀더 효율적으로 git을 사용할 수 있을 것 같다.

<br>

## Figma

### ✏ 학습 내용

#### 단축키

N: 프레임 한 장씩 이동
[ / Ctrl + [ : 순서 위/아래로 이동
Ctrl + P: 단축키 검색
Alt + L: 레이어 모두 접기
Shift + 방향키: big nudge 설정값만큼 이동(기본 패딩값)

#### Component Variants

/로 그룹 관리
컴포넌트 작명: key=value, key=value…

#### Component property

텍스트가 자주 바뀌는 컴포넌트에는 text property 넣기(동시에 수정 가능)
icon의 경우 component set이 아닌 개별 component로 생성(화살표 제외)

#### Auto Layout

Constraints: 개체 크기가 변경될 때 기준점을 설정

<br>

### 🤔 느낀점

하루만에 figma의 모든 기능을 익히는 건 어려웠지만 핵심적인 기능들을 빠르게 배울 수 있어 좋았다. 기본적인 기능들을 어떻게 더 쉽게 사용할 수 있는지 알게 되었다.

<br>

## Node와 NPM

### ✏ 학습 내용

#### Node

> 브라우저 외부에서 V8 Javascript 엔진을 실행할 수 있는 Javascript 런타임 환경

<br>

#### NPM

> Node Package Manager
> Javascript 프로그래밍 환경에서 패키지를 설치하고 관리하는 도구. 주로 Node.js 환경에서 사용된다.

<br>

#### NPM 명령어

<hr>

##### NPM을 최신 버전으로 업데이트

```
npm i -g npm@latest
```

##### NPM 패키지 설치

- 전역(Global)으로 설치: 어느 폴더에서나 가능

```
npm i -g <패키지>
```

- 로컬(Local)으로 설치: 프로젝트 폴더에서 설치

```
npm i <패키지>
```

##### NPM 패키지 삭제

- 전역(Global) 패키지 삭제

```
npm un -g <패키지>
```

- 로컬(Local) 패키지 삭제

```
npm un <패키지>
```

<br>

#### package.json

> Node.js 프로젝트에서 사용되는 메타데이터 파일
> 프로젝트의 이름, 버전, 의존성 패키지 정보 등을 포함하고 있다.

- 프로젝트 루트 리렉토리에 위치한다.
- `npm init` 명령어로 초기화시킬 수 있다.
- 다른 사람의 git 저장소로부터 내려받은 프로젝트 파일에서 `npm i`를 사용하면 프로젝트의 패키지 정보를 업데이트할 수 있다.

<br>

### 🤔 느낀점

git과 마찬가지로 프로젝트에서 자주 사용하는 node.js와 NPM의 개념부터 설정 방법까지 기초부터 다시 익혔다. 왜 쓰는지도 모르고 사용했던 명령어들의 작동 방식에 대해 알고 나니 앞으로는 node와 NPM에 대해 하나하나 이해하면서 사용할 수 있을 것 같다.

<br>

## HTML

### ✏ 학습 내용

#### HTML이란?

> HyperText Markup Language
> 웹에 표시되는 문서의 구조를 설명하는 표준 마크업 언어

- 의미있는 방식으로 문서를 구조화함
- 요소는 tag로 구분함
  ![](https://velog.velcdn.com/images/hjb0304/post/22aa65bc-1d46-429a-8aa8-4a077f5788c7/image.png)

- VS Code는 Emmet을 내장하고 있어 단축어를 통해 사용 가능함
- Emmit이란? HTML, XML, XSL 문서 등을 편집할 때 빠른 코딩을 위해 사용하는 플러그인
- 대소문자를 구분하지 않음

<br />

##### 시맨틱 마크업

용도에 맞는 요소를 사용해 마크업을 하는 것

<br />

##### 중첩 태그(Nesting Tag)

태그 안에 태그를 넣는 것

<br />

##### 빈 태그(Empty Element)

종료 태그가 없는 태그
`<input>, <img>...`

<br />

##### 속성(Attributes)

요소에 대한 정보를 제공. 여는 태그에 나타남
![](https://velog.velcdn.com/images/hjb0304/post/297a7f5a-36f4-484d-abdf-e883895f0c5d/image.png)

- 논리 속성: required처럼 값이 필요하지 않은 속성
  `<input type="radio" required/>`

<br />

##### HTML 기본 구조

```
<!DOCTYPE html>
<html lang="ko">
  <head>
  </head>
  <body>
  </body>
</html>
```

<br />

VS Code에 ! 입력 시 자동완성됨

<br />

##### XTML

> XML 기반의 마크업 언어
> HTML보다 엄격한 문법을 가짐

- 소문자로 작성함
- 닫는 태그가 필수적임
  `<img />`
- 속성은 반드시 값을 가져야 함
  `<input type="radio" required="required"/>`

<br />

##### HTML5

> HTML의 다섯번째 버전
> WWW의 핵심 마크업 언어

- `콘텐츠 모델`: HTML5에서 카테고리를 정의하여 각 요소별로 비슷한 성격을 가지고 있는 것끼리 그룹화한 것
- `아웃라인 알고리즘`: 웹페이지의 정보 구조를 판별할 수 있는 개념
- 다양한 API가 추가됨
- HTML 4.01과 XHTML 1.0의 형식을 모두 허용
- 소문자로 작성 권장
- 특수문자는 Entity Code로 변환해 사용
  참고 사이트: https://entitycode.com/#featured-content

<br />

##### Vs Code 설정

- Empty tag 기본으로 닫기
  ![](https://velog.velcdn.com/images/hjb0304/post/459717e4-06af-4c95-8cfb-1f2d949f216e/image.PNG)

1. Ctrl+P를 눌러 탐색기를 연 후 **emmet**을 검색해 나온 창에서 Edit in settings.json 파일을 클릭해 연다.

```
"emmet.syntaxProfiles": {
"html": "xhtml"
}
```

2. "emmet.syntaxProfiles"를 찾아 "html": "xhtml" 코드를 추가한다.
   <br />

- 문서의 기본 language 설정 변경
  ![](https://velog.velcdn.com/images/hjb0304/post/d1e554c7-a982-4d70-b8c4-ba21f61cdd3a/image.PNG)
  위와 같이 탐색기에 **emmet**을 검색해 나온 창에서 Emmet: Variables를 찾아 item에 lang / ko-KR을 추가한다.
  <br />
- Prettier Extension 설정
  ![](https://velog.velcdn.com/images/hjb0304/post/6f8d67da-1a4c-4172-934f-d2e6315b0a7f/image.PNG)
  탐색기에 **format**을 검색해 나온 창에서 위 이미지처럼 설정을 변경해 Prettier를 기본 포맷터로 만들고 저장 시 포맷이 이루어지도록 한다.

<br />

##### 참고 사이트

> - https://web.dev/learn/html

- https://developer.mozilla.org/ko/docs/Learn_web_development/Core/Structuring_content

<br />

#### HTML 제목

> 제목을 표시하는 태그. 숫자가 작을수록 높은 수준의 제목을 의미하며 숫자 순서대로 사용해야 한다.

```
<h1>제목</h1>
<h2>제목</h2>
```

#### HTML 문단

> 문단을 표시하는 태그

```
<p>문단</p>
```

#### HTML 목록

> 비순차 목록과 순차 목록을 표시하는 태그

```
/// 비순차 목록
<ul>
  <li>항목1</li>
  <li>항목2</li>
</ul>

/// 순차 목록
<ol>
  <li>항목1</li>
  <li>항목2</li>
</ol>
```

#### HTML 이미지

##### img

> 이미지를 포함하는 기본 태그

```
<img
src="/src/assets/food/icecream.webp"
alt="밴앤제리스 파인트 아이스크림"
/>
```

- `src` 이미지 경로를 지정하는 속성
- `alt` 이미지를 설명하는 속성으로 웹접근성 관점에서 정확하게 적어둬야 함. 맥락에 따라 설명이 달라짐
- `width, height` 이미지의 너비와 높이를 지정하는 속성. 이미지의 자리를 미리 잡아두기 때문에 성능 면에서 효과적임
  [참고 블로그](https://junglast.com/blog/img-width-height-attribute)
- `loading` 브라우저가 이미지를 불러올 때 사용할 방식을 지정함
  `loading="lazy"` 지연 로딩. 이미지가 뷰포트의 일정 거리 안으로 들어와야 불러옴. 성능 향상에 효과적임
  <br>

##### svg

> 벡터 이미지를 설명하기 위한 태그

- `<title>` svg 요소 안에서 사용하며 img의 alt 역할을 하는 요소.
  <br>

##### figure

> 독립적인 콘텐츠를 표현함. figcaption 요소를 사용해 설명을 붙일 수 있음

```
<figure>
 <img></img>
 <figcaption></figcaption>
</figure>
```

이런 구조로 이미지를 감싸고 이미지에 대한 설명을 붙일 수 있다.
<br>

##### 참고 사이트

> https://developer.mozilla.org/ko/docs/Web/HTML/Element

#### HTML 하이퍼링크

##### a(앵커)

> href 특성을 통해 다른 페이지나 같은 페이지의 어느 위치, 파일, 이메일 주소와 그 외 다른 **URL로 연결**할 수 있는 **하이퍼링크**를 만드는 요소

<br>

- `href` 하이퍼 링크가 가리키는 URL

```
<a href="https://www.naver.com">네이버</a>
```

<br>

- `target` 링크할 URL을 표시할 위치. target="\_blank" 설정 시 URL이 새 창으로 열림

```
<a href="https://www.naver.com" target="_blank">네이버</a>
```

<br>

- `rel` 링크 유형 속성 -`noopener`: 링크 클릭 시 브라우저 컨텍스트 권한 없이 열림. 신뢰할 수 없는 링크를 열 때 유용함 -`noreferrer`: 링크 클릭 시 referrer header를 생략하고 참조자 정보를 유출하지 않게 한다.
  => target="\_blank"와 함께 설정하는 것이 보안상 안전함

```
<a href="https://www.naver.com" target="_blank" rel="noopener noreferrer">네이버</a>
```

<br>

- `title` 하이퍼 링크의 툴팁을 설정하는 속성

```
<a href="https://www.naver.com" title="네이버 사이트로 이동(새창)">네이버</a>
```

<br>

- `download` 링크로 이동하는 대신 사용자에게 URL을 저장할 수 있게 하는 속성. 값 지정 시 파일 이름으로 설정됨

```
<a href="/src/assets/pdf//google-seo-guide-ko.pdf" download="google-seo-guide-ko.pdf">구글 SEO 가이드</a>
```

<br>

##### 참고 사이트

> https://developer.mozilla.org/ko/docs/Web/HTML/Element/a

<br>

### 🤔 느낀점

HTML은 나에게 아주 익숙한 존재라고 생각했지만, 생각보다 내가 모르고 놓치고 있던 부분도 많다는 걸 느끼게 되었다. 웹 접근성이나 보안 같은 부분을 조금 더 신경쓰면서 HTML을 사용해야겠다고 생각했다.

<br>

## 종합적인 느낀점
