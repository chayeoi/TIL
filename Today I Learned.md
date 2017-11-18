# Today I Learned

## 01 HTML5

### 1. Web은 Internet의 수많은 서비스 중에 하나일 뿐이다.

<br />

### 2. 웹 접근성

1. 웹 접근성을 보장하는 방법

- 가이드라인 준수(WCAG 2.0)
- 웹 표준 준수

2. 한 가지 수단이 아니라 다양한 수단으로 접근할 수 있도록 제공되어야 한다.

<br />

### 3. 화면 구성 분할

1. 기본적으로 다음과 같은 단위와 순서로 분할한다.

- 헤더
- (네비게이션)
- 콘텐츠
- 푸터

2. 반복되지만 정보를 가진 영역이 아닐 때 그 의미에 맞게 네이밍하고 div 또는 article을 사용한다.
3. div 태그의 'role' 속성을 이용해 의미를 부여해도 괜찮지만, 역할 모델을 쓰느니 시맨틱 태그를 사용하여 분할하는 것이 더 바람직하다.
4. `div.container`로 영역을 감싸는 것은 필수가 아니라 옵션이다.

<br />

### 4. HTML5 기초

1. 특수문자

- `&lt;`: less than, &lt;
- `&gt;`: greater than, &gt;
- `&amp;`: ampersand, &amp;
- [Speical Entities](http://www.htmlhelp.com/reference/html40/entities/special.html)

2. head 설정

   ```html
   <!--다음 2개의 meta 태그는 같은 인코딩 속성을 설정한다.-->
   <meta http-equiv="Content-Type" content="text/html;charset=UTF-8"> <!--HTML 4.1 방식-->
   <meta charset="UTF-8"> <!--HTML5 방식-->

   <!--'lang'은 global attribute로 웹 접근성과 밀접한 관련이 있다.-->
   <!--'id'라는 content가 있을 때 lang="ko"면 "이드"라 읽고 lang="en"일 때 "아이디"라 읽는다.-->
   <html lang="en"></html>

   <!--meta charset="UTF-8을 꼭 head가 들어가자마자 첫 줄에 선언해줘야 그 다음 줄부터 위치하는 tag들도 인코딩이 깨지지 않는다.-->

   <!--UI에 대한 변경을 해주고 싶을 때 사용하는 meta 속성-->
   <meta name="viewport">

   <!--X는 비표준, UA는 User Agent를 의미한다.-->
   <!--"ie=edge": 설치되어 있는 브라우저 중에 최신 버전으로 설정-->
   <!--"ie=8": 11 버전을 쓰고 있더라도 8 버전으로 렌더링-->
   <meta http-equiv="X-UA-Compatible" content="ie=edge">
   ```

3. `<abbr>`: 축약 태그

<br />

### 5. Cross Browsing Issue

1. 지원하지 않는 브라우저를 버릴 것이 아니라 대안을 만드는 것이 진정한 해결 방법이다.

<br />

### 6. Keyboard Focusing

1. 키보드 포커싱은 기본적으로 `a`와 `form` 관련 요소만 받을 수 있다.

2. 다른 속성들이 포커스를 받게 하려면 `tabindex` 속성을 마크업에 추가한다.

   ```html
   <span tabindex="0">HTML에 대해</span>
   ```

3. `tabindex`는 마크업 순서에 따라 접근한다.

<br />

> #### `tabindex`
>
> 1. `tabindex`의 value가 0인 이유?
>
> - `tabindex`는 링크 관련 태그 및 `input` 태그 이외의 요소가 키보드 포커싱을 받을 수 있도록 설정하는 어트리뷰트
> - `tabindex: 0`은 순차적으로 포커싱을 받을 수 있도록 하고,  `tabindex: 1`은 인접한 요소 중에 `tabindex` 속성을 가진 요소를 탐색한 후 해당 요소들에 대해 인덱싱한다.
> - `tabindex: -1`은 모든 요소들에 대하여 탭 포커스에서 제외시킬 수 있다.
> 2. 만약 인접한 형제 요소가 tabindex를 가지고 있다면 자식 요소보다 형제 요소에 먼저 접근하는지?
> - 자식 요소를 탐색 후 형제 요소에 접근한다.

<br />

### 7. 섹셔닝 ([https://seulbi.github.io/](https://seulbi.github.io/))

1. 구조 잡는 순서

- Step 1: 영역을 구분한다.
- Step 2: 어떤 태그를 사용할 지 정한다.
- Step 3: 각 요소를 클래스와 아이디로 네이밍한다.
- Step 4: 특정 이벤트가 발생했을 때 어떤 방식으로 처리할 건지 조사한다. 그 이후에 더 합리적인 방법을 고민하면서 튜닝하고 문제를 줄여나간다.

3. 섹셔닝

- header: 로고(h1), 멤버(ul), 검색 홈(form)
- nav: 메인 메뉴(ul)
- main: 서적(section), 뉴스(article), 게시판(section), 인기 사이트(section), 트위터(article)

  - 트위터나 뉴스 콘텐츠처럼 배포 목적이 있을 때 article로 보는 것도 좋다.
  - div로 구분할 시에 `헤딩 처리`를 통해 암묵적인 아웃라인을 형성햐여야 한다.
  - section과 article도 역시 헤딩을 가져야 한다.
- footer: 주소(address), 저작권(div)

<br />

### 8. form

1. (네이버에서 CSS 제거한 검색 폼 참고): 테두리는 `fieldset`, '검색'은 `legend`이다. 검색과 관련된 요소를 묶어주는 역할을 한다.
2. 회원가입 폼을 만들 때 한 개의 form 안에 두 개의 fieldset을 만들어 필수 정보, 선택 정보로 성격이 다른 것을 구분하기도 한다.
3. `fieldset`은 `div`와 성격이 유사하지만 div는 범용적인 그루핑 요소인 반면, fieldset은 전용 그루핑 요소이다. 즉, 연관된 요소들을 묶을 때에 사용한다.
4. `input`은 어떤 `label`을 위한 것인지 id를 통해 알려줘야 하고 `label`의 for 어트리뷰트를 이용해 연관된 `input`의 아이디를 지정해줘야 한다.

<br />

### 9. button

1. Type

- submit: 폼 양식 제출
- reset: 입력 내용 리셋
- button: 스크립트 실행

<br />
<br />

## 02 CSS3

### 1. `overflow: hidden`의 특성

1. `overflow: hidden`은 `overflow: visible`일때는 인식하지 못 했던 몇 가지를 인식하게 한다.

- **float** 처리된 요소
- 자식 요소의 **margin 값**

2. 만약 `overflow` 프로퍼티의 값이 `visible`이고 내부 여백(padding)과 테두리(border)가 없는 상태에서 자식 요소가 'margin-top'을 가지고 있을 경우, 마치 요소 자신의 'margin-top'처럼 보여진다. 하지만, `hidden`인 상태에서는 그 'margin-top'이 자신의 요소 안에서 이뤄진다. 물론 부모 요소가 해당 margin이나 border를 가지고 있다면 `hidden`처럼 인식할 수 있다.
3. `overflow: hidden;`*을 적용하면 content가 border 이외로 흘러넘치는 영역을 숨길 뿐, padding 영역에서는 content를 숨기지 않고 그대로 표시한다.
4. 넘치는 영역을 계산하는 방식으로 자식 요소의 사이즈를 체크하여 영역을 잡는다.

<br />

> #### Box Model
>
> 1. 부모 요소 내에 위치한 자식 요소에 margin을 설정하면 그 margin은 부모 요소 내의 Content Box를 기준으로 설정되는지?
>
>    → Me: 해보니깐 그런 것 같음. `overflow: hidden`일 때 자식 요소의 margin을 인식한다는 글을 보니깐 아닌 것 같기도 하고?
>
> 2. `overflow: visible`일 때 자식 요소의 margin을 마치 자신의 margin처럼 인식한다는데, 그렇게 되면 해당 요소의 margin은 자신과 자식 요소의 margin 중 어떤 것이 적용되는 것인지?
>
> 3. `overflow: visible`이고 `border-width: 1px`일 때 자식 요소의 margin은 border를 기준으로 인식하는 듯 한데, 만약 padding에도 값이 있으면  padding 영역으로부터 margin을 인식? 아니면 똑같이 border를 기준으로 인식?

<br />

### 2. 레이아웃

1. 높이는 auto로 설정하여 컨텐츠에 따라 자연스럽게 늘어나게 하는 것이 좋다.
2. 배치 조정 방법

- `float`: 구형 브라우저까지 고려
- `flexbox`: 모던 브라우저에 맞출 때 사용
- `grid`: 모던 브라우저에 맞출 때 사용

3. flexbox(CSS3) vs float(CSS2)
4. 레이아웃 구성 시 헷갈리지 않도록 `box-sizing: border-box`로 설정한다.

<br />

#### 2.1 flexbox

1. `display: flex: 해당 요소 안의 모든 엘리먼트가 **flex item으로 변경**된다.

2. `flex-direction`의 default는 **row**이다.

3. 모바일 웹 개발 시 box-sizing은 **content-box보다 border-box가 더 유리**하다.

4. `justify-content: flex-direction`에 설정된 방향에 대한 정렬 설정 (**메인 축**)

5. `align-items`: 교차점 정렬 설정 (**교차점**)

6. `justify-content`의 default는 **flex-start**이다.

7. `justify-content`

   ```css
   .between {
     justify-content: space-between; /* 남는 역역을 잘라서 between 값을 자동 계산 */
   }

   .around {
     justify-content: space-around; /* 양쪽에 여백까지 할당 */
   }
   ```


8. `align-items`는 해당 요소 내의 모든 아이템을 정렬할 때, align-self는 자신만 정렬할 때 사용한다.

9. 요소 간에 정렬 순서를 변경할 때에는 마크업 순서로 배치를 바꾸는 것이 아니라 `flexbox`의 order 프로퍼티를 사용하여 정렬 순서를 변경한다. order 프로퍼티의 **default는 0**이다.

10. `flexbox`는 자신의 container보다 width가 클 때, **각 아이템의 width를 알아서 비율에 맞게 계산**한다.

11. `flexbox`의 width가 container보다 width를 넘었을 때 줄을 변경하고 싶다면 `flex-wrap: wrap`을 설정하면 된다.

12. `flex-wrap`의 **default는 no-wrap**이다.

13. `flex-flow`로 `flex-direction`과 `flex-wrap`을 한 번에 설정할 수 있다.

14. `align-items`는 단일 행, 열을 정렬할 때 사용하고 `align-content`는 다중 행, 열을 정렬할 때 사용한다.

<br />

> #### `justify-content: space-around`
>
> 사이 여백과 끝 여백이 다르게 나타나는데 그 계산 방법은 그리드와 관련이 있다.

<br />

#### 2.2 float

1. `float`의 **default는 none**이다.
2. `float`은 left, right 정렬만 가능할 뿐, 속성 값에 center를 주는 것은 불가능하다.
3. `float`은 **Block Element**에만 적용 가능하며, float 되는 순간 좌측 혹은 우측에 다른 요소를 배치하기 위해 자신의 너비를 최소화하게 된다.
4. `clear` 프로퍼티는 **Block Element**에만 사용 가능하다.

<br />

#### 2.3 Grid

1. 제일 좋은 그리드 컬럼은 12 컬럼 기반이고, 좀 복잡할 경우 16 컬럼을 사용한다. 더 세밀함이 요구될 때에는 24 컬럼을 사용한다.

<br />

### 3. 색상 조정

1. rgb 16진수 방식

- 앞에서부터 두 자리씩 Red, Green, Blue 색상을 나타낸다.
- 색상별로 같은 값이 반복될 때, short-hand로 세 자리로 축약하여 나타낼 수 있다. (#AA55BB → #A5B) 

2. rgb 10진수 방식

- 앞에서부터 Red, Green, Blue, 불투명도를 나타낸다. (rgba(255, 0, 0,  0.5))

<br />

### 4. vh(Viewport Height)

1. 높이를 나타내는 단위로 px, %, em 이외에 vh를 사용할 수 있다.
2. 1vh는 디바이스 화면 높이의  1 / 100의 크기를 의미한다.
3. vh와 % 모두 상대 크기를 나타내는 단위로 헷갈릴 수 있다.

- vh: 디바이스 화면 높이를 기준으로 상대적 크기를 정함.
- %: 해당 요소가 속한 부모 요소의 content 영역의 높이를 기준으로 상대적 크기를 정함. 

<br />

### 5. Selector

1. 그룹 선택자

- 그룹 선택자(,)를 이용하면 공통된 성질을 한 번에 선언할 수 있다.
- 모든 스타일에 대해 공통으로 적용할 수 있으므로 유지보수하기 편리하다.

2. 같은 `header`라도 본문과 섹션에서 사용되는 `header`는 서로 다르므로 서로 다른 클래스명으로 스타일을 지정한다.

<br />

### 6. 가운데 정렬

1. CSS2에서는 가운데 정렬이 없지만(`margin: 0 auto`는 트릭에 불과하다) CSS3에서는 `flexbox`를 이용하면 가운데 정렬이 가능하다.
2. `margin: 0 auto`는 브라우저 뷰포트에서 width를 제외한 나머지를 자동으로 절반으로 나누어 처리한다. 즉, 실제로 가운데 정렬이 일어난 것이 아니라 **margin 영역은 눈에 보이지 않는 영역이기 때문에 가운데 정렬처럼 보이는 것**이다.
3. 수평 정렬: `position` 프로퍼티 설정 후 `left: 50%`와 `transform: translateX(-50%)`를 적용
4. 수직 정렬: `position` 프로퍼티 설정 후 `top: 50%`와 `transform: translateY(-50%)`를 적용
5. `line-height`를 이용하여 수직 정렬을 할 수 있다.

- line-height에서 font-size를 제외한 나머지를 이등분해서 상하 여백을 설정한다.
- 그러나 글꼴에 따라 정확히 가운데 정렬이 되지 않을 수도 있다.

6. `flex-box`의 `align-items: center`를 이용하여 정렬할 수도 있다.

<br />

> #### `translate` 프로퍼티
>
> 1. 더 공부해보기
>
> `line-height` 프로퍼티
>
> 1. 상하 여백은 margin과 padding  중 어떤 것에 해당하는지?

<br />

### 7. outline

1. `border` 프로퍼티는 border의 속성을 정의하고, `outline` 프로퍼티는 border의 바깥쪽 선 속성을 정의한다.

<br />

### 8. SASS

1. CSS 전처리기이다. 브라우저는 사스를 바로 해석할 수 없고, 컴파일(빌드)로 CSS로 변환 후 해석을 시작한다.
2. SASS를 이용해 CSS를 프로그래밍적으로 다룰 수 있다.

<br />

### 9. `display: none`와 `visibility: hidden`

1. `display: none`은 영역까지 감춘다.
2. `visibility: hidden`은 영역은 남겨둔다.

<br />

### 10. 음수 margin

1. padding은 음수를 사용할 수 없다.

<br />

### 11. `position`

1. `position` 프로퍼티 이용 시, 먼저 마크업된 태그가 아래에 놓이게 된다.
2. 간혹 `position`과 `float`를 같이 사용할 수 없냐고 묻는 사람들이 있는데, 같이 사용될 수 있다.
3. `position` 프로퍼티의 기준점은 `box-sizing: content-box`일 때 padding 영역을 기준으로 하고, `box-sizing: border-box`일 때 border 영역을 기준으로 한다.
4. `position: relative`는 자신의 top-left를 기준(0, 0)으로 하여 움직인다.
5. `position: absolute` 선언 시, block 레벨 요소의 width는 inline 요소와 같이 content에 맞게 변화되므로 적절한 width를 지정하여야 한다.
6. `position: absolute` 선언 시 inline 요소도 block 요소로 바뀌므로 width를 지정할 수 있다.
7. `positon: fixed`: 부모 요소와 관계없이 브라우저의 viewport를 기준으로 좌표프로퍼티(top, bottom, left, right)을 사용하여 위치를 이동시킨다. 스크롤이 되더라도 화면에서 사라지지 않고 항상 같은 곳에 위치한다. fixed 프로퍼티 선언 시, block 요소의 width는 inline 요소와 같이 content에 맞게 변화되므로 적절한 width를 지정하여야 한다.
8. `z-index`: `z-index` 프로퍼티에 큰 숫자값을 지정할수록 화면 전면에 출력된다. `position` 프로퍼티가 static 이외인 요소에만 적용된다.
9. `position: relative`는 자신의 분신을 제 자리에 놓아둔 상태로 움직인다고 생각하면 된다.

<br />

> #### `z-index`
>
> 1. `z-index`의 기본값은?
>
>    → 기본값은 0이다. `z-index`의 값이 같을 때, 나중에 마크업된 요소가 상위에 위치한다.
>
> #### `position`
>
> 1. `position: absolute` 시에 `span`은 너비를 가질 수 있었고 `div`는 너비가 콘텐츠만큼의 너비를 갖게 되었는데, `span`은 block 요소가 된 것이고 `div`는 inline-block 요소가 된 것인지?
>
>    → me: block 요소이지만 width만 content에 맞게 줄어드는 것 같다.
>
> 2. `position: absolute`를 설정하면 부모 `div`가 자식을 인식하지 못 하게 되는 문제는 `.clearfix`는 당연히 먹히지 않으므로 어떻게 해결할 수 있는지?
>
> 3. `position: absolute`이 선언되었을 때 `float` 속성을 아예 사용할 수 없는지? `float` 속성을 함께 사용할 수 없는 것인지? 

<br />

### 12. 구체성 점수

1. 이진수로 표현된다.
2. !important는 VIP이다.
3. 같은 구체성 점수일 때 나중에 정의한 부분이 적용된다.

<br />

### 13. `background`

1. `background` 지정

   ```css
   .example1 {
     background: url('url'); /* 'url'을 배경으로 지정 */
   }

   .example2 {
     background: linear-gradient(to bottom, #f4bd30 0%, #ed802d 30%, #ed802d 70%, #f4bd30 100%); /* 배경에 그라디언트를 적용 */
   }
   ```

2. 하나의 속성에 값을 두 번 지정하면 나중에 적용된 속성을 최종적으로 인식한다.

<br />

### 14. `border-radius`

1. `border-radius: 0 0 15px 15px`: bottom-right와 bottom-left에 x와 y 방향의 반지름이 15px인 곡률을 생성
2. `border-radius: 0 0 15px 15px / 0 0 10px 10px`: x와 y 방향의 반지름을 다르게 설정할 수 있다. 

<br />

### 15. 디자인 시안에 각 속성을 적어보면서 체크한다.

<br />

### 16. 상속

1. 배치와 관련된 속성이 아닌 것들은 보통 상속된다.
2. 배치와 관련된 속성들은 상속되지 않는다.

<br />

### 17. `cursor: pointer`

1. `cursor: pointer`는 해당 요소에 커서가 위치했을 때 커서의 모양을 포인터로 설정한다.

<br />

### 18. `text-shadow`

1. `text-shadow` 프로퍼티

   ```css
   .example1 {
     /* 각 값은 순서대로 offset-x, offset-y, blur, color를 나타낸다. */
     text-shadow: 1px 1px 0 #000; 
   }

   .example2 {
     /* 그림자의 두께를 조정하려면 다음과 같이 설정한다. */
     text-shadow: 1px 1px 5px #000, 2px 2px 5px #000, 3px 3px 5px #000, 4px 4px 0 #000;
   }

   .example3 {
     /* 그림자를 활용한 윤곽체를 만들려면 다음과 같이 설정한다.  */
     text-shadow: 1px 0 0 #000, 0 1px 0 #000, -1px 0 0 #000, 0 -1px 0 #000;
   }

   ```

<br />

### 19.  `box-sizing`

1. `box-sizing: content-box`는 패딩 영역까지 포함한 넓이이다.
2. `background-color` 프로퍼티를 적용하면 padding 영역까지 적용된다.

<br />

### 20. `white-space: nowrap`

1. `white-space`은 공백문자 처리에 관한 방법이다.
2. `white-space: nowrap`은 상자 크기가 작더라도 줄바꿈을 하지 말고 한 줄에 보여달라는 뜻이다.

<br />

### 21. `display`

1. 작은 상자가 큰 상자를 포함하는 건 바람직하지 않다.
2. block > inline-block > inline

> #### inline 요소 내의 block 요소
> 1. 불가능한 건 아니지만 바람직하지 않다는 것인지?
>   ```html
>   <a href="#"><div class="a">Hello</div></a>
>   ```

<br />

### 22. 가상 요소 선택자

1. 가상 요소 선택자(:after, ::after)

- :을 하나만 찍는 것은 예전 방식이고, 2개를 찍는 것이 요즘 방식이다.

2. 가상 요소 선택자를 사용하여 block 요소로 지정하면 해당 텍스트 요소와 같은 같은 너비의 width를 갖도록 할 수 있다.
3. `:hover`에 지정한 프로퍼티는 요소 선택자에서 지정한 기본 프로퍼티에 덮어 씌운다. 

<br />

### 23. Reset CSS

1. 브라우저의 Agent Style을 무시하기 위한 CSS 초기화 스타일이다.
2. 에릭 마이어의 CSS 초기화 스타일을 이용하면 좋다.
3. 전체 선택자(*)로 선택해서 리셋하는 것보다 필요한 태그만 추려 리셋하는 것이 필요하지 않은 요소 설정을 피할 수 있기 때문에 성능면에서 더 좋다.

<br />

### 24. CSS Animation

1. Animation

- 가장 먼저 할 일은 애니메이션의 이름을 정하는 것이다.

- 그 다음으로 어떤 효과가 필요할지 직접 적어본다.

  - 텍스트 이동: translate(x, y)
  - 글자 크기 변화: font-size
  - 투명도의 변화: color: rgba() (상자 자체의 불투명도를 변화시키고 싶으면 `opacity` 프로퍼티를 이용한다.)

- Example
  ```css
  @keyframes text-ani {
    /* 시작 지점  0%{} */
    from {
      font-size: 12px;
      color: rgba(0, 0, 0, 0);
      transform: translate(0, 0);
      /* top: 0;
      left: 0; */
    }
    /* 끝 지점 100%{} */
    to {
      font-size: 24px;
      color: rgba(0, 0, 0, 1);
      transform: translate(400px, 70px);
      /* top: 70px;
      left: 400px; */
    }
  }

  .short-hand {
    animation: [animation-name] [animation-duration] [animation-timing-function]
    [animation-delay] [animation-iteration-count] [animation-direction]
    [animation-fill-mode] [animation-play-state];
  }
  ```

- `animation-delay`는 처음 시작 시간만 늦출 뿐, 매번 반복할 때 마다 시간을 늦추지는 않는다.

- from, to가 아닌 %로 시점을 선택하여 효과를 지정할 수도 있다.

- `animation-play-state: paused`: 애니메이션 실행을 중지한다.

- [CSS 애니메이션](https://brunch.co.kr/@99-life/3)

2. Transform
3. Transition

- transition은 프로퍼티의 값이 duration 동안 매끄럽게 변화하도록 한다.
- [Poiemaweb - CSS3 Effect](http://poiemaweb.com/css3-effect)
- Move 애니메이션을 실현할 때, position을 이용한 방식은 리페인팅 방식으로 성능에 많은 문제를 일으키므로 translate를 이용한 방식이 더 좋은 방식이다.

4. [codepen - CSS Animation](https://codepen.io/search/pens?q=animation&limit=all&type=type-pens)

<br />

### 25. Multi Background

1. Multi Background

  ```css
  .container {
    background-image: url("images/bg_flower.png");
    background-repeat: no-repeat;

    /* short-hand */
    background: url("images/bg_flower.png") no-repeat 50% 0, linear-gradient(to bottom, #aaa 0%, #eee 50%, #fff 100%);

  }
  ```

2. `background-position`: 픽셀 방식과 백분율 방식, 키워드 방식이 있다.

- 픽셀 방식: 요소 박스를 기준으로 위치를 체크한다.
- 백분율 방식: 요소 박스와 배경 박스를 모두 기준으로 위치를 체크한다. 따라서 가운데 정렬 시에 백분율 방식이 많이 쓰인다.
- 키워드 방식: center left right / top bottom 등의 키워드를 지정할 수 있다.

<br />

### 26. SASS vs SCSS 

1. SASS(구 문법)
2. SCSS(신 문법)

<br />

### 27. 미디어 쿼리

1. Mobile First? Desktop First?: 가장 좋은 전략은 작은 기기부터 구성하는 것이다.

2. /media-query.css

   ```css
   @charset "utf-8"; /* 가장 선두에 선언하여야 모든 문자 포맷을 깨지지 않고 읽을 수 있다. */

   /* 모든 디바이스 */

   body {
     background: yellow;
   }

   /* 태블릿 디바이스 이상 */
   /* @media(미디어 쿼리를 적용하여) all(디바이스 지정, all 또는 screen은 모든 디바이스) min-width: 768px(디바이스의 최소 너비가 768px일 때){ 이 코드를 실행한다. } */ 
   @media screen and (min-width:768px) {
     body {
       background: pink;
     }
   }
   ```

3. 네이버는 반응형 웹이 아니다. naver.com과 m.naver.com은 다른 사이트이다.

4. 뷰포트 메타 태그가 없으면 휴대기기는 일반적 데스크톱 화면 너비로 페이지를 렌더링한 다음 모바일 화면에 맞게 페이지 크기를 조정한다. 따라서 디바이스의 가상 해상도로 인식하도록 하는 태그가 필요하다.

   ```html
   <!-- 뷰포트를 설정하여 뷰포트의 너비와 크기를 제어할 수 있다. -->
   <!-- 이제부터 뷰포트는 디바이스의 width(물리적 해상도)에 맞추겠다. -->
   <!-- 기기 독립적 픽셀과 CSS 픽셀 간에 1:1 관계를 설정하려면 initial-scale=1을 포함한다. -->
   <!-- initial-scale 속성은 페이지가 처음 로드될 때 줌 레벨을 조정한다. maximum-scale, minimum-scale, 그리고 user-scalable 속성들은 사용자가 얼마나 페이지를 줌-인, 줌-아웃할 수 있는지를 조정한다. -->
   <!-- maximum-scale과 minimum-scale의 기본값은 브라우저에 따라 다르다. -->
   <meta name="viewport" content="width=device-width, initial-scale=1.0">
   ```

5. [뷰포트 메타 태그가 있는 HTML](https://developers.google.com/web/tools/lighthouse/audits/has-viewport-meta-tag?hl=ko)

<br />

### 28. 개발 버전과 배포 버전

1. *.css: 개발버전으로, 주석 및 단락을 포함한다.
2. *.min.css: 배포 버전으로 최적화된 버전이다.

<br />

### 29. Vendor Prefix

1. 특정 브라우저에 대해 제어하기 위한 접두사를 말한다.
2. -webkit-: Chrome, Safari, Opera
3. [Vendor Prefix란?](http://aueyoo.tistory.com/11)

<br />

### 30. CSS 선언 순서의 중요성

1. 중복 선언된 프로퍼티는 나중에 선언된 CSS 파일 또는 라인이 최종적으로 렌더링된다.

<br />

### 31. 웹 폰트

1. `@font-face`: font의 성격과 자원을 선언한다.
2. 폰트의 용량이 커질수록 성능에 영향을 준다.
3. 다양한 폰트를 선언해서 해당 폰트가 존재하지 않을 때 차선책으로 적용할 대안을 제시해야 한다.
4. **[CSS Validation Service](https://jigsaw.w3.org/css-validator/)**에서 `@import`와 `@font-face`는 체크할 수 없다.
5. 로컬 경로를 우선 설정한다.
6. [웹 폰트 파헤치기](https://www.slideshare.net/wsconf/web-font-wsconfseoul2017-vol2)

<br />

> #### /fonts.css 파일 질문
>
> 1. `font-family`와  `font-style, ` `font-weight`의 값은 지정된 키워드 값이 아니라 원하는 값으로 지정해도 되는 것인지? 그 후 그 값으로 사용하면 되는 것인지?
> 2. `local()`과 `url()` 방식의 차이점은?
> 3. `src` 프로퍼티에 여러 개를 선언하는 이유는 해당 폰트가 존재하지 않을 때에 대응하기 위한 것인지?

<br />

### 32. 병합 이슈

1. margin collaspsing: margin은 투명한 영역으로 병합이 발생한다.
2. padding은 병합되지 않는다.

<br />

### 33. 상속 이슈

1. `a`의 `color` 프로퍼티의 기본값(agent style)은 `blue`
2. 직접 설정한 값이 기본 속성의 값보다 우선 순위가 높다.
3. 배치 / 레이아웃에 관한 속성은 상속되지 않는다.
4. 데코레이션 속성은 상속되는 경향이 많다.

<br />

### 34. 모바일을 고려한 링크 또는 버튼의 사이즈

1. 성인 남성 검지 손가락 기준으로 화면을 클릭하는 영역은 최소 44px

<br />

### 35. 기본 스타일

1. 본문 스타일

   ```css
   html {
       font-size: 10px; /* 루트 요소에 고정 폰트 사이즈 지정 */
   }
   body {
       font-family: 'Noto Sans Regular', sans-serif;
       font-size: 1.4rem; /* root equal M, 1.4rem = 14px */
       color: #181818;
   }
   ```

2. 링크 스타일

   ```css
   a:link, a:visited {
       color:inherit; /* 상위 요소를 탐색하여 상속받는다. */
       text-decoration: none;
   }
   a:hover, a:focus {
       color: #f000;
   }
   ```

3. .clearfix

   ```css
   .clearfix::after {
      content: "" ; /* 글자 하나만큼의 높이 */
       display: block; /* 가상 요소는 기본적으로 inline이다. */
       clear: both;
   }
   ```

4. 멤버 링크

   ```css
   .member {
       text-transform: uppercase;
       font-size: 0; /* 부모 요소 font-size: 0. 마크업 구조로 인한 간극을 없애기 위함 */
       text-align:right;
       transform: translateX(10px); 
   }

   .member li {
       display: inline-block; /* 가로 배치를 위해 inline-block 지정. IE8 이상 지원 */
       font-size:1.4rem;/* 해당 콘텐츠 font-size 재정의 */
       padding:10px 0;
   }
   ```

5. ​

<br />
<br />

## 03 Javascript

<br />
<br />

## 04 ES6

<br />
<br />

## 05 jQuery

### 1. `toggleClass()`, `addClass()`, `removeClass()`

1. `toggleClass()`는 `addClass()`와 `removeClass()`를 합쳐놓은 것과 같다.
2. 따라서 `toggleClass()`는 class 속성에 바인딩된 값 자체를 바꾸는 것이 아니라 기존에 존재하던 class에 다른 class를 추가하고 삭제하는 역할을 한다.

<br />
<br />

## 06 React.js

<br />
<br />

## 07 Basic

### 1. 컴파일 언어 vs 인터프리트 언어

1. 컴파일 언어: 파일에 오류가 있어야 정확한 결과를 보여준다.
2. 인터프리트 언어: 어플리케이션이 코드를 순차적으로 한 줄씩 해석

<br />
<br />

## 08 Git

### 1. 과제 및 강의 내용 요약본 제출 방법

1. [https://github.com/kwonjounghun/FDS_7s](https://github.com/kwonjounghun/FDS_7s)를 자신의 저장소로 fork한다.

2. fork한 저장소를 clone한다.

   ```bash
   git clone https://github.com/chayeoi/FDS_7s.git
   cd FDS_7s
   ```

3. upstream이라는 이름으로 새로운 원격 저장소를 추가한다. (origin 다음 저장소 이름을 관례적으로 upstream이라 명명)

   ```bash
   git remote add upstream https://github.com/kwonjounghun/FDS_7s.git
   ```

4. 정리한 내용을 자신의 폴더 안에 파일명은 20171116.md로 저장한 후 자신의 원격 저장소에 push한다.

   ```bash
   git add .
   git commit -m "20171116 과제"
   git push origin master
   ```

5. 자신의 저장소에서 'Pull requests' → 'New pull request'한다.
6. request 내용: '20171116 김찬연 과제입니다.'
7. 과제를 다시 받아오려면

   ```bash
   git pull upstream master
   ```

8. fork를 뜬 저장소로 직접 push하려면 해당 저장소로부터 키를 받아야 한다. 키를 받지 않아도 pull은 가능하다.

<br />

> #### github 계정 2개 사용법
>
> 1. 하나의 맥에서 github 계정을 2개 사용하려면?


<br />
<br />

## 09 ETC

### 1. Tool

1. Slack
2. Trello
3. Git
4. Google Drive
5. Naver Cafe

<br />

### 2. Shortcut

1. VScode

- 커서가 위치한 줄 삭제: cmd + shift + K
- 커서가 위치한 코드 라인 변경: opt + ↑, ↓
- 명령 팔레트 실행: cmd + shift + P
- indent, miniMap, fontSize 수정: formatter config를 통해 수정 가능
- 약어로 래핑: 래핑할 블록 선택 → 명령 팔레트 실행 → 약어로 래핑, cmd + G

2. Emmet

- !: 기본 골격 완성

<br />

### 3. Naming Convention

1. 카멜 케이스: mainContent
2. 파스칼 케이스: MainContent
3. 스네이크 케이스: main_content
4. 케밥 케이스: main-content
5. [CSS 방법론](http://wit.nts-corp.com/2015/04/16/3538)

<br />

### 4. DTD(Document Type Definition)

1. Strict DTD
2. Transitional DTD
3. Frame DTD

<br />

### 5. Bookmark(/FDS07)

1. ***[seulbinim/FC-FDS](https://github.com/seulbinim/FC-FDS)***
2. ***[Emmet](https://docs.emmet.io/)***
3. ***[W3schools](https://www.w3schools.com/)***
4. ***[w3.org](https://www.w3.org/)*** -  'Markup Validation Service'를 이용하여 HTML 문법을 검사할 수 있다.
5. ***[html5test](html5test.com)*** - 사용 중인 브라우저가 HTML5 스펙을 얼마나 지원하는지 확인할 수 있다.
6. ***[css3test](http://css3test.com/)*** - 사용 중인 브라우저가 CSS3 모듈을 얼마나 지원하는지 확인할 수 있다.
7. ***[csszengarden](http://csszengarden.com/)*** - 하나의 html 문서에 대해 다양한 CSS 레이아웃을 적용해볼 수 있다.
8. ***[naradesign](naradesign.net/wp/)*** - 웹 관련 기술 블로그
9. ***[flexboxfroggy](http://flexboxfroggy.com/)***
10. ***[Responsive Logos](http://responsivelogos.co.uk/)***
11. ***[Troy - Responsive web tester](http://troy.labs.daum.net/)***
12. ***[Can I use](https://www.caniuse.com/)***
13. ***[Nth master](http://nthmaster.com/)***
14. ***[Colorzilla](http://www.colorzilla.com/gradient-editor/)***
15. ***[Prefix free](https://leaverou.github.io/prefixfree/)*** - 해당 사이트에서 제공하는 스크립트 파일을 html 파일에 연동하면 css 파일에 자동으로 prefix를 추가해준다. (브라우저 별로 다른 지원이 필요할 경우에 사용. 특히 gradient를 적용할 때 prefix를 붙이는 습관을 들여야 한다.)
16. ***[Fontello](http://fontello.com/)*** - 아이콘을 폰트로 변환해준다.

<br />

### 6. CLI Command

1. `ls`: List의 약어. 현재 위치한 디렉토리 내의 파일들을 나열한다.
2. `cd`: Change Directory의 약어
3. `touch test.html`: test.html 생성
4. `rmdir dirname`: 빈 디렉토리 dirname 삭제
5. `vim config`: config 파일을 vim editor로 열기

<br />

### 7. Book Recommend

1. 제프리 젤드만의 웹 표준 가이드

<br />

### 8. VS Extension

1. Path Autocomplete: path 자동 완성 기능
2. ​

<br />

### 9. User Agent Style 

1. 브라우저가 갖고 있는 default style을 의미한다.

<br />

### 10. Reference

1. http://naradesign.net/wp/2008/05/27/144/
2. 웹 접근성 가이드라인: WCAG 4대 원칙
3. [웹 폰트 파헤치기](https://www.slideshare.net/wsconf/web-font-wsconfseoul2017-vol2?qid=953d01dc-4191-43ec-9c03-845a22578cf4&v=&b=&from_search=1)
4. [CSS 애니메이션 성능](https://www.slideshare.net/wsconf/css-animation-wsconfseoul2017-vol2?qid=953d01dc-4191-43ec-9c03-845a22578cf4&v=&b=&from_search=2)
5. [CSS 방법론](http://wit.nts-corp.com/2015/04/16/3538)

<br />

### 11. Tip

1. 영문 번역이 어색할 때 일본어 문서 보기가 있으면 일본어 문서를 한국어로 번역한다. (일본어 어순이 한국어 어순이랑 비슷하기 때문)

<br />

### 12. 경로 설정

1. ''./css/style.css'와 'css/style.css'는 같은 의미이다.

<br />

<br />

## 10 Question

### 1. 부모 요소에 `font-size: 0`으로 준 이유는?

```css
.member {
    text-transform: uppercase;
    font-size: 0;
    text-align: right;
    transform: translateX(10px); 
}
```

→ 마크업 구조로 인한 간극을 없애기 위해 `font-size: 0` 지정

<br />

### 2. BEM 방법을 사용할 때 Block 내 Block 내의 Element 네이밍은 어떤 방식으로?

<br />

### 3. 다른 사이트들을 살펴봤을 때 보통 `<nav>`가 `<header>`에 포함되어 있던데 보통은 어떻게 하는지?