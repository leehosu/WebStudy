# 🎢 Web Structure

---
- HTML은 페이지의 개별 부분을 정의할 뿐만 아니라 웹 사이트의 영역을 정의 하는데 사용되는 여러 Block 수준 요소를 갖고 있다.
- 기본 웹 사이트의 구조를 계획하고 나타내는 HTML을 작성하는 방법을 공부한다.
---

## Basic sections of a Document
- 웹 페이지는 서로 다르게 보일 수 있지만 페이지가 구조를 갖추어 내용을 표출한다.

    1. header
    - 일반적으로 상단에 큰 줄 및 로고가 있는 구조인데, 한 웹 페이지에서 다른 웹페이지로 정보가 전달되는 구조이다.
    2. Navigation bar
    - 일반적으로 메뉴 버튼, 링크 또는 탭으로 표시되며 사이트의 주요 section으로 연결한다. 
    - header와 마찬가지로 한 웹 페이지에서 다른 웹 페이지로 연결한다. 
    - header와 nav를 잘 성정하면 접근성이 좋다.
    3. Main Contents
    - 중앙에서 특정 웹 페이지의 고유 한 contents가 포함된 넓은 영역이며 페이지마다 다른 구조이다.
    4. side bar
    - 주변 정보, 링크, 광고등 일반적으로 Main Contents에 포함된 내용과 관련 있는 내용이 표출되는 구조이지만 Navigation bar와 중복 될 수 있다.
    5. footer
    - 일반적으로 작은 글씨로 저작권 고지 또는 연락처가 포함된 정보가 표출되는 페이지 하단의 스트립이다.
    - 콘텐츠에 빠르게 access할 수 있는 링크를 제공하여 SEO 목적으로 사용되기도 한다.
    
## HTML for Structuring Content
- HTML 코드에서 기능을 기반으로 Contents Section을 markup할 수 있다. 
- 올바른 작업에 올바른 구조 요소와 의미를 사용하지 않으면 많은 문제가 발생한다.

1. Header : `<header>`
2. Navigation bar : `<nav>`
3. Main Contents : `<main>` / 하위 section : `<article>`,`<section>`,`<div>`
4. Side bar : `<aside>` / 종종 내부에 배치됨 `<main>`
5. Footer : `<footer>`

