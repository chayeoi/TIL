# Flex 레이아웃

## 정렬

`space-evenly`는 `space-around`와 달리, 양 끝 공간을 flex item 간의 간격과 동일하게 설정한다. 이 속성 값은 현재 [모든 IE 버전에서 지원되지 않는 듯](https://caniuse.com/#feat=justify-content-space-evenly)하다.

## flex-grow

flex item의 너비에 대한 확대 인자(flex grow factor)를 지정한다. 기본값은 0이고 음수값은 무효하다. `flex-grow: 0;`이 아니고 flex item의 너비 합계가 flex container의 너비보다 작을 시, flex item들은 지정된 `width` 값을 무시한 채 flex container의 너비에 맞게 확대된다.

## flex-shrink

flex item의 너비에 대한 축소 인자(flex shrink factor)를 지정한다. 기본값은 1이고 음수값은 무효하다. 0을 지정하면 축소가 해제되어 원래의 너비를 유지한다. `flex-shrink: 0;`이 아니고 flex item의 너비 합계가 flex container의 너비보다 클 시, flex item들은 지정된 `width` 값을 무시한 채 flex container의 너비에 맞게 축소된다.

## flex-basis

flex item의 너비 기본값을 px, % 등의 단위로 지정한다. 기본값은 auto이다.

## Flex 아이템의 `z-index` 속성

`z-index` 속성은 기본적으로 위치를 갖는 요소에만 지정할 수 있는 속성이다. 그러나 예외적으로 flex 아이템의 경우, 위치를 갖지 않더라도 `z-index` 속성을 지정할 수 있다는 특징이 있다.

## 참고 {docsify-ignore}

* [CSS3 Flexbox Layout - Poiemaweb](https://poiemaweb.com/css3-flexbox)
* [Quick Tip: How z-index and Auto Margins Work in Flexbox - sitepoint](https://www.sitepoint.com/quick-tip-how-z-index-and-auto-margins-work-in-flexbox/)
