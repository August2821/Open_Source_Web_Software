# Responsive Design

## 개요

**Responsive Web Design(반응형 웹 디자인)**은 모든 기기에서 웹 페이지가 보기 좋게 표시되도록 만드는 디자인 기법입니다.

- 반응형 웹 디자인은 다양한 화면 크기(스마트폰부터 데스크톱까지)에 자동으로 맞춰지는 웹사이트를 만듭니다.
- 오직 **HTML과 CSS**만을 사용하여 구현되며, **프로그램이나 JavaScript가 아닙니다**.

## 핵심 원칙 (Key Principles)

### 1. Fluid Layouts
- **유동적인 레이아웃**을 사용하여, 요소들이 고정된 픽셀이 아닌 상대 단위(% 등)로 크기를 조절합니다.
- 다양한 화면 크기에 자연스럽게 적응합니다.

### 2. Flexible Images and Media
- 이미지와 비디오가 **자신을 포함하는 요소의 크기에 맞춰 조정**되며, 넘치거나 비율이 깨지지 않습니다.

### 3. Media Queries
- **미디어 쿼리(CSS 기능)**를 사용하여, 화면의 크기, 해상도, 방향 등에 따라 스타일을 다르게 적용합니다.
```css
@media (max-width: 768px) {
  body {
    font-size: 14px;
  }
}
```

### 4. Mobile-First Design
- **모바일 화면을 우선적으로 설계**하고, 점진적으로 큰 화면에 맞춰 디자인을 확장합니다.

### 5. Viewport Meta Tag
- HTML에 다음 메타 태그를 추가하여 **모바일 브라우저의 화면 크기를 제어**합니다.
```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

### 6. Touch-Friendly Design
- 버튼, 링크 등의 **인터랙티브 요소는 충분히 크고 간격이 넓어야** 하며, **터치 조작에 적합**해야 합니다.

## 왜 반응형 디자인인가?

1. **더 나은 사용자 경험**  
   - 모든 기기에서 일관되고 편리한 사용성을 제공합니다.

2. **비용 효율적인 선택**  
   - 여러 기기에 맞춘 별도 사이트를 만들 필요 없이 하나의 디자인으로 유지 가능합니다.

3. **SEO 관점에서 더 나은 가시성**  
   - 검색 엔진은 반응형 웹을 선호합니다.

4. **관리의 용이성**  
   - 하나의 코드베이스만 관리하면 됩니다.

5. **유연성 제공**  
   - 다양한 디바이스에 대응 가능하며, 새로운 기기가 나와도 쉽게 확장 가능합니다.

6. **높은 전환율 기대 가능**  
   - 사용자 만족도가 높아지면 구매, 신청 등의 전환율이 향상됩니다.

7. **빠른 로딩 속도로 더 많은 트래픽 유입**  
   - 최적화된 콘텐츠로 로딩 시간이 짧아지고, 사용자 유입이 증가합니다.

---

# CSS Responsive Design

## 1. CSS Flexbox란?

**Flexbox**는 **Flexible Box Layout Module**의 줄임말로, HTML 요소들을 **행(row) 또는 열(column)**로 유연하게 배치할 수 있도록 해주는 CSS 레이아웃 방법입니다.

### 기존 레이아웃 방식

Flexbox가 도입되기 전에는 다음 4가지 레이아웃 방식이 사용되었습니다:

- **Block**: 웹 페이지의 섹션에 사용  
- **Inline**: 텍스트 레이아웃에 사용  
- **Table**: 2차원 표 데이터를 표현  
- **Positioned**: 요소의 위치를 명시적으로 설정  

> Flexbox는 **모든 최신 브라우저에서 지원**됩니다.

## 2. Flexbox의 기본 구조

Flexbox는 항상 다음 두 가지 요소로 구성됩니다:

- **Flex Container**: 부모 `<div>` 요소
- **Flex Items**: 컨테이너 내부의 자식 요소들

Flexbox 사용을 시작하려면 **`display` 속성을 `flex`로 설정**해야 합니다.

```css
.container {
  display: flex;
}
```

## 3. Flexbox 예제

### 문제 상황 (Flexbox 미사용 시):
- `Logo`, `Menu`, `Login`을 같은 줄에 배치하려면 float, margin 조정 등 복잡한 작업 필요
- 반응형 디자인도 따로 고려해야 함

```html
<!-- float 방식으로 정렬 -->
<div class="header">
  <div class="logo">Logo</div>
  <div class="menu">Menu</div>
  <div class="login">Login</div>
</div>
```

```css
.header {
  overflow: hidden;
}

.logo, .menu, .login {
  float: left;
  margin: 0 10px;
  line-height: 60px;
}

.login {
  float: right;
}
```

- **문제점**:
  - float으로 인해 clearfix 필요
  - margin으로 수동 조정 필요
  - 모바일 대응하려면 따로 미디어 쿼리 작성 필요

### Flexbox 사용 시:
- 코드가 간결하고 최소화됨
- 자동 수직 정렬 가능
- **미디어 쿼리만 추가하면 반응형 대응 용이**

```html
<!-- Flexbox로 간단하게 정렬 -->
<div class="header">
  <div class="logo">Logo</div>
  <div class="menu">Menu</div>
  <div class="login">Login</div>
</div>
```

```css
.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  height: 60px;
  padding: 0 20px;
  background-color: #f0f0f0;
}
```

- **장점**:
  - `display: flex` 한 줄로 레이아웃 정렬
  - `align-items: center`로 세로 중앙 정렬
  - 반응형은 미디어 쿼리로 간단하게 확장 가능

```css
@media (max-width: 600px) {
  .header {
    flex-direction: column;
    align-items: flex-start;
  }
}
```

## 4. Flex Container 관련 속성

| 속성 | 설명 |
|------|------|
| `flex-direction` | 행(row) 또는 열(column) 방향 설정 |
| `flex-wrap` | 요소가 한 줄에 넘칠 경우 줄바꿈 여부 설정 |
| `flex-flow` | `flex-direction`과 `flex-wrap`을 한 번에 설정 |
| `justify-content` | 주 축(main axis) 정렬 방식 설정 |
| `align-items` | 교차 축(cross axis) 정렬 방식 설정 |
| `align-content` | 여러 줄 정렬 방식 설정 |
| `gap`, `row-gap`, `column-gap` | 요소 간 간격 설정 |

### 예시
```css
.container {
  display: flex;
  flex-direction: row;
  flex-wrap: nowrap;
  justify-content: space-between;
  align-items: center;
  gap: 16px;
}
```

## 5. Flex Item 관련 속성

| 속성 | 설명 |
|------|------|
| `order` | 요소의 순서 변경 |
| `flex-grow` | 남은 공간을 얼마나 차지할지 설정 |
| `flex-shrink` | 공간 부족 시 줄어드는 비율 설정 |
| `flex-basis` | 기본 크기 설정 |
| `flex` | `flex-grow`, `flex-shrink`, `flex-basis`를 한 번에 설정 |
| `align-self` | 개별 요소의 교차 축 정렬 설정 |

```html
<div class="container">
  <div class="item item1">1</div>
  <div class="item item2">2</div>
  <div class="item item3">3</div>
</div>
```

```css
.container {
  display: flex;
  height: 100px;
}

.item {
  padding: 10px;
  color: white;
  text-align: center;
}

/* flex item 속성 적용 */
.item1 {
  background-color: crimson;
  order: 2;            /* 순서 변경 */
  flex-grow: 1;        /* 남은 공간 비율 */
}

.item2 {
  background-color: royalblue;
  order: 1;
  flex: 2 1 100px;     /* grow, shrink, basis */
}

.item3 {
  background-color: seagreen;
  order: 3;
  align-self: flex-end; /* 개별 정렬 */
}
```

- `.item1`은 두 번째에 표시되고, `flex-grow: 1`로 남은 공간을 일부 차지함
- `.item2`는 첫 번째에 오며, `flex: 2 1 100px`로 2배 성장, 줄어들 수 있고 기본 크기는 100px
- `.item3`은 세 번째에 오며, 컨테이너의 아래쪽으로 정렬됨 (`align-self`)

## 6. 미디어 쿼리(Media Queries)

미디어 쿼리는 기기의 화면 크기, 해상도, 방향 등에 따라 **다른 스타일을 적용**할 수 있는 CSS 기능입니다.

### 예시
```css
@media (max-width: 768px) {
  .container {
    flex-direction: column;
  }
}
```

- 데스크탑에서는 요소가 **수평(horizontal)**으로 배치됨
- 모바일에서는 요소가 **수직(vertical)**으로 쌓임

## 7. Viewport란?

**Viewport**는 사용자가 웹 페이지에서 **볼 수 있는 영역**입니다.

HTML5에서는 Viewport를 제어할 수 있는 `<meta>` 태그를 도입했습니다.

### 예시
```html
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
```

- `width=device-width`: 기기의 화면 너비에 맞춤  
- `initial-scale=1.0`: 페이지 최초 로딩 시 확대/축소 배율 설정

## 8. 반응형 이미지 (Responsive Images)

- `width`를 **퍼센트(%)**로 설정하고, `height`는 **auto**로 지정하면 이미지가 부모 요소 크기에 맞게 조절됩니다.

### 예시
```css
img {
  width: 100%;
  height: auto;
}
```

- 미디어 쿼리를 사용하여 **기기별로 다른 이미지**를 보여줄 수도 있습니다.
- HTML5의 `<picture>` 요소를 사용하면 **화면 조건에 따라 이미지 리소스를 유연하게 지정**할 수 있습니다.

### 예시
```html
<picture>
  <source media="(max-width: 768px)" srcset="small.jpg">
  <source media="(min-width: 769px)" srcset="large.jpg">
  <img src="default.jpg" alt="Responsive image">
</picture>
```

---

# Bootstrap Tutorial

## 1. Bootstrap이란?

- **Bootstrap**은 웹 개발을 더 쉽고 빠르게 할 수 있도록 도와주는 **무료 프론트엔드 프레임워크**입니다.
- 반응형 디자인을 쉽게 구현할 수 있도록 다양한 도구를 제공합니다.
- HTML 및 CSS 기반의 다양한 **미리 정의된 클래스**를 제공하여 웹 요소를 쉽게 구성할 수 있습니다.
  - 타이포그래피, 폼, 버튼, 테이블, 내비게이션, 모달, 이미지 등 다양한 UI 요소 구성 가능

## 2. Bootstrap 요소

### 2-1. 타이포그래피 클래스

| 클래스 | 설명 |
|--------|------|
| `.text-left` | 텍스트를 왼쪽 정렬 |
| `.text-center` | 텍스트를 가운데 정렬 |
| `.text-right` | 텍스트를 오른쪽 정렬 |
| `.text-justify` | 텍스트 양쪽 정렬 |
| `.text-nowrap` | 텍스트 줄바꿈 방지 |
| `.text-lowercase` | 텍스트 소문자 변환 |
| `.text-uppercase` | 텍스트 대문자 변환 |
| `.text-capitalize` | 각 단어의 첫 글자 대문자 변환 |

### 2-2. 이미지 모양 클래스

| 클래스 | 설명 |
|--------|------|
| `.img-rounded` | 둥근 모서리 이미지 |
| `.img-circle` | 원형 이미지 |
| `.img-thumbnail` | 테두리가 있는 썸네일 이미지 |

> CSS로도 원형 이미지를 만들 수 있습니다: `border-radius: 50%`

**예시:**

```html
<img src="sample.jpg" class="img-circle" alt="Circle Image">
```

### 2-3. 버튼 클래스

#### 버튼 스타일

| 클래스 | 설명 |
|--------|------|
| `.btn` | 기본 버튼 |
| `.btn-default` | 회색 기본 버튼 |
| `.btn-primary` | 파란색 주요 버튼 |
| `.btn-success` | 녹색 성공 버튼 |
| `.btn-info` | 파란색 정보 버튼 |
| `.btn-warning` | 주황색 경고 버튼 |
| `.btn-danger` | 빨간색 위험 버튼 |
| `.btn-link` | 링크 버튼 스타일 |

#### 버튼 크기

| 클래스 | 설명 |
|--------|------|
| `.btn-lg` | 큰 버튼 |
| `.btn-sm` | 작은 버튼 |
| `.btn-xs` | 매우 작은 버튼 |

#### 블록 버튼

- `.btn-block`: 전체 너비를 차지하는 블록 형태 버튼

#### 활성/비활성 버튼

- `.active`: 활성 상태 버튼
- `.disabled`: 비활성 상태 버튼

```html
<button class="btn btn-primary btn-lg">큰 파란 버튼</button>
```

## 3. Collapse (접기 기능)

- 많은 내용을 접었다 펼 수 있는 유용한 구성 요소입니다.
- 구성 요소:
  - `.collapse` 클래스: 접기 가능 요소
  - `data-toggle="collapse"` 속성: 클릭 시 동작
  - `data-target="#id"` 속성: 어떤 요소를 접을지 지정

**예시:**

```html
<button data-toggle="collapse" data-target="#demo" class="btn btn-info">토글</button>
<div id="demo" class="collapse">
  여기에 접히는 내용이 들어갑니다.
</div>
```

## 4. Glyphicons (아이콘)

- Bootstrap은 260개의 아이콘(Glyphicons)을 제공합니다.

**예시 아이콘 클래스**:

```html
<span class="glyphicon glyphicon-envelope"></span> 메일
<span class="glyphicon glyphicon-print"></span> 프린트
<span class="glyphicon glyphicon-search"></span> 검색
<span class="glyphicon glyphicon-download"></span> 다운로드
```

## 5. Bootstrap Grid (그리드 시스템)

- 반응형 레이아웃을 위한 시스템
- 한 줄에 최대 12개의 컬럼까지 배치 가능
- 화면 크기에 따라 컬럼을 조절할 수 있도록 도와줌

### 기본 구조

```html
<div class="row">
  <div class="col-md-6">절반 너비</div>
  <div class="col-md-6">절반 너비</div>
</div>
```

### 그리드 클래스 종류

| 클래스 접두사 | 사용 환경 |
|---------------|------------|
| `xs` | 휴대폰 (<768px) |
| `sm` | 태블릿 (≥768px) |
| `md` | 노트북 (≥992px) |
| `lg` | 데스크탑 (≥1200px) |

## 6. 반응형 이미지

- `.img-responsive` 클래스 사용 시, 이미지가 부모 요소에 맞춰 자동 조절됨

```html
<img src="image.jpg" class="img-responsive" alt="반응형 이미지">
```

## 7. Bootstrap 내비게이션 바

### 기본 내비게이션 바 만들기

```html
<nav class="navbar navbar-default">
  <div class="container-fluid">
    <div class="navbar-header">
      <a class="navbar-brand" href="#">로고</a>
    </div>
    <ul class="nav navbar-nav">
      <li class="active"><a href="#">홈</a></li>
      <li><a href="#">페이지1</a></li>
    </ul>
  </div>
</nav>
```

### 주요 클래스 설명

| 클래스 | 설명 |
|--------|------|
| `.navbar` | 내비게이션 바 생성 |
| `.navbar-default` | 기본 스타일(회색) |
| `.navbar-inverse` | 어두운 배경 스타일 |
| `.navbar-header` | 로고 또는 제목 영역 |
| `.navbar-brand` | 로고 또는 브랜드 링크 |
| `.navbar-left` | 왼쪽 정렬 |
| `.navbar-right` | 오른쪽 정렬 |
| `.navbar-nav` | 내비게이션 링크 그룹 |

### 작은 화면에서의 토글 버튼

```html
<button class="navbar-toggle" data-toggle="collapse" data-target="#myNavbar">
  <span class="icon-bar"></span>
  <span class="icon-bar"></span>
  <span class="icon-bar"></span>
</button>
```

## 8. 스크롤 효과

```css
html {
  scroll-behavior: smooth;
}
```

- 부드러운 스크롤링 기능 제공

## 9. 테이블

| 클래스 | 설명 |
|--------|------|
| `.table` | 기본 테이블 스타일 |
| `.table-striped` | 줄마다 배경색 교차 |
| `.table-bordered` | 테두리 포함 |
| `.table-hover` | 마우스 오버 시 강조 |
| `.table-condensed` | 셀 간격 줄이기 |

**예시:**

```html
<table class="table table-striped table-bordered table-hover table-condensed">
  <tr><th>이름</th><th>나이</th></tr>
  <tr><td>홍길동</td><td>30</td></tr>
</table>
```

## 10. 폼

- 폼 요소들은 자동으로 전역 스타일을 가짐
- 각 입력 그룹은 `.form-group`으로 감싸야 함
- `.form-control` 클래스는 `input`, `textarea`, `select` 등에 사용

**예시:**

```html
<form>
  <div class="form-group">
    <label for="name">이름:</label>
    <input type="text" class="form-control" id="name">
  </div>
</form>
```

## 11. Bootstrap 추가 방법

- Bootstrap 라이브러리는 HTML `<head>` 안에 포함

```html
<!-- CDN 방식 -->
<link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.4.1/css/bootstrap.min.css">
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.6.0/jquery.min.js"></script>
<script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.4.1/js/bootstrap.min.js"></script>
```

- HTML 요소에 Bootstrap 클래스들을 사용하면 다양한 UI 구성 가능