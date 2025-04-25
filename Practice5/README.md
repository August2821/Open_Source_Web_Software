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

### Flexbox 사용 시:
- 코드가 간결하고 최소화됨
- 자동 수직 정렬 가능
- **미디어 쿼리만 추가하면 반응형 대응 용이**

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
