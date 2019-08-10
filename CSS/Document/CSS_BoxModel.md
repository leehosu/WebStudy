# 👨‍🔬 CSS Box Modeling

---
- CSS 상자 모델은 웹에서 레이아웃의 기초이다. 각 요소는 content, padding, margin등 서로 주위에 쌓여있는 사각형 상자로 표시된다.
- 브라우저는 웹 페이지 레이아웃을 렌더링 할 때 각 상자의 내용에 적용되는 스타일, 주변과 관련되어 있는 위치를 결정한다
---

## Box Attribute
- 문서 내의 모든 요소는 문서 레이아웃 내부의 사각형 상자로 구성되며, 특정 CSS 속성을 사용하여 크기와 레이아웃을 조정할 수 있다.

![BoxModel](../../image/css/box-model.png)

#### `width` and `height`
- `width`및 `height` 속성은 상자의 내용이 표시되는 영역인 content 상자의 폭과 높이를 설정한다.

#### `padding`
- `padding`은 content 상자의 바깥쪽 가장자리와 테두리 안쪽 가장자리 사이의 CSS 상자의 안쪽 여백을 의미한다.
- 4개의 면을 한번에 설정할 수 있고, `padding-top`, `padding-bottom`, `padding-right`, `padding-left`
로 각각 설정할 수 있다.

#### `border`
- `border` 속성은 padding의 바깥쪽 가장자리와 안쪽 가장 자리 사이에 위치한다.
- 기본적으로 `border`의 크기는 0으로 보이지 않지만 `border`의 두께, style 및 color를 설정하여 표시할 수 있다.

```css
border: 1px solid black;
```
- 위와 같이 `border` 속성은 한번에 4면에 설정 할 수 있다. 

-`border-top`, `border-bottom`, `border-rihgt`, `border-left` : 선택한 위치의 테두리의 두께, 스타일 및 색을 설정한다.

- `border-width`, `border-style`, `border-color` : 두께, 스타일, 색상만 개별적으로 설정하되, 모든 면에 설정한다.

- `border-top-width`,`border-top-style`,`border-top-color` : 테두리의 한 면에 3가지 특성 중 하나를 개별적으로 설정할 수 있다.

#### `margin`
- `margin`은 Box를 감싸고 레이아웃의 다른 box를 밀어 올린다.
- `margin`으로 모든 면에 여백을 설정할 수 있고, `margin-top`, `margin-right`,`margin-bottom`, `margin-left`로 각각에 여백을 줄 수 도 있다.