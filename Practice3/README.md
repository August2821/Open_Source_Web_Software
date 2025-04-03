# CSS란 무엇인가?

CSS(Cascading Style Sheets)는 웹 페이지의 스타일과 레이아웃을 정의하는 스타일 시트 언어이다. HTML 등의 마크업 언어와 함께 사용되며, 웹 페이지의 디자인을 개선하고 일관된 스타일을 적용하는 데 사용된다.

## Cascading Style Sheets란?

CSS의 풀네임인 **Cascading Style Sheets**에서 "Cascading"은 스타일이 여러 계층에서 적용될 수 있으며, 특정 규칙이 우선순위를 갖는 방식을 의미한다. 즉, 스타일 규칙이 여러 곳에서 정의되었을 때 어떤 규칙이 최종적으로 적용될지를 결정하는 메커니즘이 존재한다.

## CSS의 주요 기능

- **레이아웃 및 디자인 조정**: 요소의 크기, 위치, 색상, 배경, 여백 등을 조정할 수 있다.
- **반응형 웹 디자인**: 다양한 화면 크기에 맞춰 스타일을 조정할 수 있다.
- **코드의 재사용성 증가**: CSS 파일을 분리하여 여러 HTML 문서에서 공통 스타일을 적용할 수 있다.
- **웹 접근성 향상**: 스타일을 적절히 조정하여 사용자 경험을 개선할 수 있다.

## CSS의 기본 문법

```css
선택자 {
  속성: 값;
}
```

예제:
```css
p {
  color: blue;
  font-size: 16px;
}
```

이 코드는 모든 `<p>` 요소의 글자 색상을 파란색으로 지정하고, 글자 크기를 16px로 설정한다.

---

# CSS 선택자(Selector)

CSS 선택자는 HTML 요소를 선택하여 스타일을 적용하는 데 사용된다. 선택자에는 다양한 유형이 있으며, 각각 특정한 방식으로 요소를 선택할 수 있다.

## 1. 기본 선택자

### Type 선택자 (태그 선택자)
특정 HTML 태그 이름을 사용하여 해당 요소를 선택한다.
```css
p {
  color: blue;
}
```
위 코드는 모든 `<p>` 요소의 글자 색상을 파란색으로 변경한다.

### ID 선택자
`#` 기호를 사용하여 특정 `id` 속성을 가진 요소를 선택한다.
```css
#header {
  background-color: lightgray;
}
```
위 코드는 `id="header"`인 요소의 배경색을 연한 회색으로 변경한다.

### Class 선택자
`.` 기호를 사용하여 특정 `class` 속성을 가진 요소를 선택한다.
```css
.button {
  font-weight: bold;
}
```
위 코드는 `class="button"`을 가진 요소의 글자를 굵게 만든다.

### Universal 선택자 (전체 선택자)
`*` 기호를 사용하여 모든 요소를 선택한다.
```css
* {
  margin: 0;
  padding: 0;
}
```
위 코드는 모든 요소의 `margin`과 `padding`을 0으로 설정한다.

## 2. 그룹 선택자

### Grouping 선택자 (그룹 선택자)
쉼표(`,`)를 사용하여 여러 요소를 한 번에 선택할 수 있다.
```css
h1, h2, h3 {
  color: green;
}
```
위 코드는 `<h1>`, `<h2>`, `<h3>` 요소의 글자 색상을 초록색으로 변경한다.

### Descendant 선택자 (하위 선택자)
공백을 사용하여 특정 요소의 모든 하위 요소를 선택한다.
```css
div p {
  color: red;
}
```
위 코드는 `<div>` 내부의 모든 `<p>` 요소의 글자 색상을 빨간색으로 변경한다.

### Child 선택자 (자식 선택자)
`>` 기호를 사용하여 특정 요소의 직계 자식만 선택한다.
```css
div > p {
  color: blue;
}
```
위 코드는 `<div>`의 **직계 자식** `<p>` 요소만 선택하여 글자 색상을 파란색으로 변경한다.

### Next Sibling 선택자 (인접 형제 선택자)
`+` 기호를 사용하여 특정 요소의 **바로 다음 형제 요소**를 선택한다.
```css
h1 + p {
  font-style: italic;
}
```
위 코드는 `<h1>` 다음에 오는 `<p>` 요소의 글꼴을 기울인다.

### General Sibling 선택자 (일반 형제 선택자)
`~` 기호를 사용하여 특정 요소의 **모든 형제 요소**를 선택한다.
```css
h1 ~ p {
  color: gray;
}
```
위 코드는 `<h1>` 이후의 모든 `<p>` 요소의 글자 색상을 회색으로 변경한다.

## 3. 속성 선택자 (Attribute Selector)

### 특정 속성이 있는 요소 선택
```css
input[type="text"] {
  border: 1px solid black;
}
```
위 코드는 `type="text"`인 `<input>` 요소에 테두리를 추가한다.

### 특정 속성값을 포함하는 요소 선택
```css
a[href*="example"] {
  color: orange;
}
```
위 코드는 `href` 속성에 `"example"`이 포함된 모든 `<a>` 요소의 글자 색상을 주황색으로 변경한다.

## 4. 가상 클래스 선택자 (Pseudo-Class)

### 링크 상태 선택자
```css
a:link {
  color: blue;
}
a:visited {
  color: purple;
}
a:hover {
  text-decoration: underline;
}
a:active {
  color: red;
}
```
- `:link` → 방문하지 않은 링크
- `:visited` → 방문한 링크
- `:hover` → 마우스를 올린 상태
- `:active` → 클릭한 상태

### 위치 기반 선택자
```css
li:nth-child(2) {
  color: red;
}
li:first-child {
  font-weight: bold;
}
li:last-child {
  font-style: italic;
}
```
- `:nth-child(n)` → n번째 자식을 선택
- `:first-child` → 첫 번째 자식 선택
- `:last-child` → 마지막 자식 선택

## 5. 가상 요소 선택자 (Pseudo-Element)

### `::before` & `::after`
```css
p::before {
  content: "★ ";
}
p::after {
  content: " ★";
}
```
- `::before` → 요소 앞에 콘텐츠 추가
- `::after` → 요소 뒤에 콘텐츠 추가

### `::first-letter` & `::first-line`
```css
p::first-letter {
  font-size: 2em;
  color: red;
}
p::first-line {
  font-weight: bold;
}
```
- `::first-letter` → 첫 글자 스타일 변경
- `::first-line` → 첫 줄 스타일 변경

### `::marker` (목록 기호 스타일링)
```css
li::marker {
  color: blue;
  font-size: 1.2em;
}
```
- `::marker` → 리스트 아이템의 마커(`•`, `1.` 등) 스타일 변경

### `::selection` (선택된 텍스트 스타일링)
```css
::selection {
  background-color: yellow;
  color: black;
}
```
- `::selection` → 사용자가 선택한 텍스트의 스타일 변경

## 6. 정리

| 선택자 유형 | 설명 |
|------------|------|
| **Type** | 특정 태그 이름으로 선택 |
| **ID** | 특정 `id` 값을 가진 요소 선택 (`#id`) |
| **Class** | 특정 `class` 값을 가진 요소 선택 (`.class`) |
| **Universal** | 모든 요소 선택 (`*`) |
| **Grouping** | 여러 요소를 동시에 선택 (`h1, h2, h3`) |
| **Descendant** | 특정 요소 내부의 모든 자손 선택 (`div p`) |
| **Child** | 특정 요소의 직계 자식 선택 (`div > p`) |
| **Next Sibling** | 특정 요소의 다음 형제 선택 (`h1 + p`) |
| **General Sibling** | 특정 요소의 모든 형제 선택 (`h1 ~ p`) |
| **Attribute** | 특정 속성을 가진 요소 선택 (`input[type="text"]`) |
| **Pseudo-Class** | 요소의 특정 상태 선택 (`:hover`, `:first-child`, `:nth-child(n)`) |
| **Pseudo-Element** | 요소 내부의 특정 부분 선택 (`::before`, `::first-letter`, `::selection`) |

CSS 선택자는 웹 페이지의 스타일을 세밀하게 조정하는 강력한 도구이며, 다양한 조합을 통해 복잡한 디자인 요구를 충족할 수 있다.

---

# CSS 스타일 적용 방법과 우선순위

CSS는 여러 가지 방법으로 웹 페이지에 스타일을 적용할 수 있으며, 각각의 방법은 특정한 **우선순위(Priority)** 를 가진다. 또한 **특정성(Specificity)** 과 **계층 구조(Hierarchy)** 를 통해 최종적으로 어떤 스타일이 적용될지 결정된다.

## 1. CSS 스타일 적용 방법

### 1.1 External Style Sheet (외부 스타일 시트)
별도의 `.css` 파일을 만들어 `<link>` 태그로 연결하여 스타일을 적용하는 방법이다.

- **장점**:
  - 여러 HTML 문서에서 같은 스타일을 공유할 수 있어 유지보수가 용이함.
  - HTML과 스타일을 분리하여 코드 가독성을 높일 수 있음.
- **단점**:
  - 별도의 파일을 불러와야 하므로 네트워크 속도에 영향을 받을 수 있음.

```html
<!-- HTML 문서에서 외부 CSS 파일을 연결 -->
<link rel="stylesheet" href="styles.css">
```

```css
/* styles.css */
p {
  color: blue;
  font-size: 16px;
}
```

### 1.2 Internal Style Sheet (내부 스타일 시트)
HTML 문서 내 `<style>` 태그를 사용하여 스타일을 적용하는 방법이다.

- **장점**:
  - 외부 CSS 파일이 필요하지 않으므로 빠르게 로드됨.
  - 특정 HTML 파일에만 스타일을 적용할 때 유용함.
- **단점**:
  - 여러 HTML 파일에서 동일한 스타일을 사용할 경우 중복 작성해야 함.
  - HTML과 CSS가 섞여 가독성이 떨어질 수 있음.

```html
<!DOCTYPE html>
<html lang="ko">
<head>
  <style>
    p {
      color: green;
      font-size: 18px;
    }
  </style>
</head>
<body>
  <p>이것은 내부 스타일 시트입니다.</p>
</body>
</html>
```

### 1.3 Inline Style (인라인 스타일)
HTML 요소의 `style` 속성을 사용하여 직접 스타일을 적용하는 방법이다.

- **장점**:
  - 특정 요소에만 빠르게 스타일을 적용할 수 있음.
  - 외부 CSS 파일 없이 간단한 수정이 가능함.
- **단점**:
  - 코드가 지저분해지고 유지보수가 어려움.
  - 스타일을 여러 요소에 적용하려면 중복 코드가 발생함.

```html
<p style="color: red; font-size: 20px;">이것은 인라인 스타일입니다.</p>
```

### 1.4 Web Browser Default Value (웹 브라우저 기본 스타일)
웹 브라우저는 HTML 요소에 기본 스타일을 적용한다. 예를 들어:

```css
body {
  margin: 8px;
}

h1 {
  font-size: 2em;
  font-weight: bold;
}

p {
  margin-top: 16px;
  margin-bottom: 16px;
}
```

기본 스타일을 제거하고 싶은 경우 다음과 같이 `reset` 또는 `normalize` CSS를 사용할 수 있다.

```css
/* 기본 스타일 제거 */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
```

## 2. CSS 우선순위(Priority)와 특정성(Specificity)

CSS 스타일이 여러 곳에서 정의되었을 때 어떤 스타일이 적용될지를 결정하는 요소는 **우선순위(Priority)**, **특정성(Specificity)**, 그리고 **계층 구조(Hierarchy)** 이다.

### 2.1 우선순위 (Priority)
아래 순서대로 스타일이 적용되며, **아래에 위치할수록 높은 우선순위를 가진다.**
1. **웹 브라우저 기본 스타일** (가장 낮음)
2. **외부 스타일 시트 (External)**
3. **내부 스타일 시트 (Internal)**
4. **인라인 스타일 (Inline)**
5. **`!important` 키워드 사용** (가장 높음)

```css
p {
  color: blue !important;  /* 최우선 적용 */
}

p {
  color: green;  /* 적용되지 않음 */
}
```

### 2.2 특정성 (Specificity)
특정성이 높을수록 우선적으로 적용된다. 특정성은 아래 기준으로 점수를 계산할 수 있다.

| 선택자 유형 | 특정성 점수 |
|------------|------------|
| 태그 선택자 (`p`, `div`) | 1점 |
| 클래스 선택자 (`.class`) | 10점 |
| ID 선택자 (`#id`) | 100점 |
| 인라인 스타일 (`style="color: red;"`) | 1000점 |
| `!important` 키워드 | 무조건 최우선 |

#### 특정성 예제:
```css
p { color: black; }          /* 특정성: 1 */
.class-name { color: blue; } /* 특정성: 10 */
#id-name { color: red; }     /* 특정성: 100 */
```

적용 결과:
- `#id-name`이 가장 높은 특정성을 가지므로 **빨간색**이 적용됨.

### 2.3 계층 구조 (Hierarchy)
CSS는 **계층적(Cascading)** 으로 적용되며, 동일한 특정성을 가진 스타일이 여러 개 있다면 **나중에 작성된 스타일이 적용된다.**

```css
p {
  color: black;
}

p {
  color: green; /* 마지막에 선언되어 적용됨 */
}
```

결과적으로 **초록색**이 적용된다.

## 3. 정리

| 개념 | 설명 |
|------|------|
| **External Style Sheet** | 별도의 `.css` 파일에서 스타일을 정의하고 `<link>` 태그로 불러옴 |
| **Internal Style Sheet** | HTML 문서 내부의 `<style>` 태그에 스타일을 작성 |
| **Inline Style** | 개별 HTML 요소에 `style` 속성을 사용하여 직접 스타일 지정 |
| **Web Browser Default Value** | 브라우저가 기본적으로 적용하는 스타일 |
| **Priority (우선순위)** | `!important` > 인라인 스타일 > 내부 스타일 시트 > 외부 스타일 시트 > 브라우저 기본값 |
| **Specificity (특정성)** | `ID (100점) > Class (10점) > 태그 (1점)` |
| **Hierarchy (계층 구조)** | 동일한 특정성을 가진 스타일이 여러 개 있다면, **나중에 선언된 스타일이 적용됨** |

이러한 개념을 이해하면 CSS를 더욱 정밀하게 제어할 수 있으며, 스타일 충돌을 방지할 수 있다.