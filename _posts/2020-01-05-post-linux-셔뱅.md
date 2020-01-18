---
layout: post
title: "셔뱅(shebang) 사용법"
tags: Linux Setup
description: "리눅스 사용시 꼭 기억해야하는 사항!"
---

![](https://cdn.pixabay.com/photo/2017/04/27/01/31/question-2264166_1280.png)

### 셔뱅(shebang)의 의미


운영체제 입장에서는 스크립트 파일이 어떤 문법으로 짜여진건지 모른다.

(예: 이게 파이썬 코드야, 쉘 코드야?)

이걸 알려주기위해 스크립트 파일 첫줄에

```sh
#! /bin/bash
```
와 같이 인터프리팅 정보를 주는것을 셔뱅이라 한다.


- [위키피디아](https://ko.wikipedia.org/wiki/%EC%85%94%EB%B1%85) 설명

> 셔뱅(shebang)은 해시 기호와 느낌표(#!)로 이루어진 문자 시퀀스로, 스크립트의 맨 처음에 온다. ... 이하 중략

### 스크립트 파일 사용 예제


특정 스크립트 파일을 파이썬 코드로 작성하였다고 가정하자.

이때 아래와 같이 두 가지 스크립트 파일 실행이 가능하다.


- 쌩으로 스크립트 파일 실행


```console
$>python script_file
```

이렇게 실행해도 되지만, 자주 사용하는 스크립트의 경우 아래가 훨~씬 편하다.


- 셔뱅 + 파일 실행

```console
$>which python
/usr/bin/python
```

`which` 명령어로 python 경로를 알아낸후 스크립트 파일 첫줄에

```console
#! /usr/bin/python
```

추가 후 

```console
$>chmod +x script_file
```

로 실행 권한 부여 후

```console
$>./script_file
```

이렇게 `'쩜+슬러쉬+파일명'`으로 실행가능하다.
