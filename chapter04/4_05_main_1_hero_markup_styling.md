# 4-05. main(1): hero section 마크업 및 스타일링

- 실습 사이트 예제: https://python-lecture-example-1.netlify.com/
- 코드: https://github.com/tinytinystone/python-lecture-example/tree/4_05_main_1_hero_markup_styling

(추후 업데이트 예정)

<!-- html 필요 없는 부분 접기 - header 부분 접어놓고 시작

- main에는 총 3개의 섹션

  - hero, main-content, side-content
  - main-content와 side-content는 단으로 나란히 -> 부모요소로 한번 감싸서 float 처리
  - float할 필요는 없고 padding만 있는 container와 float로 높이를 잃었을 때 처리해줘야 하는 container-float 두개로 나누기

- 소개글 설명과 Django 문서로 이어지는 링크 두 개로 이뤄져 있음.
- 클래스 네이밍. 클릭, 가입 등의 액션을 요구하는 버튼이나 링크 등을 call to action, 줄여서 cta라고 부름. 눈에 띄는 색상을 주는 편.

- 스타일링
  - text-align: center
  - 완벽하게 똑같이 구현한다기보다 적절하게 간격을 두도록 하겠다.
  - 위아래 패딩. 50px 0
  - border-bottom => 단축표기법으로 사용. 1px solid (색상값)
  - .intro-desc - 글씨를 두 줄에 적어주기 위해서 크기 지정. width: 700px; - 바깥여백. 가운데 정렬하기 위해서 좌우는 auto로 두고 위 아래만 적절히. margin: 40px auto 50px; - 글씨 관련 속성은 개발자도구를 한번 켜서 살펴보고 기재.
    font-weight: 300;
    font-size: 3.6rem;
    line-height: 1.3; - cta - a 태그는 인라인 요소이나 크기를 줘야 하므로 display block - padding, border를 이용해서 버튼처럼 보이도록 디자인 해보기 - 배경색/font-size/font-weight 등 적용 - 마우스가 올라가거나 탭 키 등을 이용하여 포커스가 가있을 때 배경색이 변한다 => 가상요소를 사용해서 디자인
    .cta {
    display: block;
    width: 300px;
    padding: 2rem 5rem;
    margin: 20px auto 60px;
    border-radius: 8px;
    font-size: 1.8rem;
    font-weight: 400;
    background: #44b78b;
    color: #fff;
    }
    .cta:focus,
    .cta:hover,
    .cta:active {
    background-color: #51be95;
    } -->
