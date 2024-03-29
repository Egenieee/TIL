# .gitignore

### 🤷🏻‍♀️️`.gitignore` 파일이 모죠? 
* 로컬 저장소에서 작업한 파일 중 업로드하고 싶은 파일만을 올리고 싶을 때 사용할 수 있는 일종의 관리 파일이라고 할 수 있다. 
* Git은 gitignore에 정의한 파일들은 tracking하지 않는다. 

<br>

### 👩🏻‍💻 어떻게 사용할 수 있죠?
* 일단 `.gitignore` 파일은 프로젝트 안에서 최상위 위치에 존재해야 한다.
* 디렉토리를 확인한 뒤에 IDE 환경에서 파일을 생성하거나 메모장으로 작성해서 파일명을 `.gitignore` 로 변경해주면 된다. 생성하는 방법은 내키는대로.
* 생성한 `.gitignore` 파일을 연 뒤에 tracking하지 않을 파일 이름을 다음과 같은 문법을 사용하여 정의한다.
  * `#` : `#` 으로 시작하면 주석 역할을 한다. 
  * `/` : 디렉토리 구분자로 사용된다. 
  * `*` : `/` 를 제외한 모든 문자열과 매칭된다. 
  * `!` : `!` 로 시작하는 라인은 무시되지 않는다. 
* 파일을 정의한 후에 add, commit 그리고 push 해준다.

<br>

### 💻 파일 작성 예시
```gitignore

# .iml 확장자를 가진 파일 무시
*.iml

# genieee.iml 파일은 무시하지 않음 
!egnieee.iml

# 현재 디렉토리에 있는 egenieee.java는 무시되지만,
# 하위 다른 디렉토리에 있는 egenieee.java 파일은 무시되지 않음
/egnieee.java

# out/ 디렉토리에 있는 모든 파일 무시
out/

# src/ 하위 .iml 파일만 무시
src/*.iml

# src/ 하위 모든 디렉토리에 존재하는 .iml 파일 무시 
src/**/*.iml

# 현재 디렉토리 포함, 그 하위 디렉토리에 존재하는 모든 .iml 파일 무시 
/**/*.iml


```

<br>

### 🤦🏻‍♀️ 파일이 적용되지 않을 경우
만약 프로젝트 작업 이후에 gitignore 파일을 정의했다면, git은 원래대로 그 파일들을 추적하게 되므로, 이 때는 이미 버전 관리가 되고 있는 파일들을 수동으로 제외시켜주어야 한다.

```shell
// Repository의 cache를 모두 삭제한다.
git rm -r --cached .

// .gitignore 파일에 정의한 목롤들을 제외한 나머지 파일들을 git이 track하도록 한다.
git add .

git commit -m "set untracked files"
```

#### git rm에 대해서
* `git rm -r [filename]` : 원격 저장소와 로컬 저장소에 있는 파일을 삭제한다 (조심해야 됨. 다 날라간다 어흥..)
* `git rm -r --cached [filename]` : 원격 저장소에 있는 파일은 삭제하고, 로컬 저장소에 있는건 그대로 둔다.
* `-r` : 하위 디렉토리를 포함하여 모든 내용을 삭제한다.

<br>

### 💡 자동으로 `.gitignore` 파일을 만들어주는 사이트가 있다?!
* 자신의 개발 환경이나 사용하는 언어를 입력하면 자동으로 `gitignore` 파일을 생성해주는 사이트 :
  [gitignore.io](https://www.toptal.com/developers/gitignore)