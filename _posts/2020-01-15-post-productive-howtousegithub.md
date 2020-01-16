---
layout: post
title: "[Git] GitHub 사용법 (for Linux)"
tags: Git
description: "깃허브는 분산 버전 관리 툴인 깃을 사용하는 프로젝트를 지원하는 웹호스팅 서비스이다. - 위키백과 -"
---

## .

### Overall Contents

---

1. https://github.com/ 에서 계정 만들기

2. 사이트에서 저장소 (리포지토리, repository) 만들기

3. 클라이언트 (리눅스) 에서 내 저장소와 연결 정보 만들기

4. 저장소에 파일 저장하기 (upload)

5. 저장소에서 파일 내려받기 (download)

6. 추가 사항!

## .

### 1. https://github.com/ 에서 계정 만들기  

---

-  [https://github.com/](https://github.com/) 

-  회원가입: Sign In - 로그인, Sign Up - 회원가입

## .

### 2. 사이트에서 저장소 (리포지토리, repository) 만들기

---

-  사이트 화면에서 Repositories 옆에 New 버튼 클릭

-  저장소 (repository) 이름 선정

![](https://i.ibb.co/yFDJwvk/1.png)

`/` 오른쪽 위치에 원하는 `저장소 이름`을 적어넣고, 맨 아래 `Create repository` 버튼 클릭

- 아래에 몇가지 옵션이 있는데 건드리지 말자.)

- Public: 공개 (아무나 볼수 있다, 무료)

- Private: 비공개 (1개 공짜, 그 이상은 유료)




## .

### 3. 클라이언트 (리눅스) 에서 내 저장소와 연결 정보 만들기

---

-  Git 설치 (Install)

```console
git
```

터미널에 `git` 입력 시 설치하라고 나오면

```console
sudo apt-get install git
```

커맨드를 통해 설치 할 수 있다.

-  Git 초기 설정 (환경 설정)

```console
git config --global user.name woongchoi84
git config --global user.email woongchoi84@gmail.com
git config --global --list
```
리눅스 입장에서는 내 깃허브 정보를 알리가 없다. 처음 한번 입력해주자!.

-  GitHub의 저장소와 동기화

```console
git init
git remote add origin https://github.com/woongchoi84/test
```

- git init : 실행한 폴더에 `.git` 폴더를 만든다. 이 안에 git에 필요한 정보들이 업데이트 된다.

- git remote  ~~ : https://github.com/`깃허브 아이디`/`저장소 이름`

>  [주의할 점]

`git init` 혹은 `git clone repo_url` 등의 명령어를 사용하는 경우 `.git` 폴더가 생기는데, 이게 하위 디렉토리 같은 곳에 있으면 문제가 된다.
뒤에서 설명할 `git push` 혹은 `git pull` 이 안되는 경우 리눅스 `tree` 명령어를 통해 불필요한 `.git` 폴더의 유무를 체크해보자!


## .

### 4. 저장소에 파일 저장하기 (upload)

---



```console
git add .
git commit -m "first commit"
git push -u origin master
```

`git add` : 저장소에 올릴 파일을 정하는 것 (`.`의 의미는 전체 파일)

`git commit` : 저장소에 올리는데 설명을 붙여주는 것 (귀찮지만 꼭 해야한다)

`git push` : 이 명령어를 통해 실제로 업로드


## .

### 5. 저장소에서 파일 내려받기 (download)

---

-  첫번째 방법: git clone

```console
git clone repo_url
```

이 명령어는 위에서 했던 과정없이 바로 수행 가능하며 단지 깃허브 저장소 (repo_url)에서 파일을 복사해온다.

-  유용한 팁 (., 점 유무에 주의)

	- `git clone repo_url .` : 저장소에 있는 파일을 현재 경로로 가져온다. 리눅스 명령어와 비교해보면 `cp -rf ../source_dir/* .`와 같은 동작이 수행된다. 

	- `git clone repo_url`   : 저장소 폴더 통째로 현재 경로로 가져온다. 즉, 저장소 이름의 폴더명이 현재 경로에 생성된다. 리눅스 명령어와 비교해보면 `cp -rf ../source_dir .`와 같은 동작이 수행된다. 


-  두번째 방법: git pull

이 명령어를 쓰게되는 상황은 다음과 같다. 

1. A씨는 출근해서 이것저것 코딩을 하고 개발한 코드를 `git push`를 통해 저장소에 업로드하였다.

2. 퇴근을 하고 일을 더하고 싶어진 A씨는 `git clone`을 통해 회사에서 개발한 코드를 집에 있는 컴퓨터로 복사한 후 추가적으로 코드를 업데이트 하였다.

3. 잠들기 전 집에서 개발한 코드를 `git push`를 통해 저장소에 업로드하였다.

4. 다음 날 출근한 A씨가 이어서 코딩을 하기 위해서는 무엇을 해야할까?

```console
git pull
```

작업 중인 경로에 가서 위 명령어를 치면 `.git` 폴더의 내용을 기반으로 저장소와 내 로컬 (리눅스) 간의 연결 정보를 파악하여 저장소에 있는 최신 코드로 내 로컬 파일들을 업데이트한다.

## .

### 6. 추가 사항!

---


-  추가 사항을 넣은 이유는 다음과 같은 상황 때문이다.

두괄식으로 요약하자면, 

1. 작업: 로컬에서 코드 개발
2. 업로드: 로컬 (리눅스) --  저장소
3. 다운로드: 저장소 --  로컬 (리눅스)

위의 1-2-3-1-2-3-1-2-3-... 순서가 어그러지면 문제가 발생한다.

아래는 발생할 수 있는 몇가지 케이스이다.

>  Case I

1. A씨는 출근해서 이것저것 코딩을 하고 개발한 코드를 `git push`를 통해 저장소에 업로드하였다.

2. 퇴근을 하고 일을 더하고 싶어진 A씨는 `git clone`을 통해 회사에서 개발한 코드를 집에 있는 컴퓨터로 복사한 후 추가적으로 코드를 업데이트 하였다.

3. 잠들기 전 집에서 개발한 코드를 깜빡하고 업로드 못하였다.

4. 다음 날 출근한 A씨가 깜빡하고 `git push`를 못한걸 기억하고 어쩔 수 없이 다시 중간서부터 코드를 이어서 짜나간다.

5. A씨는 퇴근 전 `git push`를 통해 저장소에 업로드하고 퇴근하였다.

6. 집에서 `git pull`을 하는 경우 어떻게 될까?

이 때, Merge가 필요하다고 하면서 뭔가 이상한 메시지를 뿌린다. 뒤죽 박죽이 되버린 것이다.

Git에 대해 초심자의 경우 그냥 새로 `git clone`을 통해 회사에서 마지막으로 개발한 코드와 Sync를 맞추자.

>  Case II

1. A씨는 출근해서 이것저것 코딩을 하고 개발한 코드를 `git push`를 통해 저장소에 업로드하였다.

2. 퇴근을 하고 일을 더하고 싶어진 A씨는 `git clone`을 통해 회사에서 개발한 코드를 집에 있는 컴퓨터로 복사한 후 추가적으로 코드를 업데이트 하였다.

3. 잠들기 전 집에서 개발한 코드를 `git push`를 통해 저장소에 업로드하였다.

4. 다음 날 출근한 A씨는 어제 집에서 짠 코드가 엉망이었음을 깨닫고 그냥 회사 컴퓨터에 남아있는 코드에서 이어서 작업을 하기로 한다.

5. 퇴근 전 `git push`를 하는 경우 어떻게 될까?

이 때도, Merge가 필요하다고 하면서 뭔가 이상한 메시지를 뿌린다.

Git에 대해 초심자의 경우,


```console
git push -u origin +master
```

master 앞에 `+` 기호를 넣어 강제로 로컬에 있는 자료를 저장소로 업로드 해버리자!.

다음에는 윈도우 설치 프로그램 기준 깃 사용법에 대해 포스팅 할 예정이다.

>  마지막 팁

필자의 경우 편의를 위해 아래와 같이 'alias' (단축키) 설정해두고 사용한다.

```sh
alias	gitpush='git add .; git commit -m "w/o comment"; git push -u origin +master;'
```
