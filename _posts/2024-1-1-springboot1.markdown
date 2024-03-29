---
layout: post
title: "[자바 백엔드] 1장 스프링 부트 시작하기"
date: 2024-1-1 22:40
category: "Spring-Boot"
toc: true
toc_sticky: true
---
## 1장 스프링 부트 시작하기
[자바 백엔드] *태그는 '코딩 자율학습 스프링 부트 3 자바 백엔드 개발 입문'을 읽으며 정리하는 내용이다.*

### 1.1 스프링 부트란
스프링 부트란, 웹 프로그램을 더 쉽게 만들기 위한 프레임워크인 스프링에 사용되는 도구이다. 스프링에서 개발 환경 설정을 간소화하여 사용자가 직접 라이브러리를 연동하지 않아도 되도록 했고, 웹 애플리케이션 서버(WAS)인 Tomcat을 내장시켜 배포가 간편하도록 하였다. 

### 1.2 스프링 부트 개발 환경 설정하기
1. JDK 17과 intelliJ를 설치한다. 
2. 스프링 부트 프로젝트를 만든다. [스프링 이니셜라이즈](https://start.spring.io)에서 간단하게 프로젝트 설정을 할 수 있다. 
대부분 기본값으로 둔 뒤 Java의 버전(17)만 잘 확인하자.  
Project Metadata에서 Artifact는 프로젝트 이름을 설정하는 부분이다. 이를 원하는 이름(firstproject)로 설정하고 Dependencies를 설정한다.  
추가할 의존성은 다음과 같다. 
    - Spring Web  
    - H2 Database  
: 자바로 작성된 관계형 데이터베이스 관리 시스템
    - Mustache  
: 화면을 만들기 위한 템플릿 엔진
    - Spring Data JPA  
: JPA를 편리하게 사용할 수 있는 기술  

    위 설정을 다 마친 뒤 파일을 다운로드하고 압축을 푼다. 

3. 인텔리제이에서 해당 폴더를 열고, scr>main>java>com.example.firstproject 경로에서 Firstproject 파일을 실행한다. 터미널에 "tomcat started on port(s): 8080", "started FirstprojectApplication in ..." 라는 메시지가 있다면 서버가 로컬의 8080 포트에서 실행되었다는 것이다.   
이를 확인하기 위해 웹 브라우저에서 "localhost:8080" 주소로 접속해 서버가 실행된 것을 볼 수 있다. 
4. 정적 파일을 추가해 서버에서 요청해 보자. src>main>resources>static 경로가 기본적인 정적 파일이 위치하는 곳이므로, 해당 경로에 간단한 html 파일을 추가하자. 경로에 hello.html 파일을 추가하고 서버를 껐다가 다시 실행한 뒤, "localhost:8080/static/hello.html" 주소로 접속하면 작성한 html 파일을 볼 수 있다. 

### 1.3 웹 서비스의 동작 원리 이해하기
위에서 설명한 대로 웹 서비스는 서버를 실행해야만 웹 브라우저를 통해 접근할 수 있다. 위에서 실습해 본 스프링부트 프로젝트는 톰캣 웹 서버에 담겨 로컬의 8080 포트에서 실행되게 된다. 해당 서버를 실행하면 static 경로 안에 작성해 둔 정적 파일에 접근할 수 있다. 