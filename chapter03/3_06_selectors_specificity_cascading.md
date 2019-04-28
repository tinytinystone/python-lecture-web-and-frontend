# 3-06. 다양한 셀렉터와 적용 우선순위, 상속과 캐스캐이딩

## [코드 예제(클릭)](https://codepen.io/tinystone/pen/mgvvYp)

선택자, 셀렉터는 특정 HTML 요소를 선택해서 스타일을 적용할 수 있도록 합니다. 모든 셀렉터를 한번에 다룰 수는 없습니다만 앞에서 배워본 태그 셀렉터, 클래스 셀렉터, ID 셀렉터를 비롯해 그 외에 빈번하게 사용되는 여러가지 셀렉터를 알아 보겠습니다. 그리고 이와 관련하여 CSS의 중요 개념인 캐스캐이딩도 살펴 보겠습니다.

```html
<div class="class-selector">클래스 선택자</div>
<p>태그 선택자</p>
<p id="id-selector">id 선택자</p>
```

가장 많이 사용하게 될 클래스 셀렉터부터 한번 살펴 보겠습니다. 클래스 셀렉터는 가장 범용적으로, 그리고 빈번하게 사용됩니다.

```html
<div class="region korea seoul"></div>
```

필요한 경우 여러 개의 클래스를 부여해줄 수도 있습니다. 공백으로 구분이 가능하고요. 이러면 요소들을 묶어주기에도 편리하겠죠.

```html
<a href="#">a 요소1</a>
<a href="#">a 요소2</a>
<ul class="region korea">
  <li>서울</li>
  <li>부산</li>
  <li>대구</li>
</ul>
<h2>일본</h2>
<ul class="region japan">
  <li>도쿄</li>
  <li>오사카</li>
  <li>쿄토</li>
</ul>
<h2>중국</h2>
<ul class="region china">
  <li>베이징</li>
  <li>칭다오</li>
</ul>
```

태그 선택자는 어떨 때 사용되냐 하면, 문서 전체의 태그 속성의 값을 바꿀 때 유용합니다.

```css
a {
  color: #000;
  text-decoration: none;
}
ul {
  list-style: none;
  margin: 0;
  padding: 0;
}
```

a 태그 색상은 기본값이 빨간색인데 이를 바꾼다거나, ul 태그에 앞에 붙는 동그라미 모양을 바꾸기 위해 list-style 속성을 바꾼다거나 할 때 사용 가능합니다. 하지만 태그 선택자를 너무 많이 사용하는 것은 좋지 않습니다. 유지보수성이 떨어질 수도 있기 때문입니다. 그러니 가급적이면 클래스 선택자를 사용하는 것이 좋습니다.

```css
#id-selector {
  background: orange;
  font-weight: 900;
}
```

ID 선택자는 선택자 앞에 #이 붙는 것이고요. id 속성값은 전체 문서에서 딱 하나의 요소에만 사용할 수 있습니다.

```html
<div class="class-selector selector">클래스 선택자</div>
<p>태그 선택자</p>
<p id="id-selector" class="selector">id 선택자</p>
```

```css
p {
  background: lightgrey;
  font-weight: 100;
}
.selector {
  background: lavender;
  font-weight: 400;
}
#id-selector {
  background: orange;
  border: 1px solid #696969;
  padding: 10px;
  font-weight: 900;
}
```

어떤 선택자들보다 Id 선택자가 구체적으로 해당 요소를 지칭하기 때문에, ID 선택자에서 속성과 값을 정의해준 경우에는 그 내용이 다른 선택자를 덮어쓰게 됩니다.

<!-- 선택자 적용 우선순위 -->

이러한 규칙을 선택자 적용 우선 순위라고 합니다. 구체성이 높은 선택자의 스타일이 적용되는 것입니다.

<!-- id 선택자 > 클래스 선택자 > 태그 선택자 -->

태그 선택자보다는 클래스 선택자가, 클래스 선택자보다는 ID 선택자가 더 구체적이라고 할 수 있고요. 그래서 먼저 적용이 됩니다.

id 선택자 > 클래스 선택자 > 태그 선택자

```html
<div class="container">
  <h1 class="title">각 국가의 지역들</h1>
  <p>동아시아 각 국가를 소개하고, 여러 지역에 대해서 알아보도록 하겠습니다.</p>
  <div class="region korea">
    <h2 class="region-title korea" id="my-country">한국</h2>
    <p>
      한국(韓國), 조선(朝鮮), 또는 코리아(Korea)는 동아시아에 위치한 지역 또는
      헌법상의 국가로, 현대사에서는 한반도의 대한민국과 조선민주주의인민공화국을
      통틀어 이르는 말이다. 근현대사에서 한국은 고종이 수립한 대한제국을 일컫는
      말이었다. 넓은 의미로 한국은 고조선 이후 한반도에서 설립된 여러 한민족의
      국가를 통칭하는 말이다. 한국의 역사를 한국사라고 한다.
    </p>
    <ul class="list">
      <li class="list-item">서울</li>
      <li class="list-item">
        경상도
        <ul>
          <li>대구</li>
          <li>부산</li>
        </ul>
      </li>
      <li class="list-item">
        <a
          href="https://www.google.com/maps/place/제주특별자치도"
          title="제주 지도"
          >제주</a
        >
      </li>
    </ul>
  </div>
  <div class="region japan">
    <h2 class="region-title japan">일본</h2>
    <p>
      일본국(일본어: 日本国 니혼코쿠[*][4], にっぽんこく 닛폰코쿠[*]), 약칭
      일본(日本, 일본어: 日本 니혼[*], にっぽん 닛폰[*])은 동아시아에 있는
      국가다. 국토는 태평양에 있는 일본 열도의 네 개의 섬으로 이루어진 홋카이도,
      혼슈, 시코쿠, 규슈를 중심으로 주변에 산재한 작은 섬으로 구성되어 있다. 총
      면적은 37만 7835 km2인데 이는 노르웨이(스발바르 제도와 얀마옌을 포함한
      경우)보다 작으며 독일보다 크다. 면적 순으로는 세계 61위다.[5]
    </p>
    <ul class="list">
      <li class="list-item">도쿄</li>
      <li class="list-item">
        오사카 구
        <ul>
          <li>오사카</li>
          <li>교토</li>
        </ul>
      </li>
      <li class="list-item">
        <a href="https://www.google.com/maps/place/일본+가가와현+다카마쓰시"
          >다카마쓰</a
        >
      </li>
    </ul>
  </div>
  <div class="region china">
    <h2 class="region-title china">중국</h2>
    <p>
      중국(중국어 간체자: 中国, 정체자: 中國, 병음: Zhōngguó 중궈[*], 영어:
      China 차이나[*])은 동아시아와 중앙아시아, 그리고 태평양 서부 연안의 도서
      지방을 포괄하는 지명이다. 1949년에 국공내전에서 승패가 갈리면서 두 국가로
      된 이래 현재까지 중화인민공화국과 중화민국, 즉 두 개의 중국이 존재하고
      있다. 그러나 각자는 하나의 중국을 주장하며 상대를 인정하지 않고 있다.
      유엔에서는 중화인민공화국만을 합법 국가로 인정하고 있다.
    </p>
    <ul class="list">
      <li class="list-item">베이징</li>
      <li class="list-item">칭다오</li>
    </ul>
  </div>
</div>
```

지금부터는 조금 더 구체적으로 여러 개의 요소를 선택하거나, 특정한 위치의 구체적인 요소를 선택하는 선택자 등에 대해서 익혀 보겠습니다.

여러 개의 요소를 한꺼번에 선택하는 것은 해당 선택자를 콤마로 구분해 나열하면 됩니다.

```css
h1,
h2 {
  color: blue;
  /* 모든 제목요소에 같은 디자인 속성을 지정하려면 이렇게 묶을 수 있습니다 */
}
.korea,
.japan,
.china {
  /* 클래스 선택자도 마찬가지로 묶어서 선택할 수 있습니다. */
}
```

HTML 문서의 계층구조를 이용해서 특정 요소에 접근하는 방법이나, HTML의 속성으로 접근하는 방법도 있습니다. 계층구조를 사용하는 경우 부모, 자식 관계에서 바로 아래 요소를 선택할 수도 있고, 하위요소 전체 중에서 선택하는 경우도 있습니다. '어떤 요소의 자손을 선택하라'는 선택자도 가능합니다.

```css
div.region p {
  /* region 클래스를 가지는 div 요소 하위에 포함된 모든 p 요소를 선택합니다.
   바로 위에 있는 부모 요소이든, 혹은 멀리 떨어져 있는 계층 구조이든 상관 없습니다. */
  background-color: orange;
}
.region .korea {
  /* region 클래스를 가지는 모든 요소의 하위에 포함된 korea 클래스 요소를 선택합니다. */
  background-color: orange;
}
.region.korea {
  /* 띄어쓰기가 있는 것과 없는 것은 완전히 다릅니다.
  클래스 선택자를 띄어쓰지 않고 작성하면 *두 개가 모두 포함되어 있어야* 적용된다는 의미입니다. */
  background-color: orange;
}
.container > p {
  /* module 클래스를 가진 요소의 바로 아래의 자식요소 중 h2 요소를 선택하라는 의미입니다.
  직계자손이라는 뜻에서 더욱 구체적입니다. */
  background-color: orange;
}
.container p {
  /* 위와 비교해 보세요. */
  background-color: orange;
}
a[title] {
  /* a 요소 중에서 title 속성이 있는 모든 요소를 선택 */
  background-color: orange;
}

a[href="https://www.google.com/maps/place/일본+가가와현+다카마쓰시"] {
  /* href 속성값이 "https://www.google.com/maps/place/일본+가가와현+다카마쓰시"와 일치하는 a 요소 */
  background-color: orange;
}
```

다음으로는 조금 특별한 선택자인 가상선택자를 다뤄볼 것인데요. 요소를 그냥 선택하는 것이 아니고, 요소의 일정 부분만 혹은 특정 상황에 처한 요소만을 선택합니다. 예를 들어서 어떤 요소에 마우스 버튼이 올라가 있을 때, 클릭되어 있을 때, 체크박스가 되어 있을 때, 첫 번째 자식요소일 때, 같은 타입 중에서 마지막 요소일 때 등의 상황에서 사용하는 가상클래스가 있습니다.

```css
a {
  /* 모든 a 요소 */
  background-color: orange;
}
a:hover,
a:active,
a:focus {
  /* a 요소에 마우스가 올라가있거나, 활성화되어 있거나, 키보드로 선택되어 있을 때 */
  background-color: orange;
}
li:first-child {
  /* li 요소 중 첫 번째 li 요소 */
  background-color: orange;
}
.container div:last-of-type {
  /* container 선택자 요소의 하위 div 요소 중 마지막 요소 */
  background-color: orange;
}
```

가상요소라는 개념도 있는데요. 가상요소는 존재하지 않는 요소를 존재하는 것처럼 부여하여 문서 특정 부분을 선택하는 것을 의미합니다. 콜론을 2개 붙여야 한다는 것도 가상클래스와는 다른 점입니다.

```css
h2::before {
  content: "👉 ";
  /* h2 요소 앞에 가상 요소를 넣어 '>'라는 콘텐트를 넣어줍니다. */
}
```

태그가 여러 개 사용되거나, 가상선택자 등의 선택자가 사용되었을 때는 구체성 우선 순위가 어떻게 될까요? 위에서 언급한 우선순위에서 조금 더 덧붙여서 규칙을 쉽게 이해하는 방법을 말씀 드리겠습니다.

id 선택자의 구체성 값을 100점, Class 선택자 및 가상클래스의 구체성 값은 10점, 태그 선택자 및 가상요소 구체성 값을 1점이라고 하겠습니다. 각각의 선택자가 사용된 횟수를 모두 더한 값이 큰 선택자가 우선적으로 적용됩니다.

그럼 위에 각 선택자들의 구체성 값을 한번 계산해 볼까요?

구체성 점수를 계산해주는 사이트가 있는데요. 한번 들어가 보겠습니다. https://specificity.keegan.st/

어떻게 보면 조금 이상합니다. 스타일시트에는 같은 요소를 가리키는 선택자를 여러 번 쓸 수 있는데 오류가 나기는커녕 덮어씌워진다고 표현하고 있습니다. 다른 프로그래밍 언어와는 이 점에서 차이가 있죠.

그것은 CSS의 C가 Cascading, 폭포라는 뜻을 가진다는 점을 생각해보아야 합니다.

CSS는 기본적으로 상위 태그의 스타일 속성을 상속 받습니다. 상속이란 상위 요소에 적용된 속성을 하위 요소가 물려받는 것을 의미하고, 대표적으로는 font나 color 같은 속성이 있습니다. 그 외에 position이나 box 관련 속성 등은 상속이 되지 않습니다. 상속이 된다고 생각하면 좀 이상하죠. 하여튼 상속이 가능하기 때문에 혼란스럽기도 하지만, 각 요소를 따로 지정해줄 필요가 없어 효율적이라고도 할 수 있습니다.

이렇게 CSS는 기본적으로 상위 태그의 스타일 속성을 상속받고, 하위 태그에 중복된 스타일 속성이 있다면 상위 태그의 내용을 덮어씁니다. 또, 셀렉터 구체성 점수나 언제 어느 위치에서 선언이 되었는지 등에 따라서 달라집니다. 스타일이 겹치는 부분을 잘 살펴봐야 하죠.

복잡한 것 같지만 한편으로는 스타일을 효율적이고도 합리적으로 적용하는 방법입니다.
