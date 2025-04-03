# 인터넷의 역사

## 1. ARPANET

1969년 미국 국방부 고등연구계획국(DARPA)의 프로젝트로 시작된 **ARPANET(Advanced Research Projects Agency Network)**는 인터넷의 시초로 여겨진다. 이 네트워크는 분산형 네트워크 구조를 기반으로 설계되어, 한 노드가 손실되더라도 데이터 전송이 가능하도록 구축되었다.

- 최초의 패킷 교환 네트워크
- 1969년 10월 29일, UCLA와 SRI International 사이에서 첫 데이터 전송 성공
- 점차 여러 대학과 연구기관으로 확장됨

## 2. 인터넷(Internet)

ARPANET이 발전하면서 1980년대부터 네트워크 간 상호 연결을 위한 표준이 필요하게 되었다. 이에 따라 **인터넷(Internet)**이라는 개념이 등장하였다.

- 네트워크와 네트워크를 연결하는 거대한 네트워크 시스템
- 1983년 1월 1일, ARPANET이 **TCP/IP 프로토콜**로 전환되며 인터넷의 기반 확립
- 1990년 ARPANET 폐쇄 후에도 인터넷은 계속 발전하며 상용화됨

## 3. TCP/IP

인터넷의 핵심 프로토콜인 **TCP/IP(Transmission Control Protocol/Internet Protocol)**는 데이터 전송을 위한 표준이다.

- **TCP (전송 제어 프로토콜)**: 데이터의 신뢰성 있는 전송을 보장
- **IP (인터넷 프로토콜)**: 데이터 패킷을 목적지까지 효율적으로 전달

TCP/IP 프로토콜이 등장하면서 네트워크 간의 상호 연결이 원활해졌으며, 인터넷이 전 세계적으로 확장될 수 있는 기반이 마련되었다.

## 4. WWW (World Wide Web)

**World Wide Web(WWW)**은 1989년 영국의 팀 버너스 리(Tim Berners-Lee)에 의해 개발된 인터넷 기반의 정보 공유 시스템이다.

- 1990년, 첫 번째 웹 브라우저와 웹 서버 개발
- 1991년, 최초의 웹사이트 운영 시작
- 하이퍼텍스트(HTML)를 기반으로 정보 연결
- 인터넷을 보다 사용자 친화적으로 만들어 대중화에 기여

## 5. WWW의 동작 과정 (Step-by-step illustration of how WWW works)

WWW는 다음과 같은 단계로 동작한다.

1. **사용자가 브라우저에 URL 입력**
   - 예: `https://www.example.com`
2. **DNS 서버가 도메인 이름을 IP 주소로 변환**
   - `www.example.com` → `192.168.1.1`
3. **브라우저가 웹 서버에 HTTP 요청 전송**
   - `GET /index.html HTTP/1.1`
4. **웹 서버가 HTML 문서를 반환**
   - `HTTP/1.1 200 OK`
5. **브라우저가 HTML을 렌더링하여 사용자에게 웹 페이지 표시**

이러한 과정을 통해 사용자는 인터넷을 통해 원하는 정보를 손쉽게 접근할 수 있다.

---

# 소프트웨어와 개발 개요

## 1. Proprietary Software (독점 소프트웨어)

**Proprietary Software(독점 소프트웨어)**는 소스 코드가 비공개이며, 특정 기업이나 개인이 소유 및 관리하는 소프트웨어를 의미한다.

- 사용자는 라이선스를 구매해야 사용 가능
- 수정 및 재배포가 제한됨
- 대표적인 예시: Microsoft Windows, Adobe Photoshop, macOS

## 2. Open Source Software (오픈 소스 소프트웨어)

**Open Source Software(오픈 소스 소프트웨어)**는 소스 코드가 공개되어 있으며, 누구나 자유롭게 사용, 수정, 배포할 수 있는 소프트웨어를 의미한다.

- 개발자 및 사용자 커뮤니티가 유지보수
- 비용 없이 자유롭게 활용 가능
- 대표적인 예시: Linux, Apache, Mozilla Firefox, Blender

## 3. Front End Development (프론트엔드 개발)

**프론트엔드 개발**은 사용자가 직접 상호작용하는 웹사이트 또는 애플리케이션의 UI(User Interface) 부분을 개발하는 작업이다.

- 주요 기술: HTML, CSS, JavaScript
- 프레임워크 및 라이브러리: React, Vue.js, Angular
- 역할: 웹사이트 디자인 구현, 사용자 경험(UX) 개선, 반응형 웹 개발

## 4. Back End Development (백엔드 개발)

**백엔드 개발**은 데이터베이스, 서버, 애플리케이션 로직 등 웹 애플리케이션의 내부 기능을 담당하는 개발 영역이다.

- 주요 언어: Python, Java, Node.js, PHP, Ruby
- 데이터베이스: MySQL, PostgreSQL, MongoDB
- 역할: 데이터 처리, 사용자 인증, API 개발 및 관리

프론트엔드와 백엔드는 함께 협력하여 웹 애플리케이션을 완성하며, 풀스택 개발자는 이 두 영역을 모두 다룰 수 있는 개발자를 의미한다.

---

# Web Development Techniques

## 1. HTML5

**HTML (HyperText Markup Language)**는 웹 페이지의 구조를 정의하는 마크업 언어이다.

- 기본적인 웹 페이지의 뼈대를 형성
- `<h1>`, `<p>`, `<a>`, `<img>` 등의 태그를 사용하여 콘텐츠 배치

**HTML5**는 HTML의 최신 표준으로, 다양한 새로운 기능을 포함한다.

- 멀티미디어 지원 (예: `<video>`, `<audio>` 태그)
- 반응형 디자인을 위한 `<canvas>` 요소 제공
- 향상된 웹 폼 기능 및 로컬 저장소 지원

## 2. CSS3.0

**CSS (Cascading Style Sheets)**는 HTML 요소의 스타일(디자인)을 정의하는 언어이다.

- 색상, 글꼴, 레이아웃 등을 조정하여 웹사이트를 디자인
- `class`, `id`를 사용하여 특정 요소에 스타일 적용 가능

**CSS3.0**은 CSS의 최신 표준으로, 다음과 같은 향상된 기능을 포함한다.

- 애니메이션 및 트랜지션 (`@keyframes`, `transition`)
- 미디어 쿼리를 통한 반응형 디자인 지원
- `flexbox`, `grid` 등을 이용한 강력한 레이아웃 시스템 제공

## 3. JavaScript

**JavaScript**는 웹 페이지에서 동적 기능을 추가하는 프로그래밍 언어이다.

- 버튼 클릭 이벤트, 폼 검증 등 사용자 인터랙션 처리 가능
- DOM(Document Object Model) 조작을 통해 HTML 요소를 변경
- 비동기 통신(AJAX, Fetch API)을 활용하여 데이터 불러오기

## 4. React

**React**는 Facebook에서 개발한 JavaScript 라이브러리로, UI 개발을 위한 컴포넌트 기반의 아키텍처를 제공한다.

- **컴포넌트 기반 개발**: 재사용 가능한 UI 컴포넌트 생성 가능
- **가상 DOM(Virtual DOM)**: 성능 최적화를 위한 효율적인 렌더링
- **단방향 데이터 흐름**: 상태 관리가 용이하며 유지보수가 쉬움
- **훅(Hooks) 지원**: `useState`, `useEffect` 등을 활용한 상태 관리 가능

React는 대규모 애플리케이션에서 효율적인 UI 개발을 가능하게 하며, 프론트엔드 개발에서 널리 사용되고 있다.

---

## HTML Tag

### 1. **텍스트 관련 태그**
| 태그 | 설명 | 주요 속성 및 예제 |
|------|------|----------------|
| `<h1>` ~ `<h6>` | 제목 태그 (h1이 가장 크고 h6이 가장 작음) | `<h1>제목</h1>` |
| `<p>` | 문단 태그 | `<p>이것은 문단입니다.</p>` |
| `<br>` | 줄 바꿈 (self-closing) | `줄 바꿈<br>이후 텍스트` |
| `<hr>` | 가로선 (self-closing) | `<hr>` |
| `<b>` | 굵은 텍스트 (단순 스타일) | `<b>굵은 텍스트</b>` |
| `<i>` | 기울임꼴 (단순 스타일) | `<i>기울임꼴 텍스트</i>` |
| `<strong>` | 강조 (중요한 의미) | `<strong>강조된 텍스트</strong>` |
| `<em>` | 강조 (기울임 + 의미 강조) | `<em>강조된 텍스트</em>` |
| `<code>` | 코드 블록 | `<code>console.log('Hello')</code>` |
| `<sup>` | 위 첨자 | `X<sup>2</sup>` |
| `<sub>` | 아래 첨자 | `H<sub>2</sub>O` |
| `<address>` | 주소 정보 | `<address>서울, 대한민국</address>` |
| `<bdo>` | 텍스트 방향 지정 | `<bdo dir="rtl">오른쪽부터</bdo>` |
| `<blockquote>` | 인용 블록 | `<blockquote>이것은 인용문입니다.</blockquote>` |
| `<cite>` | 출처 표시 | `<cite>책 제목</cite>` |
| `<q>` | 인라인 인용 | `<q>짧은 인용문</q>` |

---

### 2. **특수 문자**
| 코드 | 설명 | 예제 |
|------|------|------|
| `&nbsp;` | 공백 추가 | `A&nbsp;B` |
| `&lt;` | `<` 표시 | `&lt;div&gt;` |
| `&gt;` | `>` 표시 | `&gt;span&lt;` |
| `&quot;` | `"` 표시 | `&quot;문자열&quot;` |
| `&amp;` | `&` 표시 | `Tom &amp; Jerry` |
| `&copy;` | 저작권 기호 | `&copy; 2024 회사명` |
| `<!-- -->` | 주석 | `<!-- 여기에 주석을 작성 -->` |

---

### 3. **목록 관련 태그**
| 태그 | 설명 | 예제 |
|------|------|------|
| `<ul>` | 순서 없는 목록 | `<ul><li>항목 1</li></ul>` |
| `<ol>` | 순서 있는 목록 | `<ol><li>첫 번째</li></ol>` |
| `<li>` | 목록 항목 | `<li>리스트 항목</li>` |

---

### 4. **링크 및 이미지 태그**
| 태그 | 설명 | 주요 속성 및 예제 |
|------|------|----------------|
| `<a>` | 하이퍼링크 | `<a href="https://example.com">링크</a>` |
| `target="_blank"` | 새 창에서 열기 | `<a href="url" target="_blank">링크</a>` |
| `target="_self"` | 현재 창에서 열기 (기본값) | `<a href="url" target="_self">링크</a>` |
| `target="_parent"` | 부모 프레임에서 열기 | `<a href="url" target="_parent">링크</a>` |
| `target="_top"` | 최상위 창에서 열기 | `<a href="url" target="_top">링크</a>` |
| `<img>` | 이미지 삽입 | `<img src="image.jpg" alt="이미지 설명">` |
| `alt` | 대체 텍스트 | `<img src="image.jpg" alt="설명">` |
| `src` | 이미지 경로 | `<img src="image.jpg">` |
| `<picture>` | 반응형 이미지 지원 | `<picture><source srcset="image.webp" type="image/webp"><img src="image.jpg"></picture>` |
| `<source>` | `picture`, `audio`, `video`에서 사용 | `<source srcset="image.webp" type="image/webp">` |

---

### 5. **테이블 관련 태그**
| 태그 | 설명 | 예제 |
|------|------|------|
| `<table>` | 테이블 생성 | `<table>...</table>` |
| `<tr>` | 행 생성 | `<tr>...</tr>` |
| `<td>` | 셀 생성 (데이터) | `<td>내용</td>` |
| `<th>` | 헤더 셀 | `<th>제목</th>` |
| `border` | 테두리 설정 | `<table border="1">` |
| `rowspan` | 행 병합 | `<td rowspan="2">세로 병합</td>` |
| `colspan` | 열 병합 | `<td colspan="2">합쳐진 셀</td>` |

---

### 6. **미디어 관련 태그**
| 태그 | 설명 | 주요 속성 및 예제 |
|------|--------|----------------|
| `<audio>` | 오디오 삽입 | `<audio controls><source src="audio.mp3"></audio>` |
| `autoplay` | 자동 재생 | `<audio autoplay>` |
| `controls` | 재생 컨트롤 | `<audio controls>` |
| `loop` | 반복 재생 | `<audio loop>` |
| `muted` | 음소거 | `<audio muted>` |
| `<video>` | 비디오 삽입 | `<video controls><source src="video.mp4"></video>` |
| `poster` | 미리보기 이미지 | `<video poster="thumbnail.jpg">` |
| `<iframe>` | 외부 페이지 삽입 | `<iframe src="https://example.com"></iframe>` |
| `title` | 프레임 설명 | `<iframe src="url" title="설명"></iframe>` |
| `frameborder` | 테두리 설정 | `<iframe frameborder="0">` |
| `allow` | 특정 기능 허용 | `<iframe allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"></iframe>` |
| `referrerpolicy` | 보안 정책 설정 | `<iframe referrerpolicy="strict-origin-when-cross-origin"></iframe>` |
| `allowfullscreen` | 전체 화면 허용 | `<iframe allowfullscreen></iframe>` |

---

### 7. **기본 구조 태그**
| 태그 | 설명 | 예제 |
|------|------|------|
| `<!DOCTYPE html>` | HTML5 문서 선언 | `<!DOCTYPE html>` |
| `<html>` | HTML 문서 루트 요소 | `<html>...</html>` |
| `<head>` | 문서 정보 포함 | `<head>...</head>` |
| `<body>` | 문서 본문 | `<body>...</body>` |

---

### 8. **시맨틱 태그**
| 태그 | 설명 |
|------|------|
| `<header>` | 머리글 |
| `<nav>` | 내비게이션 영역 |
| `<section>` | 섹션 구분 |
| `<article>` | 독립적 콘텐츠 |
| `<aside>` | 사이드 콘텐츠 |
| `<footer>` | 바닥글 |

<br/>

---

## HTML `<input>` 속성 정리

### 1. **기본 속성**
| 속성 | 설명 | 예제 |
|-------|------|------|
| `type` | 입력 필드의 유형을 지정 | `<input type="text">` |
| `name` | 서버로 전송될 때 식별자로 사용 | `<input type="text" name="username">` |
| `id` | 요소를 고유하게 식별하는 ID (CSS나 JS에서 사용) | `<input type="text" id="userInput">` |
| `value` | 입력 필드의 기본값 설정 | `<input type="text" value="기본값">` |
| `placeholder` | 입력 필드에 힌트 제공 (값 입력 전) | `<input type="text" placeholder="이름을 입력하세요">` |
| `disabled` | 입력 필드를 비활성화 | `<input type="text" disabled>` |
| `readonly` | 입력 필드를 읽기 전용으로 설정 | `<input type="text" readonly>` |

---

### 2. **폼 관련 속성**
| 속성 | 설명 | 예제 |
|------|------|------|
| `form` | 특정 폼과 연결 (폼 태그 ID 참조) | `<input type="text" form="myForm">` |
| `required` | 필수 입력 필드로 설정 | `<input type="email" required>` |
| `autocomplete` | 자동완성 설정 (`on`/`off`) | `<input type="text" autocomplete="off">` |
| `autofocus` | 페이지 로드 시 자동 포커스 | `<input type="text" autofocus>` |
| `multiple` | 여러 개의 값 입력 허용 (파일 업로드, 이메일 등) | `<input type="file" multiple>` |
| `pattern` | 입력 값의 정규 표현식 패턴 지정 | `<input type="text" pattern="[A-Za-z]{3,10}">` |

---

### 3. **숫자 및 범위 관련 속성**
| 속성 | 설명 | 예제 |
|------|------|------|
| `min` | 최소값 지정 | `<input type="number" min="10">` |
| `max` | 최대값 지정 | `<input type="number" max="100">` |
| `step` | 증가 단위 지정 | `<input type="number" step="5">` |

---

### 4. **파일 업로드 관련 속성**
| 속성 | 설명 | 예제 |
|------|------|------|
| `accept` | 허용할 파일 형식 지정 | `<input type="file" accept="image/png, image/jpeg">` |

---

### 5. **체크박스 및 라디오 버튼 관련 속성**
| 속성 | 설명 | 예제 |
|------|------|------|
| `checked` | 기본적으로 체크된 상태로 설정 | `<input type="checkbox" checked>` |

---

### 6. **기타 속성**
| 속성 | 설명 | 예제 |
|------|------|------|
| `list` | `<datalist>`와 연결 | `<input type="text" list="suggestions">` |
| `size` | 입력 필드의 표시 크기 지정 | `<input type="text" size="30">` |

<br/>

---

## input 속성에서 `name`과 `value`의 역할

### **예제 1: 일반적인 폼 전송**
```html
<form action="/submit" method="POST">
    <input type="text" name="username" value="홍길동">
    <input type="submit" value="전송">
</form>
```
- 사용자가 입력을 변경하지 않고 제출하면, 서버로 전송되는 데이터는:
  ```
  username=홍길동
  ```
- 여기서 `name="username"`이 **키(식별자)** 역할을 하고, `value="홍길동"`이 **값**이 됩니다.

---

### **예제 2: 체크박스 (체크했을 때만 값 전송)**
```html
<form action="/submit" method="POST">
    <input type="checkbox" name="subscribe" value="yes"> 구독하기
    <input type="submit" value="전송">
</form>
```
- 체크하면 서버로 `subscribe=yes`가 전송됨.
- 체크하지 않으면 해당 데이터가 아예 전송되지 않음.

---

### **예제 3: 라디오 버튼 (선택한 값만 전송)**
```html
<form action="/submit" method="POST">
    <input type="radio" name="gender" value="male"> 남성
    <input type="radio" name="gender" value="female"> 여성
    <input type="submit" value="전송">
</form>
```
- "남성"을 선택하면 서버로 `gender=male`이 전송됨.
- "여성"을 선택하면 서버로 `gender=female`이 전송됨.

---

### **정리**
1. **`name`** → 서버에서 값을 구별하는 키(식별자).
2. **`value`** → 실제 서버로 전송되는 값.

즉, 폼 데이터는 `name=value` 형식으로 서버에 전달된다.

