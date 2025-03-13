# HTML

### Tag
`<br>`: 줄 바꾸기 <br/>
`<hr>`: 수평선 (horizontal line) <br/>
`<sub> </sub>`: 아래첨자 (subscript) <br/>
`<sup> </sup>`: 윗첨자 (superscript)

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

