# 4-07. form

https://codepen.io/tinystone/pen/WWWwaz

form은 우리가 평소에 인터넷을 하면서 많이 보았던 요소입니다. 로그인할 때, 요소를 선택할 때, 검색할 때 등등 사용하던 요소들이 폼 요소입니다.

폼 요소는 웹사이트에서 서버 쪽으로 정보를 제출하기 위해, 혹은 브라우저 내부에서 사용하기 위해 사용됩니다. 사용자와 웹 사이트가 서로 상호작용하는 중요한 기술입니다.

```html
<form action="http://www.데이터보낼URL.co.kr" method="post">
  <label for="text">텍스트 필드</label>
  <input type="text" id="text" />

  <label for="checkbox">체크박스</label>
  <input type="checkbox" id="checkbox" />

  <label for="radio">라디오 버튼</label>
  <input type="radio" id="radio" />

  <label for="search">검색</label>
  <input type="search" id="search" />

  <button>전송 버튼</button>
</form>
```

한번 코드를 살펴 보겠습니다.

글을 입력할 수 있는 텍스트 필드나 버튼, 체크박스, 라디오 버튼 등이 모두 폼의 구성요소입니다. 또, 이러한 구성요소가 무엇인지를 설명하는 라벨이 있습니다.

여기 만들어야 하는 form은 이메일을 입력할 수 있는 입력창과 이를 전송하는 버튼으로 굉장히 단순한 형태입니다. 여기서부터 한번 시작해 보겠습니다.

먼저 form 요소를 생성합니다. 그리고 그 안에 입력창인 input 요소와 전송할 수 있는 button 요소를 생성합니다.

form 요소부터 보겠습니다. form에는 action, method 등의 속성이 있습니다. 먼저 action은 데이터를 보낼 URL 값이 들어가게 됩니다. 지금은 당장 서버와 통신하는 웹사이트를 만드는 것이 아니므로 나중에 form 요소에 어떤 속성을 어떻게 사용하면 되는지를 배워볼 것입니다. method 속성은 일전에 HTTP를 배울 때 데이터 관련 메소드가 값으로 들어갑니다. GET, POST, DELETE 등이 들어갑니다.

<input> 요소는 빈요소로, type을 속성으로 가집니다. type은 <input> 요소가 어떻게 입력을 받을 것인지 정의합니다.

type에 checkbox라고 써보면 checkbox가 나오네요. 그 외에도 button, radio 등의 타입을 적어주면 모양이 달라지는 것을 확인할 수 있습니다. 우리가 입력받을 것은 email 입니다. type에 email이라고 쓰면 입력모양으로 바뀌는데, 이메일 형식이 입력되지 않으면 알림을 보내줍니다. 그 외에 search, number, text, password 등이 있습니다. password 타입이면 입력한 내용이 보이지 않고, number라면 문자가 입력되었을 때 오류가 있음을 알려줍니다.

placeholder 속성은 사용자가 어떤 정보를 입력해야 하는지를 알려줍니다. input 창에 회색의 글씨로 표현되며 데이터가 입력되면 사라집니다.

input 태그가 여러 개 있을 때는 이 요소를 설명해주는 캡션을 달아줘야 하는데요. 이를 label 요소라고 합니다. label 요소는 input 요소와 꼭 한 쌍으로 딱 한 번만 지정할 수 있기 때문에 input에서는 id 속성, label에서는 for 속성을 똑같이 적어줍니다.

사용자 데이터를 서버에 보낼 수 있도록 버튼을 추가할 수 있습니다.

```html
<form action="#" class="mailing-form" method="post">
  <label for="email-contribute">send e-mail for contribution</label>
  <input
    type="email"
    placeholder="Enter email"
    id="email-contribute"
    name="email-contribute"
  />
  <button type="submit" class="mailing-form-btn">Submit</button>
</form>
```
