# 4-08. main-content 영역 스타일링

- 실습 사이트 예제: https://python-lecture-example-1.netlify.com/
- 코드
  - 스타일링 전: https://github.com/tinytinystone/python-lecture-example/tree/4_08_1_main_3_styling_before
  - 스타일링 후: https://github.com/tinytinystone/python-lecture-example/tree/4_08_2_main_3_styling_after

float 속성을 활용해 보겠습니다. 세 개 속성에 각각 float: left, float: left, float: right를 적용해 두겠습니다. 문제가 발생했습니다. 레이아웃이 전반적으로 깨진 것처럼 보입니다. 일단 h1 요소, meta 요소, nav 요소 다 제대로 일렬로 배치되어 있기는 합니다. 다만 header와 container가 사라져서 main 쪽의 요소들이 세 개 태그를 감싸면서 흐르는 모습입니다.

이 문제는 자식요소가 float가 되면 노멀 플로우에서 벗어나기 때문에 자신의 위치를 잃어버리기 때문에 생겨납니다. float된 자식요소를 부모요소가 그 높이를 인지할 수가 없는 것입니다. 이를 해결하기 위해서 사용하는 방법을 한 가지 말씀 드리겠습니다. clear 속성 기억 하시나요? float에 영향을 받지 않기 위해서는 clear 속성을 사용하여 해제해주면 된다고 말씀 드렸지요. 이를 부모요소의 가상요소에 적용하는 것입니다. 이를 위해서는 가상요소가 display 속성이 block이 되어야 하고, content 부분에 빈 문자열을 넣어주어야 합니다.

```css
.container::after {
  display: block;
  content: "";
  clear: both;
}
```

이를 통하여 부모요소가 원하는 높이를 찾은 것을 확인할 수 있습니다.

main-content 영역에, 전체적인 레이아웃과 폰트 속성 등을 미리 적용해 두었는데요. 아직 완성되지 않은 부분은 배경색 하늘색으로 지정해 두거나 주석을 달아 두었습니다. 한번 살펴보면서 완성해 보겠습니다.

cta 클래스가 중복되어 사용하고 있는데요. 공유하고 있는 속성은 별도의 룰셋으로 분리해 선언할 수 있도록 클래스를 나눠 보겠습니다. 그리고 원래 cta 였던 클래스 속성 값은 좀 더 구체적인 값으로 적어 주겠습니다.

```html
<a href="#" class="cta hero-cta"></a> <a href="#" class="cta main-cta"></a>
```

```css
/* CALL TO ACTION */
.cta {
  display: block;
  border-radius: 8px;
  font-size: 1.8rem;
  font-weight: 400;
  text-align: center;
}
.hero-cta {
  width: 300px;
  padding: 2rem 5rem;
  margin: 20px auto 60px;
  background: #44b78b;
  color: #fff;
}
.hero-cta:focus,
.hero-cta:hover,
.hero-cta:active {
  background-color: #51be95;
}
```

이제 main-content 내부에 있는 cta 요소 스타일링을 완성해 보겠습니다.

```css
.main-cta {
  color: #859d94;
  max-width: 500px;
  padding: 18px 27px;
  margin: 20px auto;
  border: 1px solid #cfe3dc;
  background: none;
}
.main-cta:focus,
.main-cta:hover,
.main-cta:active {
  border-color: #20aa76;
  color: #20aa76;
}
```

다음으로는,

요소와 요소 사이에 줄이 있는 두 가지 경우를 살펴보고 해결해 보겠습니다.

하나는 두 개의 section 요소 사이에 적절한 간격이 있고, 줄이 그려져 있는 것이고요. 다른 하나는 폼 요소에 p 요소 사이에 줄이 있는 상황입니다. 첫번째 상황은 border-bottom 속성을 사용해 보겠고, 두번째는 HTML에 hr 요소를 넣어서 이미 그려주었기 때문에 원하는 대로 색상과 두께를 넣어보도록 하겠습니다.

섹션요소 사이에 있는 가로줄은 첫 번째 섹션의 border-bottom 속성을 이용해서 넣을 수 있고, padding-bottom 값을 넣어 border와 콘텐트 사이 간격을 만들어 볼 수 있는데요. main-section 클래스 값이 동일하게 들어가 있는 경우, 첫번째 요소를 어떻게 선택할 수 있을까요? 저는 first-child라는 가상 클래스를 활용해 보도록 하겠습니다.

```css
.main-section:first-child {
  padding-bottom: 40px;
  border-bottom: 1px solid #cfe3dc;
}
```

first-child 클래스를 한번 더 사용해 보겠습니다. mailing 클래스 요소 사이에 여백을 주어야 하는 경우입니다. 이 경우에도 first-child를 사용하여 첫번째 요소에 margin-right를 줄 수 있습니다.

```css
.mailing:first-child {
  margin-right: 4%;
}
```

이제 앞서 이야기했던 hr 요소의 두께와 색상을 바꿔 보겠습니다. hr 요소도 마찬가지로 border 속성을 통해 가로줄을 표현하는데요. 기본값을 0으로 초기화한 후, border-top 속성에 적절한 값을 주어 원하는 색상을 표시할 수 있습니다.

```css
hr {
  border: 0;
  border-top: 1px solid #cfe3dc;
}
```

마지막으로 form 요소 내부의 label 요소, input 요소와 button 요소를 스타일링 해보겠습니다.

먼저 label 요소는 화면에 보이지는 않지만, 스크린 리더 등 필요한 경우 그 내용이 사용될 수 있도록 고려한 방식을 사용합니다. 단순하게 display: none 등으로 글씨를 없애버리는 것이 아니라, 숨기는 것임을 명심해 주세요.

```css
/* READABLE-HIDDEN */
.readable-hidden {
  position: absolute;
  width: 1px;
  height: 1px;
  overflow: hidden;
  margin: -1px;
  clip: rect(0, 0, 0, 0);
}
```

예제를 보게 되면, input 창의 테두리 색상과 크기가 기본값과는 차이가 있고, 또 버튼도 테두리와 배경색이 없는 상태에서 input 요소 안쪽에 위치해있음을 알 수 있습니다. 이 경우, 버튼에는 글씨를 띄워서 원하는 곳에 위치시키는 position 속성의 absolute 값을 적용해 보겠습니다.

position 속성을 바꾸기에 앞서, 먼저 input 요소와 button 요소의 스타일을 적용해 보겠습니다. 이 상태에서, button 요소의 상위요소에 position: relative를, 버튼요소에 position: absolute를 줍니다. top과 right 속성에 적절한 값을 주어 원하는 자리에 위치 시킵니다.

참고로 이 부분은 추후 강의에서 아이콘 폰트를 사용해 봉투 모양의 아이콘을 적용하는 것으로 바꿔볼 예정입니다.

이렇게 메인 콘텐트 영역의 스타일링이 완성 되었습니다.
