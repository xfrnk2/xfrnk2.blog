---
title: "Github의 잔디가 심어지지 않던 문제와 해결"
date: 2021-08-03T11:17:34+09:00
draft: false

categories: ['resolved problem']
tags: ['resolved problem']
author: "xfrnk2"
---

### 문제 발생 상황
+ 나의 깃허브 페이지에 접속해보니 지난 2일간 잔디가 심어지고 있지 않았고, 커밋&푸쉬는 모두 정상적으로 반영되고 있는 것이 확인되었다.
+ 아마도 약 사흘전 Github Desktop 설치 후 웹 호스팅 용도로의 다른 계정으로 접속해서, 로컬에서 두 계정이 사용되고 있으니 나중에 설정 된 계정으로 사용자가 지정되고 있는 것인가 싶었다.

### 구글링 후 찾은 해결방법
~~~
git config --global user.name 아이디 작성
git config --global user.email 이메일 주소 작성
~~~
+ cmd에서 위 방법대로 실행한 후 커밋&푸쉬를 해보니 정상 작동함이 확인되었다.
