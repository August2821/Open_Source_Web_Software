# JavaScript란?

JavaScript는 웹의 프로그래밍 언어입니다. HTML과 CSS와 함께 웹 개발의 핵심 요소로 사용되며, 웹 페이지에 동적인 기능을 추가할 수 있게 해줍니다.

## JavaScript의 특징

- **인터프리터 언어 (Interpreted language)**  
  JavaScript는 컴파일 과정 없이 실행 시 해석되어 실행됩니다.

- **동적 타이핑 (Dynamic typing)**  
  변수에 저장되는 값의 타입을 명시하지 않아도 되며, 실행 중에 타입이 변경될 수 있습니다.
  ```javascript
  let x = 10;   // 숫자
  x = "hello";  // 문자열로 변경 가능
  ```

- **함수형 프로그래밍 지원 (Functional programming)**  
  C 언어처럼 함수를 일급 객체로 다루며, 함수를 변수에 할당하거나 다른 함수의 인자로 전달할 수 있습니다.
  ```javascript
  function greet(name) {
    return "Hello " + name;
  }

  let sayHello = greet;
  console.log(sayHello("Alice"));
  ```

- **객체 지향 프로그래밍 지원 (Object oriented programming)**  
  Java나 C++처럼 클래스와 객체를 사용하여 객체 지향 프로그래밍이 가능합니다.
  ```javascript
  class Person {
    constructor(name) {
      this.name = name;
    }
    greet() {
      console.log("Hello, " + this.name);
    }
  }

  const p = new Person("Bob");
  p.greet();
  ```

- **Java와는 다른 언어 (JavaScript는 Java가 아님)**  
  이름이 비슷하지만 JavaScript는 Java와는 완전히 다른 언어입니다.

- **배우기 쉬움 (Easy to learn)**  
  문법이 간단하고 이해하기 쉬워 초보자도 쉽게 배울 수 있습니다.

## JavaScript의 위치 (HTML 문서 내 삽입 방식)

### 1. 외부 JavaScript (External JavaScript)

`.js` 확장자를 가진 별도의 파일로 작성되며, HTML 파일에서는 `<script src="파일명.js"></script>`로 불러옵니다.

**예시**

**HTML 파일**
```html
<!DOCTYPE html>
<html>
<head>
  <script src="myscript.js"></script>
</head>
<body>
  <h2>This is title</h2>
  <p>This is paragraph</p>
</body>
</html>
```

**myscript.js**
```javascript
document.write("Hello World")
```

### 2. 내부 JavaScript (Inner JavaScript)

HTML 문서의 `<head>`나 `<body>` 내에 `<script>` 태그를 사용해 직접 작성합니다.

**예시**
```html
<!DOCTYPE HTML>
<html>
<head>
  <title>My First Javascript</title>
  <script>
    document.write("Hello World")
  </script>
</head>
<body>
  <h2>This is title</h2>
  <p>This is paragraph</p>
</body>
</html>
```

### 3. 인라인 JavaScript (Inline JavaScript)

HTML 요소 내부의 이벤트 속성에 직접 JavaScript 코드를 작성하는 방식입니다.

**예시**
```html
<!DOCTYPE html>
<html>
<body>
  <button type="button" onclick="alert('Welcome to JS!')">Click button</button>
</body>
</html>
```

JavaScript는 웹 페이지를 동적으로 만들고 사용자와의 상호작용을 가능하게 해주는 매우 강력한 도구입니다. 다양한 방식으로 HTML 문서에 삽입할 수 있으며, 웹 개발에서 필수적인 언어입니다.

---

# JavaScript 문법 (JavaScript Syntax)

JavaScript는 웹 브라우저에서 동작하는 프로그래밍 언어이며, 데이터를 표시하고 조작하는 데에 다양한 방법을 제공합니다.

## JavaScript 출력 방법 (JavaScript Output)

JavaScript는 데이터를 여러 방식으로 출력할 수 있습니다.

- **innerHTML을 이용한 출력**  
- **document.write()를 이용한 출력**  
- **window.alert()를 이용한 출력**  
- **console.log()를 이용한 출력**

### 1. innerHTML 사용하기

HTML 요소를 선택하여 내부의 콘텐츠를 변경할 수 있습니다.  
`document.getElementById(id)`를 사용하여 요소에 접근하고, `.innerHTML`을 사용하여 내용을 설정합니다.

**예시**
```html
<!DOCTYPE html>
<html>
<body>

<h2>My First Web Page</h2>
<p>My First Paragraph.</p>
<p id="demo"></p>

<script>
document.getElementById("demo").innerHTML = 5 + 6;
</script>

</body>
</html>
```

### 2. document.write() 사용하기

간단한 테스트나 예제 작성 시 `document.write()`를 사용하여 HTML 문서에 직접 출력할 수 있습니다.

**예시**
```html
<!DOCTYPE html>
<html>
<body>

<h2>My First Web Page</h2>
<p>My First Paragraph.</p>

<script>
document.write(5 + 6);
</script>

</body>
</html>
```

### 3. window.alert() 사용하기

`window.alert()`는 경고창(alert box)을 띄워 데이터를 출력합니다.

**예시**
```html
<!DOCTYPE html>
<html>
<body>

<h2>My First Web Page</h2>
<p>My First Paragraph.</p>

<script>
window.alert(5 + 6);
</script>

</body>
</html>
```

### 4. console.log() 사용하기

`console.log()`는 브라우저의 콘솔(개발자 도구)에 데이터를 출력할 때 사용합니다.

**예시**
```javascript
console.log(5 + 6);
```

## JavaScript 문장 (Statements)

JavaScript 문장은 웹 브라우저에게 명령을 내리는 구문입니다. 예를 들어 값을 계산하거나, 데이터를 출력하거나, 조건을 판단하는 등의 작업을 수행합니다.

## JavaScript 주석 (Comments)

- 한 줄 주석: `//`로 시작
- 여러 줄 주석: `/*`로 시작하여 `*/`로 종료

**예시**
```javascript
// 이것은 한 줄 주석입니다.

/*
이것은
여러 줄 주석입니다.
*/
```

## JavaScript 변수 (Variables)

변수는 데이터를 저장할 수 있는 공간입니다. 변수 선언에는 `var`, `let`, `const` 키워드를 사용합니다.

### 변수 선언 예시

**예시**
```html
<!DOCTYPE html>
<html>
<body>

<h2>JavaScript Variable</h2>
<p>Create, assign and display variable value</p>
<p id="demo"></p>

<script>
var carName = "Volvo";
document.getElementById("demo").innerHTML = carName;
</script>

</body>
</html>
```

## 변수 이름 규칙 (Identifiers)

- 변수 이름에는 문자, 숫자, 밑줄(`_`), 달러 기호(`$`)를 사용할 수 있습니다.
- 문자로 시작해야 합니다. 숫자로 시작할 수 없습니다.
- 대소문자를 구분합니다.
- JavaScript 예약어는 변수 이름으로 사용할 수 없습니다.

## JavaScript 예약어 (Reserved Keywords)

아래는 변수 이름으로 사용할 수 없는 예약어입니다:

```
break, continue, debugger, do … while, for, function,
if … else, return, switch, try … catch, var
```

## 어떤 변수 키워드를 사용할까?

| 키워드  | 특징                                  | 사용 시기              |
|--------|--------------------------------------|----------------------|
| `var`  | 함수 범위(function-scoped), 재선언 가능 | 오래된 브라우저 지원이 필요할 때 사용 |
| `let`  | 블록 범위(block-scoped), 값 변경 가능   | 값이 변경될 수 있을 때 사용     |
| `const`| 블록 범위, 상수로서 값 변경 불가       | 변경되지 않는 값을 저장할 때 사용 |

### `let` 예시
```javascript
let score = 10;
score = 20; // 가능
console.log(score); // 20
```

### `const` 예시
```javascript
const score = 10;
score = 20; // 오류 발생: Assignment to constant variable
```

## 변수 선언 권장 사항

- 항상 변수를 선언하세요.
- 값이 변경되지 않는다면 `const`를 사용하세요.
- 값이 변경될 가능성이 있다면 `let`을 사용하세요.
- 반드시 오래된 브라우저 지원이 필요한 경우에만 `var`를 사용하세요.