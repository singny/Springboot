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

## * 롬복을 활용하여, 기존 코드를 Refactoring하기
### - Lombok : 코드를 간소화 시켜주는 라이브러리
### - Lombok의 기능
#### -> 여러 필수코드의 반복을 최소화
#### -> 로깅 기능을 통해 Printin 또한 개선 (Refactoring)
### - Refactoring : 코드의 구조 또는 성능을 개선하는 작업
### - Logging : 프로그램의 수행과정을 기록으로 남기는 것.
### 1. 롬복 라이브러리 추가
#### - build.gradle의 dependencies에 코드 추가
```
	// 롬복 추가!
	compileOnly 'org.projectlombok:lombok'
	annotationProcessor 'org.projectlombok:lombok'
```
### 2. 롬복 플러그인 설치
#### - Lombok 플러그인 설치 후 Enable annotation processing 클릭
### 3. DTO 리팩토링
#### - 기존 코드를 지우고 @ALLARGConstructor과 @ToString 추가
##### -> 기존코드
```
//    public ArticleForm(String title, String content) {
//        this.title = title;
//        this.content = content;
//    }

//    @Override
//    public String toString() {
//        return "ArticleForm{" +
//                "title='" + title + '\'' +
//                ", content='" + content + '\'' +
//                '}';
//    }
```
### 4. Entity 리팩토링
#### - 기존 코드를 지우고 @ALLARGConstructor과 @ToString 추가
##### -> 기존 코드
```
//    public Article(Long id, String title, String content) {
//        this.id = id;
//        this.title = title;
//        this.content = content;
//    }

//    @Override
//    public String toString() {
//        return "Article{" +
//                "id=" + id +
//                ", title='" + title + '\'' +
//                ", content='" + content + '\'' +
//                '}';
//    }
```
### 5. 로그 남기기
#### 5-1. 어노테이션 추가
```
@Slf4j // 로깅을 위한 골뱅이(어노테이션)
```
#### 5-2. 기존 println코드 삭제
```
//        System.out.println(form.toString()); -> 로깅기능으로 대체!
```
#### 5-3. 로깅코드 추가
```
        log.info(form.toString());
```
#### 5-4. 로그 결과
![image](https://user-images.githubusercontent.com/89372116/134169755-75d12f0f-aaf8-4e94-9ccd-d8c8c1af8166.png)
