---
layout: post
title: "[Productive] GitHub Clone 할 때 폴더 째 혹은 내용물만 가져오기"
tags: Productive Git
---

![](https://cdn.pixabay.com/photo/2014/07/15/23/36/github-394322_1280.png)

# git clone 의 두가지 방법
---

## 레포지토리 폴더 통째로 가져오기

```console
$>git clone repository
```

이렇게 하면 Repository이름의 폴더가 `git clone`을 실행한 `Path`로 복사된다.


## 레포지토리 내용물만 가져오기

```console
$>git clone repository .
```

이렇게 하면 현재 `Path`로 Repository 의 내용물만 복사된다.

점하나 찍었을 뿐인데...
