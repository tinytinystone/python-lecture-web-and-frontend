# 4-04. Header(3)

- 실습 사이트 예제: https://python-lecture-example-1.netlify.com/
- 코드
  - 스타일링 전: https://github.com/tinytinystone/python-lecture-example/tree/4_04_1_header_3_styling_before
  - 스타일링 후: https://github.com/tinytinystone/python-lecture-example/tree/4_04_2_header_3_styling_after

배치가 되었으니, 나머지 스타일링 작업을 해 보겠습니다. 기본적으로 적용한 속성을 설명해 드리겠습니다.

먼저 CSS 내용이 많아질 것을 대비해서 보기 편하도록 미리 주석을 달아 놓았습니다.

먼저 body 영역에 line-height, 즉 줄간격 값을 1.6으로 기본적으로 부여해 두었습니다.

header 영역에 padding 값을 추가했습니다. padding-top에 15px, padding-bottom에 4px, 그리고 padding-right 와 -left에 0px을 적용했습니다. 이렇게 단축표기법으로 3개만 쓰게 되면 이 순서 대로 적용이 됩니다. 다음으로는 logo가 position: absolute 적용이 되어 있어서 부모인 container의 padding을 제대로 반영하지 못하는데요. 그래서 저는 logo에 padding-left 속성을 inherit으로 하여 container의 padding 속성을 상속받도록 했습니다. 이렇게 함으로써 padding-left의 20px이 적용되어 있음을 확인할 수 있습니다.

그 다음으로는 li 요소들의 font-weight 속성을 700으로 미리 줬습니다.

먼저 font-family의 값을 주겠습니다. font-family는 Roboto, Avenir 글꼴 두 개와 sans-serif 제네릭 폰트가 적용되어 있습니다. Roboto는 로컬 컴퓨터에 저장되어 있지 않은 경우가 많기 때문에, 웹 폰트라는 것을 사용해 보겠습니다.

웹 폰트란, 웹에서 언제나 글꼴을 얻을 수 있도록 하는 기능입니다. 사용하고자 하는 폰트를 업로드 한 후 서버로부터 해당 내용을 받을 수도 있고요, 오픈소스 타이포그라피를 사용하는 경우도 있습니다. 우리는 Google Fonts에서 오픈소스로 올라와 있는 Roboto font를 이용해 보겠습니다.

먼저 roboto를 검색하고 선택합니다. customize에 들어가서 우리가 사용할 폰트를 골라줍니다. italic과 100을 제외하고 모두 선택합니다. 그리고 난 뒤에 link 요소에 URL과 함께 적혀 있는 코드를 복사하여 head 영역 안에 붙여넣기 해줍니다. 이제부터 우리 사이트는 이용자의 컴퓨터에 Roboto 폰트가 없더라도 웹에서 다운 받아 사용할 수 있도록 지원하게 되었습니다.

다음으로는 user-agent style들을 초기화 해보겠습니다. h1 요소에는 margin이, ul 요소에는 padding과 margin이 기본값으로 들어가 있는데요. 이를 0으로 초기화 하겠습니다.

다음으로는 a 요소에 밑줄도 초기화 해보겠습니다. 이 밑줄과 관련한 속성은 text-decoration입니다. 예제에는 가장 아래의 footer 부분을 제외하고는 링크 요소들에도 밑줄이 없습니다. 따라서 저는 a 태그 셀렉터를 사용해서 text-decoration 속성의 값을 none으로 하겠습니다. 그 외에 a 요소의 color 속성은 위치에 따라 다른 값이라서, 이 부분은 초기화하지 않겠습니다. 대신, 각 영역에서 필요할 때마다 color 값을 지정해 주겠습니다.

navigation 영역의 a 요소의 color 속성값도 바꿔 볼까요? a 요소에 user agent style이 파란색으로 들어가 있는 것을 바꿔 보겠습니다. 예제를 보면, a 요소의 color는 white입니다.

나머지 font-size와 padding 속성도 값을 주겠습니다. 그 전에 한 가지 짚고 넘어갈 것이 있는데요. 각각의 li 사이에 여백을 지정한 적이 없는데 여백이 적용되어 있습니다. 사실, 이것은 HTML에서 포맷팅을 하면서 줄바꿈이 일어나는데 이 줄바꿈 때문에 일어나는 것입니다. 포맷팅을 하지 않을 수도 있겠지만, 그러면 확실히 보기가 어렵겠죠. 저는 ul 요소의 font-size를 0으로 함으로써 이 여백의 크기를 없애버리도록 하겠습니다. 그리고 다시 li 요소의 font-size를 1.3rem으로 하겠습니다.

마지막으로 사용자에 입장에서 보았을 때 a 요소를 클릭하기 좋도록 만드는 두 가지 방법을 알려 드리겠습니다. 하나는 마우스가 hover된 상태일 때는 흐린 연두색을 적용하는 것입니다. 마우스가 올라간 것과 아닌 것을 구분하기 좋겠죠. 다음은 a 요소에 적절한 padding을 주어서, 딱 글씨만 클릭해야 클릭되는 것이 아니고 사용자의 편의를 맞춰보도록 하겠습니다. padding은 상하좌우 네 방향으로 모두 10px씩 적용하겠습니다. 이를 위해서 a 요소의 display 값을 block으로 바꾸고, padding을 적용하도록 하겠습니다.

크롬으로 들어가서 확인해 보겠습니다.

그러고 보니 list-item 요소들이 모두 다 대문자인데요. 마크업에서 수정하지 않아도 대문자로 표기하는 방법이 있습니다. text-transform 속성에 uppercase 값을 주면 됩니다.

여기까지 header 영역 스타일링이 끝났습니다. 짧은 부분이지만 신경써야 할 부분이 꽤 많았습니다. 이번에는 첫번째 스타일링이라 꼼꼼하게 보았는데, 다음 부분부터는 조금 더 빠르게 설명하도록 하겠습니다.
