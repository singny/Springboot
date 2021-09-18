# day3
## * 뷰템플릿 페이지에 header-footer 레이아웃 적용하기
### - 레이아웃 : 화면에 요소를 배치하는 것
### - header영역 : 사이트안내를 위한 navigation
### - footer영역 : 사이트의 정보
### 1. 스타터 템플릿 적용
#### - get.bootstrap.com에서 starter template 가져오기
### 2. 상단 navbar 추가
#### - get.bootstrap.com에서 navbar 가져오기
```
<!-- navigation -->
<nav class="navbar navbar-expand-lg navbar-light bg-light">
    <div class="container-fluid">
        <a class="navbar-brand" href="#">Navbar</a>
        <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
            <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarSupportedContent">
            <ul class="navbar-nav me-auto mb-2 mb-lg-0">
                <li class="nav-item">
                    <a class="nav-link active" aria-current="page" href="#">Home</a>
                </li>
                <li class="nav-item">
                    <a class="nav-link" href="#">Link</a>
                </li>
                <li class="nav-item dropdown">
                    <a class="nav-link dropdown-toggle" href="#" id="navbarDropdown" role="button" data-bs-toggle="dropdown" aria-expanded="false">
                        Dropdown
                    </a>
                    <ul class="dropdown-menu" aria-labelledby="navbarDropdown">
                        <li><a class="dropdown-item" href="#">Action</a></li>
                        <li><a class="dropdown-item" href="#">Another action</a></li>
                        <li><hr class="dropdown-divider"></li>
                        <li><a class="dropdown-item" href="#">Something else here</a></li>
                    </ul>
                </li>
                <li class="nav-item">
                    <a class="nav-link disabled">Disabled</a>
                </li>
            </ul>
            <form class="d-flex">
                <input class="form-control me-2" type="search" placeholder="Search" aria-label="Search">
                <button class="btn btn-outline-success" type="submit">Search</button>
            </form>
        </div>
    </div>
</nav>
```
### 3. 하단정보 넣기
```
<div class="mb-5 container-fluid">
    <hr>
    <p> CloudStudying <a href="#">Privacy</a> <a href="#">Terms</a> </p>
</div>
```
### 4. 레이아웃 템플릿 생성
#### - src/resources/templates 에 layouts Directory 생성
#### - header.mustache 와 footer.mustache 파일 생성
### 5. 레이아웃 템플릿 삽입
```
{{>layouts/header}}
{{>layouts/footer}}
```
## * 결과페이지
![image](https://user-images.githubusercontent.com/89372116/132950260-cf26bf81-bae6-476a-869b-92c6f850ef0f.png)
![image](https://user-images.githubusercontent.com/89372116/132950273-2e051480-7b30-4fdf-ad52-e3d251e3600c.png)
