# Text level elements

* `<sup>`: 윗첨자 요소
* `<sub>`: 아래첨자 요소
* `<abbr>`: 축약 요소
* `<time>`: 시간 요소
* `<s>`: 더 이상 관련이 없거나 더 이상 정확하지 않은 요소
* `<mark>`: 관련 참조 목적의 하이라이트된 글자 요소
* `<small>`: 저작권, 법적 텍스트, 주석 및 작은 글씨 요소
* `<time>`: 기계가 이해할 수 있는 형태로 날짜나 시간을 나타내는 요소
* `<dfn>`: 정의 용어를 표현하는 요소

```html
<dfn id="sulfuric-acid">
  H<sub>2</sub>SO<sub>4</sub>
</dfn>

<article>
  <h2>2장. - 최적의 각도를 찾아라</h2>
  <img src="images/pyramid.png" alt="피라미드(최적의 각도를 찾아라)">
  <p>
    내용은 다음과 같습니다. -고대 이집트인들은 시키드(seked)라는 특별한 각도를 사용했다. -시키드는 현대 삼각함수의 코탄젠트(cotangent)와 그값이 같다.
    <mark>삼각함수</mark>와 코탄젠트라는 단어에 멈칫했을 수도 있지만, 이것을...
  </p>
  <span class="article-share">공유 <data value="0">0</data></span> &middot;
  <span class="article-comments">댓글 <data value="0">0</data></span> &middot;
  <cite><time datetime="2018-02-22">Feb 22. 2018</time> by sortie</cite>
</article>
```

## `time` 요소

`time` 요소는 평일과 시간 범위를 지원하지 않는다. 특정 날짜, 시간 및 시간대 데이터에 사용해야 한다. `time` 요소는 다음 포맷들만 지원한다.

* 유효한 날짜 문자열 : 2011-11-18
* 유효한 현지 날짜 및 시간 문자열 : 2011-11-18T14:54
* 유효한 주 문자열 : 2011-W47
* 유효한 기간 문자열 : PT4H18M3S
* 유효한 시간대 오프셋 문자열 : -08:00

하여 시간 정보를 마크업 할 때는 다음과 같이 작성해야 한다.

```html
<time>10:00</time>
```

그리고 UTC+09 기준 시간을 명시해야할 경우는 다음과 같이 작성할 수 있다.

```html
<time datetime="+09:00">10:00</time>
```
