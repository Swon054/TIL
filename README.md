# WILT
What I learn today 
>매일 배운 거 기록

## 2022-09-13
### RPA 1기 웹 프로그래밍 기획과 기본
#### 리눅스 커맨드라인 기초
-`pwd` : print working directory의 약자. 현재 작업 경로를 알려줌

-`cd` : change directory의 약자. 작업 경로 변경을 위한 명령어
  - 절대 경로는 /로 시작함
  - 상위 경로는 ..로 나타냄
  - 특정 hint 철자와 tab을 조합하면 경로 내 폴더 or 파일 이름 자동 완성
  
-`ls` : list의 약자. 현재 작업 경로에 있는 파일이나 디렉터리를 출력해주는 명령어
  ex) ls, ls -a, ls -l, ls -al 와 같이 사용하면 됨.
-`history` : 과거에 쳤던 명령어 리스트를 보여준다
  - 123번째 명령어를 보고 싶으면 `!123`를 친다.
  - 기록을 지우고 싶다면 뒤에 `-c`를 붙이면 모두 삭제, 특정 행만 지우고 싶다면`-d` + `행 번호`를 입력한다 
  
*추가로 알고 있으면 좋은 것들
  - `touch` : 폴더 or 파일을 만들어버림
  - `cat` : 파일 전체 내용을 불러온다. 아직까진 txt 파일만 테스트 해봄
  - `less` : txt 파일 내용을 나눠서 전체화면으로 불러와준다. a와 b키를 사용해서 앞, 뒤 페이지 이동가능. q키로 종료가능.
  - `mkdir` : make directory의 약자. 디렉토리 경로를 만들어주는 명령어.
  - `방향키` : 위로 누르면 바로 전에 썼던 명령어를 불러온다.
  - `ctrl` + `A` or `E` : 현재 작성 중인 명령어의 앞(A) 또는 끝(E)으로 텍스트 커서를 이동시킨다. `C`는 현재 명령어 입력을 취소하고 줄바꿈한다.
  - 참고 자료  [https://opentutorials.org/course/730/4561](https://www.git-tower.com/learn/git/ebook/en/command-line/appendix/command-line-101#:~:text=You%20can%20easily%20remember%20this,for%20%22change%20directory%22)
#### vim 사용법
  - 명령 모드와 입력 모드
    - vim 에디터를 열 때 : 명령어 `vim`로 진입함
    
    - 명령 모드에서는 입력이 불가능하다
    
    - 입력을 하려면 입력 모드로 바꿔야 한다.
      - 키보드에서 `i`를 누른다.
      
    - 입력이 끝난 후 `esc`
      사용 가능한 명령어
      - 저장 시 `:w`
      - 종료 시 `:q`
      - 저장 종료 시 `:wq`
    - 참고 자료 [링크](https://opentutorials.org/course/730/4561)
  - 비정상적으로 종료 시 해결 방법
    - vim이 비정상 종료되었을 때 `swp`파일이 생성됨.
      - ATTENTION 문구가 뜨는 경우
        1. 두 프로세스, 두 사람이 동시에 한 파일을 수정하는 경우
        2. crash가 나서 vim이 비정상적으로 닫힌 경우
    - 기존에 입력했던 내용을 복구하고 싶을 때는 `vim -r 파일명`을 입력하거나 Recovery모드로 진입
    - 정상 종료 후, `swp`파일 삭제
      -`rm .789.txt.swp` <-- `rm` 명령어는 remove 약자
#### 마크다운 문법
- 링크 추가

* 외부링크
```
사용문법: [Title](link)
적용예: [Google](https://google.com, "google link")
```
Link: [Google](https://google.com, "google link")


#### 버전 관리 시스템과 git


##### 버전 관리 시스템을 사용하는 이유


##### 커밋
- 커밋은 논리적 변경이 있을 때 만듦
- 가능하면 커밋 크기가 작을수록 좋음
###### 커밋 이력 보기
```
git log
```
##### 리포지토리
- 정의 : 여러 파일을 하나로 모은 컬렉션
- 일반 폴더와 리포지토리 차이 : .git 폴더의 유무
* 22-09-20 오류 발생 : Github 갱신 후 클론을 생성하지 않아서 fatal 에러 발생
* 해결 방법 : Github 클론을 갱신한 뒤, 다시 시도.
* 22-09-20 2번째 오류 발생 : 이슈 번호 표시((#?)) 안됨
* 해결 방법 : Github에서 먼저 이슈 생성 후 입력하면 됨.
## 2022-09-20
### 저장소 상태 파악하기

#### 브랜치

- 정의 : A branch in Git is simply a lightweight movable pointer to one of these commits
- 브랜치는 특정한 목표를 가지고 코드를 수정할 때 주로 만듦.
  - 이슈 하나당 브랜치 하나를 *주로 만듦.
  - *사람마다 다르지만, 협업할 때는 무조건 만든다.
* 참고 : JIRA에서는 한 작업이 Epic, 하위 작업을 Task 이런 식으로 만들 수 있다.

##### 명령어 
1. 브랜치 목록 보기
- `git branch`
2. 브랜치 생성하기
- `git branch` + `fileName`
3. 특정 브랜치로 이동하기
- `git checkout` or `git switch`

