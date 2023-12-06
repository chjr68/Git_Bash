# Git Bash GuideBook.
Git Bash 사용법을 기술합니다.

# 목차
0. Git Bash 사용하는 이유
1. 설치 방법
    * Git Bash 설치
2. 사용 방법
    * Git Bash 접근
3. Command
    * git config 
    * git init
    * git status
    * git branch
    * git add
    * git commit
    * > *<i class="fa fa-info-circle" aria-hidden="true"></i> 정보:* git commit 규칙
    * git remote
    * git push
    * git pull
    * git checkout
4. Trouble Shooting
    * warning: in the working copy of '파일 명', LF will be replaced by CRLF the next time Git touches it
    * src refspec main does not match any
    * Github 디렉토리에 화살표 표시 (폴더 클릭 불가능)
    

## 0. **Git Bash 사용하는 이유**
* Github에서 파일 업로드 시, 최대 100개 까지로 제한됨
* Git Bash 사용법만 숙지하고 있으면 소스코드/DOCS 등을 쉽게 개인 레포지토리에 관리 가능
* 버전관리 가능
## 1. **설치 방법**
    1-1. Git Bash 설치
* [git bash 공식 사이트](https://git-scm.com/) 접속하여 다운로드
* 약관 동의 및 default 설정 그대로 설치 진행
* 설치 중간 에디터 설정 확인 (자주 사용하는 에디터 > VSCode 등) <br>
![image](https://github.com/chjr68/Git_Bash/blob/main/images/1.GitBash_EditorSetting.png)
* 설치 완료
* 버전 확인 <br>
\# git version

## 2. **사용 방법**
    2-1. Git Bash 접근
* 로컬 PC에서 작업하는 소스가 있는 디렉토리로 이동
* 마우스 우 클릭 > "Open Git Bash here" <br>
![image](https://github.com/chjr68/Git_Bash/blob/main/images/1.GitBash_OpenGitBash.png)
## 3. **Command**
    3-1. 자주 쓰는 명령어 리스트, 사용 방법
* git config 
* git init
* git status
* git branch
* git add
* git commit
* > *<i class="fa fa-info-circle" aria-hidden="true"></i> 정보:* git commit 규칙
* git remote
* git push
* git pull
* git checkout -- {파일경로}
  * git status 의 Changes not staged for commit: 항목 삭제
* git clean -option
  * -f: Untracked 파일을 모두 삭제
  * -fd: 디렉토리 까지 모두 삭제 

## 4. **Trouble Shooting**
- 아래와 같이 표기 <br>

- <예시> <br>
4-X. ISSUE texts <br>
Comments <br>
Solutions <br>

```
4-1. warning: in the working copy of '파일 명', LF will be replaced by CRLF the next time Git touches it
----------------------------------------------------------------------------------------------------------------------------------
LF(Line-Feed)
- Mac, Linux (Unix 계열) 줄바꿈 문자열 = \n 
CR(Carriage-Return)
- Mac 초기 모델 줄바꿈 문자열 = \r
CRLF (Carriage-Return+Line-Feed)
- Windows, DOS 줄바꿈 문자열 = \r\n

플랫폼(OS)마다 줄바꿈을 바라보는 문자열이 다르기에 형상관리를 해주는 Git이 바라볼 땐 둘 중 어느 쪽을 선택할지 몰라 경고 메세지를 띄워준 것.
----------------------------------------------------------------------------------------------------------------------------------
autocrlf 사용
- check-in, check-out할 때 파일을 어떻게 처리할지 설정하는 변수
 Windows, DOS 명령어
 + 시스템 전체 적용하고 싶다면 --global 옵션 추가
 # git config --global core.autocrlf true 
- Linux, MAC 명령어
 # git config --global core.autocrlf input
```
```
4-2. Github 디렉토리에 화살표 표시 (폴더 클릭 불가능)
----------------------------------------------------------------------------------------------------------------------------------
* 해당 디렉토리에 .git 폴더가 생겨서 발생하는 문제 <br>
최상위 디렉토리에 이미 .git이라는 파일이 생성되었는데, 해당 디렉토리 에서도 push를 진행하는 과정에 .git 파일이 생겨서 발생하는 오류
----------------------------------------------------------------------------------------------------------------------------------
1. 위 문제가 발생하는 디렉토리에서 .git 파일을 제거
# ls -al
# rm -rf .git
2. 스테이지에 존재하는 파일 제거
# git rm --cached . -rf
3. add - commit - push 진행
# git add .
# git commit -m "texts"
# git push origin
```
```
4-3. src refspec main does not match any
----------------------------------------------------------------------------------------------------------------------------------
pull 명령어 없이 push 할 경우, 기존 내용 삭제 될 수 있기 때문
----------------------------------------------------------------------------------------------------------------------------------

```


# BUGS
Please report bugs to me

# AUTHOR

Kim JiHwan, <chjr68@naver.com>

