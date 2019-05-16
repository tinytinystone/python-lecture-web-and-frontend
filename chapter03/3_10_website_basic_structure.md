# 3-10. 웹사이트 기본 구조

- 실습 사이트 예제: https://python-lecture-example-1.netlify.com/
- 코드: https://github.com/tinytinystone/python-lecture-example/tree/3_10_website_basic_structure

웹사이트의 기본적인 구조를 그려보는 시간을 가지겠습니다. 보이는 배치(디자인)에 따르는 것이 아니라 콘텐츠의 논리적 흐름에 따라 짜야 합니다.

먼저, 일반적인 웹사이트 구조를 살펴보고, 이에 따라 의미에 맞는 태그를 사용해 보도록 하겠습니다. 의미에 맞는 태그라는 용어를 시멘틱이라고 부르기도 합니다. 시멘틱한 사이트를 만들기 위하여 웹사이트 구조를 만드는 태그가 별도로 있습니다. mdn에 올라와 있는 사이트 예제를 먼저 보겠습니다.

![](https://mdn.mozillademos.org/files/12417/sample-website.png)

모든 사이트가 이런 식으로 생긴 것은 아니겠지만 대부분은 유사한 구조를 가지고 있습니다.

이 페이지의 각 부분을 부르는 이름을 먼저 알아보겠고, 이 부분을 마크업, 즉 논리적 구조를 표현하는 태그를 배워 보겠습니다.

가장 상단의 header는 페이지마다 반복되는 머리말 부분입니다. 주로 제목이나 로고, 짧은 소개말 등이 들어갑니다. header라는 태그를 사용할 수 있습니다.

navigation bar는 다른 페이지로 이동할 수 있는 메뉴 버튼이나 링크 등이 들어갑니다. header에 네비게이션 바가 포함되기도 합니다. 이 부분을 마크업하기 위해서는 nav라는 태그를 사용할 수 있습니다.

main 콘텐츠는 본문의 주요 콘텐츠 블럭입니다. main 태그를 사용할 수 있습니다. main 태그는 문서에서 한번만 사용해야 하는 점을 참고해 주세요.

side bar 영역은 기타 정보나 링크, 광고 등의 내용이 들어갑니다. navigation bar와도 유사할 수 있습니다. aside라는 태그를 사용할 수 있고, 주로 main 요소 내에 배치되는 경우가 많습니다.

footer 영역은 주소, 카피라이트, 연락처 정보 등이 포함됩니다. header 부분에 비해서는 중요도가 약간은 떨어지는 정보들이 들어간다고 생각하시면 됩니다. footer라는 태그를 주로 사용합니다.

우리가 만들려고 하는 실습 예제도 이렇게 구조를 미리 짜보도록 하겠습니다. 저는 djangoproject.com 이라는 장고 공식 사이트를 실습하기 좋도록 구조를 조금 바꿔 보았습니다. 앞으로는 이 예제를 보면서 실습해 나가겠습니다.

그럼, 이 예제를 한번 그려 보겠습니다.

```html
<header class="header">헤더</header>
<main class="main">
  <div class="hero-section">히어로 영역</div>
  <div class="main-content">메인 콘텐트</div>
  <div class="side-content">사이드 콘텐트</div>
</main>
<footer class="footer">푸터</footer>
```

기본적인 레이아웃만 먼저 CSS로 스타일링 해두고, 이제부터는 조금씩 완성해 나가면서 배워보도록 하겠습니다.
