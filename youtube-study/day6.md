# day6
## * 저장된 데이터를 직접 DB에서 확인하기
### - 테이블의 구조
#### -> 테이블 : DB에 저장된 데이터가 관리되는 틀, 행과 열로 구성.
### - SQL과 CRUD
#### -> insert : Create
#### -> select : Read
#### -> update : Update
#### -> delect : Delect
### 1. H2 DB 접속 설정
#### - src/main/resources/application.properties에 작성
```
# h2 DB, 웹 콘솔 접근 허용
spring.h2.console.enabled=true
```
### 2. H2 DB 접속
#### - localhost:8080/h2-console로 접속
#### - jdbc url주소를 intelliJ에서 찾아서 입력
### 3. 테이블 구조 확인
![image](https://user-images.githubusercontent.com/89372116/134159431-057037f6-d283-4f42-975e-fe287e4743fb.png)
### 4. SELECT 데이터 조회
```
select * from article;
```
![image](https://user-images.githubusercontent.com/89372116/134159594-26d0eccb-6244-4356-8932-9b11b630d57f.png)
#### 5. INSERT 데이터 생성
```
insert into article(id, title, content) values (3, '스프링부트', '6일차');
```
![image](https://user-images.githubusercontent.com/89372116/134159936-a2fac746-fdb9-4be8-b9d8-c9ebc015ed49.png)
