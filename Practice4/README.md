# CSS Box Model

CSS Box Model은 HTML 요소가 화면에 표시될 때 크기와 간격을 결정하는 원리입니다. 모든 요소는 사각형의 박스로 구성되며, 이 박스는 다음과 같은 4가지 구성 요소로 이루어집니다.

## Box Model 구성 요소

### 1. **Actual Content (내용 영역)**
   - 요소의 실제 콘텐츠가 표시되는 영역입니다.
   - `width`와 `height` 속성으로 크기를 지정할 수 있습니다.

### 2. **Padding (패딩)**
   - 콘텐츠와 테두리(`border`) 사이의 여백입니다.
   - 요소의 내부 간격을 조정하는 역할을 합니다.
   - `padding: 10px;`과 같이 설정하면 모든 방향의 패딩이 10px로 적용됩니다.

### 3. **Border (테두리)**
   - 요소를 감싸는 경계선입니다.
   - `border-width`, `border-style`, `border-color` 속성으로 조정할 수 있습니다.
   - 예: `border: 2px solid black;`

### 4. **Margin (마진)**
   - 요소와 다른 요소 사이의 간격을 설정하는 영역입니다.
   - `margin: 20px;`으로 설정하면 요소의 외부 여백이 20px로 적용됩니다.

## How to Calculate Box Size (박스 크기 계산)

기본적으로 요소의 총 크기는 다음과 같이 계산됩니다.

```
총 너비 = width + padding-left + padding-right + border-left + border-right + margin-left + margin-right
총 높이 = height + padding-top + padding-bottom + border-top + border-bottom + margin-top + margin-bottom
```

### 예제
```css
.box {
  width: 200px;
  height: 100px;
  padding: 10px;
  border: 5px solid black;
  margin: 20px;
}
```

위 스타일이 적용된 요소의 총 크기 계산:

- **너비**: `200px (content) + 10px * 2 (padding) + 5px * 2 (border) + 20px * 2 (margin) = 270px`
- **높이**: `100px (content) + 10px * 2 (padding) + 5px * 2 (border) + 20px * 2 (margin) = 170px`

## `box-sizing` 속성
CSS에서는 `box-sizing` 속성을 사용하여 박스 크기를 조정할 수 있습니다.

- `content-box` (기본값): `width`와 `height`는 **콘텐츠 크기**만 포함합니다.
- `border-box`: `width`와 `height`가 **패딩과 테두리를 포함한 크기**로 설정됩니다.

```css
.box {
  box-sizing: border-box;
}
```

`border-box`를 사용하면 `width`와 `height` 속성에 `padding`과 `border`가 포함되므로, 계산이 더 간단해집니다.

---

# CSS Display 속성  

CSS의 `display` 속성은 HTML 요소가 화면에 표시되는 방식을 결정합니다. 요소의 기본적인 흐름을 제어하며, 다양한 값들을 사용하여 배치를 조정할 수 있습니다.  

## Block Element (블록 요소)  
블록 요소는 기본적으로 새로운 줄에서 시작하며, 가능한 전체 너비를 차지합니다.  

### 특징  
- 기본적으로 `width: 100%`를 차지함  
- 새로운 줄에서 시작됨  
- `height`, `width`, `margin`, `padding` 등을 자유롭게 조절 가능  

### 대표적인 블록 요소  
- `<div>`, `<p>`, `<h1>` ~ `<h6>`, `<ul>`, `<ol>`, `<li>`, `<section>`, `<article>` 등  

### 예제  
```css
.block-element {
  display: block;
  width: 200px;
  height: 100px;
  background-color: lightblue;
}
```

```html
<div class="block-element">블록 요소</div>
<p class="block-element">이것도 블록 요소입니다.</p>
```

## Inline Element (인라인 요소)  
인라인 요소는 새로운 줄에서 시작하지 않으며, 콘텐츠 크기만큼만 공간을 차지합니다.  

### 특징  
- 새로운 줄에서 시작되지 않음  
- 콘텐츠 크기만큼만 공간을 차지함  
- `width`와 `height` 속성을 직접 조절할 수 없음  
- `margin`과 `padding`을 수직 방향으로 적용하기 어려움  

### 대표적인 인라인 요소  
- `<span>`, `<a>`, `<strong>`, `<em>`, `<img>`, `<label>`, `<abbr>` 등  

### 예제  
```css
.inline-element {
  display: inline;
  background-color: yellow;
}
```

```html
<span class="inline-element">인라인 요소</span>
<a class="inline-element">이것도 인라인 요소입니다.</a>
```

## Display 속성 값  
### 1. `display: none;`  
- 요소를 화면에서 완전히 제거합니다.  
- 해당 요소는 DOM에는 존재하지만, 렌더링되지 않으며 공간도 차지하지 않습니다.  

```css
.hidden {
  display: none;
}
```

```html
<div class="hidden">이 요소는 보이지 않습니다.</div>
```

### 2. `display: block;`  
- 요소를 블록 요소로 설정합니다.  

```css
.block {
  display: block;
}
```

```html
<span class="block">이 요소는 블록 요소로 변환되었습니다.</span>
```

### 3. `display: inline;`  
- 요소를 인라인 요소로 설정합니다.  

```css
.inline {
  display: inline;
}
```

```html
<div class="inline">이 요소는 인라인 요소로 변환되었습니다.</div>
```

### 4. `display: inline-block;`  
- 인라인 요소처럼 동작하지만 `width`, `height`, `margin`, `padding`을 적용할 수 있음  

```css
.inline-block {
  display: inline-block;
  width: 100px;
  height: 50px;
  background-color: lightgreen;
}
```

```html
<div class="inline-block">이 요소는 inline-block입니다.</div>
```

## Visibility 속성  
`visibility` 속성은 요소의 가시성을 조정합니다.  

### 1. `visibility: visible;`  
- 기본값이며, 요소가 보입니다.  

```css
.visible {
  visibility: visible;
}
```

```html
<div class="visible">이 요소는 보입니다.</div>
```

### 2. `visibility: hidden;`  
- 요소를 숨기지만, 해당 요소가 차지하는 공간은 유지됩니다.  

```css
.hidden {
  visibility: hidden;
}
```

```html
<div class="hidden">이 요소는 숨겨졌지만 공간은 차지합니다.</div>
```

### `display: none;` vs `visibility: hidden;` 차이  
| 속성 | 요소가 화면에서 보이는가? | 공간을 차지하는가? |
|------|-----------------|---------------|
| `display: none;` | No | No |
| `visibility: hidden;` | No | Yes |

이제 `display` 속성을 활용하여 레이아웃을 자유롭게 조정할 수 있습니다!

---

# CSS Placement (배치)  

CSS에서 요소를 배치하는 방식은 `position` 속성과 `float`, `z-index` 등을 활용하여 결정됩니다. 위치를 조정할 때 `top`, `bottom`, `left`, `right` 속성을 사용할 수 있지만, `position` 속성이 먼저 설정되어 있어야 합니다.  

## 1. Positioning (위치 지정)  

CSS의 `position` 속성은 요소의 배치 방법을 결정하는 속성입니다. `position` 속성을 사용하면 요소를 문서 흐름에서 벗어나 원하는 위치에 배치할 수 있습니다.

## `position`의 속성 값

### 1. `static`
- 기본값이며, 요소가 문서의 일반적인 흐름에 따라 배치됩니다.
- `top`, `left`, `right`, `bottom`, `z-index` 속성이 적용되지 않습니다.

```css
.element {
    position: static;
}
```

### 2. `relative`
- 요소가 원래 위치를 기준으로 상대적으로 이동합니다.
- `top`, `left`, `right`, `bottom` 값을 사용하여 이동할 수 있습니다.
- 원래 위치가 유지되므로, 다른 요소들은 영향을 받지 않습니다.

```css
.element {
    position: relative;
    top: 10px;
    left: 20px;
}
```

### 3. `absolute`
- 요소가 문서 흐름에서 제거되고, 가장 가까운 `relative`, `absolute`, `fixed` 조상 요소를 기준으로 배치됩니다.
- 조상 요소 중 `position`이 설정되지 않은 경우, `body`를 기준으로 배치됩니다.

```css
.parent {
    position: relative;
}

.child {
    position: absolute;
    top: 50px;
    left: 100px;
}
```

### 4. `fixed`
- 요소가 뷰포트를 기준으로 고정됩니다.
- 스크롤을 하더라도 요소의 위치가 변하지 않습니다.

```css
.element {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    background-color: black;
    color: white;
}
```

### 5. `sticky`
- 스크롤 위치에 따라 `relative`와 `fixed` 속성이 동적으로 변합니다.
- 특정 스크롤 위치에 도달하기 전에는 `relative`, 도달 후에는 `fixed`처럼 동작합니다.

```css
.element {
    position: sticky;
    top: 50px;
    background-color: yellow;
}
```

## 정리
| 속성 값  | 설명 |
|----------|------------------------------------------------|
| `static`  | 기본값, 일반적인 문서 흐름을 따름 |
| `relative` | 원래 위치를 기준으로 상대적으로 이동 |
| `absolute` | 문서 흐름에서 제거되고 조상 요소를 기준으로 배치 |
| `fixed` | 뷰포트를 기준으로 고정, 스크롤해도 위치 유지 |
| `sticky` | 특정 스크롤 위치에서 `fixed`처럼 동작 |


## 2. Float (부유 요소)  

`float` 속성은 요소를 좌우로 띄워서 배치할 때 사용됩니다.  

### `float` 값  
- `left` : 요소를 왼쪽으로 띄움  
- `right` : 요소를 오른쪽으로 띄움  
- `none` : 기본값 (float 해제)  

```css
.float-left {
  float: left;
  width: 100px;
  height: 100px;
  background-color: orange;
}

.float-right {
  float: right;
  width: 100px;
  height: 100px;
  background-color: green;
}
```

```html
<div class="float-left">왼쪽 배치</div>
<div class="float-right">오른쪽 배치</div>
```

### `clear` 속성  
- `float`으로 띄운 요소 아래에서 영향을 받지 않도록 설정하는 속성입니다.  
- `clear: both;`를 사용하면 `float` 요소가 양쪽에서 해제됩니다.  

```css
.clear {
  clear: both;
}
```

```html
<div class="clear">float 해제됨</div>
```

## 3. Z-Index (쌓임 순서)  

`z-index` 속성은 요소가 다른 요소와 겹칠 때 **위쪽(앞쪽) 또는 아래쪽(뒤쪽)으로 배치하는 순서**를 결정합니다.  

### `z-index` 값  
- 숫자가 클수록 **위쪽(앞쪽)** 에 배치됨  
- 기본값은 `auto` (HTML 순서대로 배치됨)  
- `position` 속성이 `static`이 아닌 경우에만 동작함  

```css
.box1 {
  position: absolute;
  top: 50px;
  left: 50px;
  width: 100px;
  height: 100px;
  background-color: blue;
  z-index: 1;
}

.box2 {
  position: absolute;
  top: 70px;
  left: 70px;
  width: 100px;
  height: 100px;
  background-color: red;
  z-index: 2; /* 더 높은 값이므로 box1 위에 표시됨 */
}
```

```html
<div class="box1">Box 1</div>
<div class="box2">Box 2</div>
```