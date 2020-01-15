---
layout: post
title: "[Blog] Minimal Mistakes 폰트 변경하기"
tags: Blog Jekyll
description: "각 테마에 폰트 변경을 위해서는 짬밥이 필요"
---

![](https://cdn.pixabay.com/photo/2017/05/30/03/58/blog-2355684_1280.jpg)

# 폰트 변경
---

**지킬 (Jekyll)을 이용한 .github.io 블로그 만들기** 까지는 구글링을 통해 어렵지 않게 해결하였다.
그러나 기본 테마가 별로라, [Jekyll Theme](http://jekyllthemes.org/) 사이트에서 구경좀 하다가
원하던 테마가 없어 다시 구글링...

구글신께서는 "니가 원하는 테마는 Minimal Mistakes임" 이라고 알려주셨다.
소프트웨어 전공자가 아닌지라 커스터마이징 하는데 애를 먹었지만, 
[Minimal Mistakes의 공식 블로그](https://mmistakes.github.io/minimal-mistakes/docs/stylesheets/) 에 나온데로 하니까 잘 적용된다.

현재는 해당 테마를 사용하고 있지는 않지만 지킬 블로그를 2주 정도 운영하면서 폰트 변경 혹은 커스터마이징을 원하는 유저를 위해 포스트 하단에 대략적인 팁을 남긴다.

---

## 1. 구글 폰트에서 원하는 폰트 찾기


[구글 폰트](https://fonts.google.com/?subset=korean)에서 원하는 폰트 선정


![](http://www.newsian.co.kr/news/photo/201809/32584_9074_824.jpg)

`Nanum Serif KR` 폰트로 선택했다.

---

## 2. 아래 2개의 파일 수정

- 'includes/head/custom.html'
- '_sass/minimal_mistakes/_variables.scss'

위 두 파일에서 `Nanum Serif KR` 가 어떻게 들어갔는지 잘 보면 된다!

## 3. includes/head/custom.html 파일

```html
<link href="https://fonts.googleapis.com/css?family=Nanum+Serif+KR" rel="stylesheet" type="text/css">
```

파일에 위 문구 추가

## 4. _sass/minimal_mistakes/_variables.scss 파일

```scss
/* system typefaces */
$serif      : Georgia, Times, serif;
$sans-serif : "Nanum Serif KR", -apple-system, BlinkMacSystemFont, "Roboto", "Segoe UI", "Helvetica Neue", "Lucida Grande", Arial, sans-serif;
$monospace  : Monaco, Consolas, "Lucida Console", monospace;
```

파일의 위 부분 수정

# 커스터마이징 팁

## 테마 다운 시 파악해야 하는 폴더

> 아래는 대략적인 가이드로 모든 테마에 공통된 특성은 아님에 주의하자.

- asset: font, css, images (사이트 로고 및 사진 파일 등) 등이 담겨 있다.

- _sass: 매우 중요한 파트로 폰트, 사이즈, 색상 등의 정보가 해당 폴더에 담겨 있다.

- _layout: tag, category, archive 및 다양한 페이지 layout 정보들이 담겨 있다.

- _page: 네비게이션 바 (navigation)에서 로드 가능한 페이지가 저장된다.

- _include : 주로 head.html 파일에서 구글 폰트를 로드해야한다.

- _data: 네비게이션 바 (navigation)에 대한 메뉴 추가 및 링크 설정을 한다.

대부분의 테마들이 위와 같이 구성되는 편이며, 완벽한 커스터마이징을 위해서는 프론트엔드 공부가 필요한 것 같다.
