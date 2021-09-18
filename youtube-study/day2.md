# day2
## * 웹 서비스 동작 원리
### - 클라이언트와 서버의 요청과 응답으로 동작한다.
### - 서버를 실행시켜야 브라우저에 접근할 수 있다.
### - 클라이언트 : 서비스를 사용하는 프로그램 또는 컴퓨터 (ex.브라우저)
### - 서버 : 서비스를 제공하는 프로그램 또는 컴퓨터 (ex. 스프링부트)
### - localhost : 내 컴퓨터의 주소
## * MVC패턴을 활용한 템플릿 페이지 만들기
### - View Templates(화면 담당 기술) : 웹페이지 변수를 활용한다. 웹페이지가 하나의 틀을 만들고 변수를 삽입.
#### -> Controller : 처리과정 담당
#### -> Model : 데이터를 관리
### - MVC패턴 : 분야별 담당자를 나눈다. 화면,처리,데이터 분야를 각 담당자 별로 나누는 기법.
#### -> Controller : 클라이언트로 요청을 받음
#### -> View : 최종페이지를 만듬
#### -> Model : 최종페이지에 쓰일 데이터들을 View에 전달
### - Mustache : 뷰템블릿을 만드는 도구
### 1. 뷰 템블릿의 위치 : 파일명/gradle/src/main/resources/templates
### 2. 플러그인 설치 : Handlebars/Mustache 설치
### 3. 뷰 텝플릿 페이지 작성
#### 3-1. 뷰 페이지에 변수 삽입 : {{variable}} 
```
<body>
    <h1>{{username}}님, 반갑습니다!</h1>
</body>
```
### 4. 컨트롤러 만들기
#### 4-1. 컨트롤러 위치 : 파일명/gradle/src/main/java/com.example.파일명(기본패키지)에 파일 생성.
#### 4-2. 컨트롤러 선언 : @Controller
#### 4-3. 응답페이지 설정 : return "페이지명";
#### 4-4. URL 요청 연결 : @GetMapping
### 5. 모델 사용하기
```
package com.example.firstproject.controller;

import org.springframework.stereotype.Controller;
import org.springframework.ui.Model;
import org.springframework.web.bind.annotation.GetMapping;

@Controller
public class FirstController {

    @GetMapping("/hi")
    public String niceTOMeetYou(Model model) {
        model.addAttribute("username", "싱니");
        return "greetings"; //templates/뷰 페이지 이름.mustache -> 브라우저로 전송!
    }
}
```
