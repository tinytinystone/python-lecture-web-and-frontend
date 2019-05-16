# 4-02. Header(1)

- 실습 사이트 예제: https://python-lecture-example-1.netlify.com/
- 코드: https://github.com/tinytinystone/python-lecture-example/tree/4_02_header_1_markup

그럼 헤더 영역의 html 구조를 한번 잡아 보도록 하겠습니다. 그 전에, 전체 구조를 한번 과제로 짜보시라 말씀 드렸는데요. 저와 비슷하게 잘 짜셨을까요?

그럼 다시 header로 돌아가서 진행을 해 보겠습니다. 여기 html 구조를 제가 한번 그림으로 그려 봤는데요.

![](./resources/header_html.png)

```html
<h1 class="logo">
  <img
    src="https://static.djangoproject.com/img/logo-django.42234b631760.svg"
    alt="Django"
  />
</h1>
<nav class="nav">
  <ul class="list">
    <li class="list-item"><a href="#">Overview</a></li>
    <li class="list-item"><a href="#">Download</a></li>
    <li class="list-item"><a href="#">Documentation</a></li>
    <li class="list-item"><a href="#">News</a></li>
    <li class="list-item"><a href="#">Community</a></li>
    <li class="list-item"><a href="#">Code</a></li>
    <li class="list-item"><a href="#">About</a></li>
    <li class="list-item"><a href="#">♥ Donate</a></li>
  </ul>
</nav>
```

가장 먼저 나오는 것이 h1, 제목요소입니다. 저는 로고라는 클래스 이름으로 h1 태그로 마크업을 해줄 것입니다. 이 사이트에서 가장 중요한 키워드가 django이고, 전체 사이트를 나타내는 부분이기 때문에 h1 요소로 마크업을 해줄 것입니다. 이 로고는 링크로 연결되어 있기 때문에 h1 요소 안쪽에는 a 요소를 사용하겠습니다.

그 옆에는 전체가 다 네비게이션 영역입니다. 네비게이션 영역은 nav라는 태그로 마크업할 수 있다고 말씀 드렸죠. 이 영역은 nav라는 태그를 이용해서 top-nav라는 클래스 이름을 적어줄 것입니다. 이런 네비게이션 메뉴를 만들 때 ul과 li 태그를 많이 활용한다고 말씀 드렸는데요. 그래서 내부에는 ul과 li로 마크업을 하겠습니다.

VS code에서 HTML 파일에 코드를 추가하겠습니다. emmet 단축키를 이용하면 빠르게 여러 태그를 자동완성 할 수 있습니다.
