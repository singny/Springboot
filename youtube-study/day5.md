# day5
## * JPA를 활용하여, DB에 데이터를 생성하기.
### - 데이터베이스(DB) : 데이터를 관리하고 창고
### - JPA : 자바언어를 DB가 이애할 수 있게 해주며 데이터관리에 편리한 여러기능들까지 제공
#### -> Entity : 자바객체를 DB가 이해할 수 있게 잘 규격화된 데이터
#### -> Repository : Entitiy를 DB에게 전달하고 처리
### 1. DTO를 Entity로 변환
```
  @PostMapping("/articles/create")
  Article article = form.toEntity();
```
#### 1-1. Entity 작성
##### - Entity Package 생성 / 생성위치 : src/main/java/com.example.파일명
```
package com.example.firstproject.entity;

import javax.persistence.Column;
import javax.persistence.Entity;
import javax.persistence.GeneratedValue;
import javax.persistence.Id;

@Entity // DB가 해당 객체를 인식 가능!
public class Article {

    @Id // 대표값을 지정! Like a 주민등록번호
    @GeneratedValue // 1, 2, 3 .... 자동 생성 어노테이션!
    private Long id;

    @Column
    private String title;

    @Column
    private String content;


    public Article(Long id, String title, String content) {
        this.id = id;
        this.title = title;
        this.content = content;
    }

    @Override
    public String toString() {
        return "Article{" +
                "id=" + id +
                ", title='" + title + '\'' +
                ", content='" + content + '\'' +
                '}';
    }
}
```
#### 1-2. 변환 메소드 추가
##### - main/java/com.example.파일명/dto의 자바클래스(ArticleForm)에 추가
```
    public Article toEntity() {
        return new Article(null, title, content);
    }
```
### 3. 데이터 저장하기
```
    private ArticleRepository articleRepository;
    
    @PostMapping("/articles/create")
        // Repository에게 Entity를 DB안에 저장하게 함!
        Article saved = articleRepository.save(article);
```
#### 3-1. Repository 작성
##### - Repository Package 생성 / 생성위치 : src/main/java/com.example.파일명
##### - Repository Package에 interface생성
```
package com.example.firstproject.repository;

import com.example.firstproject.entity.Article;
import org.springframework.data.repository.CrudRepository;

public interface ArticleRepository extends CrudRepository<Article, Long> {
}
```
#### 3-2. 객체 주입하기(DI)
```
    @Autowired // 스프링 부트가 미리 생성해놓은 객체를 가져다가 자동 연결!
```
### 4. 데이터 저장 확인
```
    @PostMapping("/articles/create")
    public String createArticle(ArticleForm form) {
        System.out.println(form.toString());

        // 1. Dto를 변환! Entity!
        Article article = form.toEntity();
        System.out.println(article.toString());


        // 2. Repository에게 Entity를 DB안에 저장하게 함!
        Article saved = articleRepository.save(article);
        System.out.println(saved.toString());
        return "";
 ```
 ## 결과값
