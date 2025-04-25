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
