# 4-03. Header(2)

- 실습 사이트 예제: https://python-lecture-example-1.netlify.com/
- 코드: https://github.com/tinytinystone/python-lecture-example/tree/4_03_header_2_layout

header 영역의 레이아웃을 HTML 요소와 CSS 속성을 통해 잡아 보겠습니다. 그 전에 전체 페이지 레이아웃을 개발자도구와 함께 살펴 보겠습니다. 지금 페이지는 content가 일정한 크기 내에 있고, 가운데에 위치해 있습니다. 브라우저 크기를 줄여보겠습니다. width가 일정 크기, 1060px에 도달하면 그 이하로는 크기가 줄어들지 않습니다. 반대로 1400px에 도달하면 그 이상 크기가 늘어나지 않습니다.

이를 위해서는 min-width 속성과 max-width 속성을 사용하면 됩니다. 저는 전체 크기가 1060px 이하가 되면 안되니까 body 요소에 최소 너비값인 min-width 속성에 1060px을 주겠습니다. 그리고 container라는 div 요소를 하나 생성할 건데요. header, main, footer 전체를 다 container로 덮으면 header와 footer 부분의 배경색을 칠할 수 있는 방법이 없겠죠. 그래서 저는 각 요소 안쪽에 div.container를 생성하고 max-width 속성에 1400px 값을 주겠습니다.

다음으로는 가운데 정렬을 하겠습니다. 가장 많이 사용하는 방법은 margin의 auto 값을 이용하는 것입니다. auto 값은 브라우저가 사용할 수 있는 적절한 마진 값을 선택하는 것을 의미합니다. 이 경우, 오른쪽과 왼쪽 마진에 auto 값을 주게 되면 브라우저 크기에 따라서 동일한 값을 양 쪽에 분배하게 됩니다. margin-left와 margin-right에 auto 값을 줄 수도 있지만, 이 김에 margin/padding/border에 동일하게 적용되는 단축표기법을 배워 보겠습니다. 순서가 동일합니다.

```css
.container {
  margin: 10px 20px 30px 40px; /* top-right-bottom-left 순 */
}
/*           10px
     -------------------
     |                 |
     |                 |
40px |                 | 30px
     |                 |
     |                 |
     ------------------- 
             30px
*/

.container {
  margin: 0 auto; /* top, bottom에 0, right, left에 auto */
}
/*            0
     -------------------
     |                 |
     |                 |
auto |                 | auto
     |                 |
     |                 |
     ------------------- 
              0
*/

.container {
  margin: 10px; /* top-right-bottom-left 순 */
}
/*           10px
     -------------------
     |                 |
     |                 |
10px |                 | 10px
     |                 |
     |                 |
     ------------------- 
             10px
*/
```

HTML 코드와 CSS 코드를 바꿔 주겠습니다.

```html
<div class="container">
  <!-- 중략 -->
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
  <!-- 중략 -->
</div>
```

```css
html {
  font-size: 10px;
}
body {
  min-width: 1060px;
  font-size: 1.8rem;
}
.container {
  margin: 0 auto;
  max-width: 1400px;
  padding: 0 4%;
}
```

body 태그의 min-width 값을 1060px, container는 max-width 값을 1400px로 적용해 두겠습니다. container에 배경색을 잠깐 칠해 놓겠습니다. 또, container에 margin: 0 auto 값을 주겠습니다. 우리가 의도한 대로 잘 동작하는 것을 확인할 수 있습니다. 세부적인 디자인을 위해서 양 쪽에 padding 값을 20px 주겠습니다.

그리고 바디 태그에 글씨 크기를 미리 지정을 해줘서 레이아웃이 혹시 흐트러지지 않도록 할 것입니다. 저는 앞에서 배운 폰트 사이즈를 픽셀로 html 고정을 하고 body에다가 1.8 rem을 적용합니다. 따로 글씨크기를 지정하지 않으면 글씨 크기는 18px이 되겠습니다. 중간중간에 필요할 때 아래에서 rem 단위를 사용할 수 있도록 하겠습니다

다시 돌아가 로고와 네비게이션을 배치해 보겠습니다. 저는 logo는 움직일 필요 없이 정확하게 그 위치에 자리해야 하므로, position: absolute를 주겠습니다. postion absolute가 적용된 요소는 부모요소 중, postion 값이 static이 아닌 가장 가까운 요소를 기준으로 한다고 말씀 드렸던 것 기억하시나요? 로고가 기준으로 해야 하는 부모 속성은 바로 위 요소인 container가 되겠죠. 저는 container에 position relative를 주도록 하겠습니다. position relative를 주더라도 normal flow는 변하지 않으므로 편하게 logo 영역만 자리를 맞춰주면 되겠습니다.

그리고, navigation bar는 오른쪽을 기준으로 정렬이 되어 있는 상태입니다. 그래서 저는 nav 요소에 text-align 속성에 right 값을 주어 오른쪽으로 정렬을 하겠습니다. 원하는 대로 오른쪽정렬이 잘 이뤄졌네요.

이제 몇 가지 작업을 더 해주겠습니다. h1과 ul 요소에 user agent style로 적용된 margin을 일단 0으로 초기화 해두겠습니다. 마지막으로는 ul요소와 li요소에 클래스 네이밍을 붙이고, li 요소를 일렬로 나란히 배치하기 위하여 display 속성을 inline-block으로 바꾸겠습니다.

```css
.logo {
  margin: 0;
}
.list {
  margin: 0;
}
.list-item {
  display: inline-block;
}
```

오늘 기억해야 할 내용은 max-width와 min-width, padding/margin/border의 단축표기법, 가운데 정렬하는 margin: 0 auto 기법,
