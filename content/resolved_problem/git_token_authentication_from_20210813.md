---
title: "깃허브 토큰 인증 로그인 해결 - Support for password authentication was removed. Please use a personal access token instead 에러 해결"
date: 2021-08-15T11:17:34+09:00
draft: false

categories: ['resolved problem']
tags: ['resolved problem']
author: "xfrnk2"
---

### 문제 발생 상황
+ push를 했더니 아래와 같은 문구가 나왔다.
> remote: Support for password authentication was removed on August 13, 2021. Please use a personal access token instead. remote: Please see https://github.blog/2020-12-15-token-authentication-requirements-for-git-operations/ for more information. fatal: unable to access "..." : The requested URL returned error: 403
  
### 해결 방법

> 8월 13일을 기점으로 유저 이름과 비밀번호로 인증을 하던 형태에서, 개인 인증 토큰을 비밀번호 대신 사용해야 git에 접근할 수 있는 형태로 바뀌었다.
  
  
1. 들어간다 - https://github.com/settings/tokens
    
2. 이동한다 - github settings > Developer Settings > Personal Access Token
  
3. 버튼을 누른다 - Generate New Token
  
4. 사용 용도(Note), 기한(Expiration), 권한(Select Scopes)을 설정후 토큰을 생성해서 보관한다.
  
> 앞으로 유저 이름과 함께 이 토큰을 가지고 Git에 접근할 수 있다.

---
### Windows를 사용하는 경우
  
1. 이동한다 - 제어판 > 사용자 계정 > 자격 증명 관리자 > Windows 자격 증명 관리
  
2. `git:https://github.com` 의 Password를 앞에서 생성한 토큰으로 설정후 저장한다.
  
3. git에 접근할 수 있게 된다.
  
---
### Source Tree를 사용하는 경우
  
1. 이동한다 - 소스트리 저장소 메인 화면 우 상단의 설정   
2. 수정 버튼을 클릭한다 - 원격 탭(기본 탭)의 저장된 원격 주소(이와 같은 형태이다 : `https://github.com/username/repo.git`)를 수정   
3. 아래와 같은 형태로 수정한다.  
 `https://<생성된 토큰 붙여넣기>@github.com/username/repo.git`  
4. 정상적으로 Sourcetree를 사용할 수 있게 된다.  