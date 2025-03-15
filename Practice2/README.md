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
|------|------|----------------|
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

