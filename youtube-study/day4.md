# day4
## * 폼데이터 주고받기 : 사용자로부터 폼 데이터를 받고, 이를 컨트롤러에서 확인하기.
### - 폼 데이터 : html요소인 form태그에 담긴 데이터
### - DTO : 폼데이터를 받는 객체
### - 게시물 작성 : 사용자의 입력이 db라는 데이터창고에 저장되는 과정
### 1. 입력폼 만들기
```
<form class="container" action="/create" method="post">
    <div class="mb-3">
        <label class="form-label">제목</label>
        <input type="text" class="form-control" name="title">
    </div>
    <div class="mb-3">
        <label class = "form-label">내용</label>
        <textarea class="form-control" rows="3" name="content"></textarea>
    </div>
    <button type="submit" class="btn-primary">Submit</button>
</form>
```
### 2. 컨트롤러 추가
```
    @GetMapping("/new")
    public String newArticleForm() {
        return "new";
    }
```
### 3. 폼 데이터 전송
### 4. 폼 데이터 받기
```
    @PostMapping("/create")
    public String createArticle(ArticleForm form) {
        System.out.println(form.toString());
        return "";
    }
``` 
### 5. DTO 작성하기
#### -> DTO객체 생성 위치 : src/java/com.example.파일명
```
package com.example.firstproject.dto;

public class ArticleForm {

    private String title;
    private String content;

    public ArticleForm(String title, String content) {
        this.title = title;
        this.content = content;
    }

    @Override
    public String toString() {
        return "ArticleForm{" +
                "title='" + title + '\'' +
                ", content='" + content + '\'' +
                '}';
    }
}
```
## * 결과값

![image](https://user-images.githubusercontent.com/89372116/132954662-4604526d-1164-4a60-9a98-f3df735dc87a.png)
![image](https://user-images.githubusercontent.com/89372116/132954690-a400f738-8ab5-4ece-ba9f-9dbdfa904bd2.png)
