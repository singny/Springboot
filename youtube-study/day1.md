# day1
## * spring boot란 ? 
### - 자바프로그램을 보다 쉽고 빠르게 만들게 하는 도구
### - 프로그램을 만들기 위한 레시피들이 존재하는데 원하는 레시피만 찾아서 사용한다.
## * 목표
### - spring boot를 위한 개발 환경 만들고 "hello world" 출력하기
### 1. JDK(8버전) ItelliJ IDEA 설치하기
### 2. spring initializr페이지를 열어서 프로젝트 생성하기
### 3. Project : Gradle Project, Language : Java, Artifact : firstproject1, Pakaging : Jar
### 4. Dependencies
#### 4-1. Spring Web : Spring MVC를 사용하여 RESTful을 포함한 웹을 구축. Apache Tomcat을 기본 포함 컨테이너로 사용한다.
#### 4-2. H2 Database : 작은 면적으로 JDBC API 및 R2DBC 액세스를 지원하는 빠른 인메모리 데이터베이스를 제공. 내장형 및 서버 모드와 브라우저 기반 콘솔 애플리케이션을 지원.
#### 4-3. Mustache : 논리가 없는 템플릿.
#### 4-4. Spring Data JPA : Spring Data alc Hivernate를 사용하여 Java Persistence API를 사용하여 SQL 저장소에 데이터를 유지한다.
### 5. ItelliJ를 통해 main/resources/static파일에 새로운 html파일 형성 및 RERUN
```
<body>
  <h1>hello world</h1>
</body>
```
### 6. 브라우저에 localhost:8080/hello.html 검색
## * 발생오류
### - JDK를 설치했음에도 불구하고 module jdk is not defined 오류로 인해 ItelliJ RUN이 동작하지 않았다.
### - cmd prompt창을 켜서 java -version을 통해 설치여부를 확인하고 ItelliJ를 다시 재실행해보니 해결되었다.
