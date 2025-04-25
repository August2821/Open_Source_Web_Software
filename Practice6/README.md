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

## JavaScript 산술 연산자 (Arithmetic Operators)
산술 연산자는 숫자에 대한 연산을 수행합니다.

| 연산자 | 설명 | 예시 | 결과 |
|--------|------|------|------|
| `+` | 덧셈 | `5 + 2` | `7` |
| `-` | 뺄셈 | `5 - 2` | `3` |
| `*` | 곱셈 | `5 * 2` | `10` |
| `**` | 거듭제곱 | `5 ** 2` | `25` |
| `/` | 나눗셈 | `5 / 2` | `2.5` |
| `%` | 나머지 | `5 % 2` | `1` |
| `++` | 증가 | `let x = 5; x++` | `6` |
| `--` | 감소 | `let x = 5; x--` | `4` |

## JavaScript 대입 연산자 (Assignment Operators)
대입 연산자는 변수에 값을 할당할 때 사용합니다.

| 연산자 | 설명 | 예시 | 결과 |
|--------|------|------|------|
| `=` | 대입 | `x = 5` | `x는 5` |
| `+=` | 더해서 대입 | `x += 2` | `x = x + 2` |
| `-=` | 빼서 대입 | `x -= 2` | `x = x - 2` |
| `*=` | 곱해서 대입 | `x *= 2` | `x = x * 2` |
| `/=` | 나눠서 대입 | `x /= 2` | `x = x / 2` |
| `%=` | 나머지 대입 | `x %= 2` | `x = x % 2` |
| `<<=` | 비트 왼쪽 시프트 | `x <<= 1` | `x = x << 1` |
| `>>=` | 비트 오른쪽 시프트 | `x >>= 1` | `x = x >> 1` |
| `>>>=` | 부호 없는 오른쪽 시프트 | `x >>>= 1` | `x = x >>> 1` |
| `&=` | 비트 AND | `x &= 1` | `x = x & 1` |
| `^=` | 비트 XOR | `x ^= 1` | `x = x ^ 1` |
| `\|=` | 비트 OR | `x \|= 1` | `x = x \| 1` |
| `**=` | 거듭제곱 대입 | `x **= 2` | `x = x ** 2` |

### 논리 대입 연산자

#### `&&=` 연산자
- 첫 번째 값이 참이면 두 번째 값이 대입됩니다.
```javascript
let x = 10;
x &&= 5;
console.log(x); // 5
```

#### `||=` 연산자
- 첫 번째 값이 거짓이면 두 번째 값이 대입됩니다.
```javascript
let x = 10;
x ||= 5;
console.log(x); // 10
```

### JavaScript에서 false로 간주되는 값
- `0`
- `false`
- `null`
- `undefined`
- `NaN`
- 빈 문자열(`""`)

그 외의 값은 모두 참으로 간주됩니다.

## JavaScript 비교 연산자 (Comparison Operators)

| 연산자 | 설명 | 예시 | 결과 |
|--------|------|------|------|
| `==` | 느슨한 동등 비교 | `10 == "10"` | `true` |
| `===` | 엄격한 동등 비교 | `10 === "10"` | `false` |
| `!=` | 느슨한 부등 비교 | `10 != "5"` | `true` |
| `!==` | 엄격한 부등 비교 | `10 !== "10"` | `true` |
| `>` | 크다 | `10 > 5` | `true` |
| `<` | 작다 | `10 < 5` | `false` |
| `>=` | 크거나 같다 | `10 >= 10` | `true` |
| `<=` | 작거나 같다 | `10 <= 9` | `false` |

### `==` vs `===` 차이 예시
```html
<!DOCTYPE html>
<html>
<body>
    <h2>JavaScript Comparison</h2>
    <p>느슨한 동등 비교 (==)</p>
    <p id="demo1"></p>
    <p>엄격한 동등 비교 (===)</p>
    <p id="demo2"></p>
    <script>
        var a = 10;
        document.getElementById("demo1").innerHTML = (a == "10"); // true
        document.getElementById("demo2").innerHTML = (a === "10"); // false
    </script>
</body>
</html>
```

위 예시를 통해 `==`는 타입 변환을 통해 값만 비교하지만, `===`는 타입까지 일치해야 한다는 것을 알 수 있습니다.

## JavaScript Data Types

### 문자열과 숫자 더하기
JavaScript에서 숫자와 문자열을 더할 경우, 숫자가 문자열로 변환됩니다.

```javascript
var x = 16 + "Volvo";       // Output: "16Volvo"
var x = "Volvo" + 16;       // Output: "Volvo16"
var x = 16 + 4 + "Volvo";   // Output: "20Volvo"
var x = "Volvo" + 16 + 4;   // Output: "Volvo164"

var x = 5 + 5;              // Output: 10
var y = "5" + 5;            // Output: "55"
var z = 5 + "Hello";        // Output: "5Hello"
```

### 뺄셈의 동작
뺄셈 연산은 피연산자들이 모두 숫자로 변환된 후 처리됩니다.

```javascript
var x = 5;
x = 5 + 7;        // 12 (number)
x = 5 + "7";      // "57" (string)
x = "5" + 7;      // "57" (string)
x = 5 - 7;        // -2 (number)
x = 5 - "7";      // -2 (number)
x = "5" - 7;      // -2 (number)
x = 5 - "x";      // NaN (number)
```

### 동적 타입
JavaScript는 동적 타입 언어입니다. 하나의 변수에 다양한 타입의 값을 저장할 수 있습니다.

```javascript
var x;          // undefined
x = 5;          // Number
y = "John";     // String
```

### typeof 연산자
변수의 타입을 확인할 수 있습니다.

```javascript
typeof "John";        // "string"
typeof "John Doe";    // "string"
typeof 0;             // "number"
typeof 314;           // "number"
typeof 3.14;          // "number"
typeof (3);           // "number"
typeof (3 + 4);       // "number"
```

**퀴즈**
```javascript
typeof ""; // 결과: "string"
```

## JavaScript Strings

### 문자열 정의
```html
<!DOCTYPE html>
<html>
<body>
    <h2>JavaScript Strings</h2>
    <p id="demo"></p>
    <script>
        var text = "John Doe";
        document.getElementById("demo").innerHTML = text;
    </script>
</body>
</html>
```

### 문자열 메서드
```javascript
// 문자열 길이
var txt = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";
var length = txt.length; // 26

// slice()
var str = "Apple, Banana, Kiwi";
str.slice(7, 13);       // "Banana"
str.slice(-12, -6);     // "Banana"
str.slice(7);           // "Banana, Kiwi"

// replace()
var text = "Hi!";
var newText = text.replace("Hi", "Hello"); // "Hello"

// 대소문자 변환
var text1 = "Hello World!";
text1.toUpperCase();    // "HELLO WORLD!"
text1.toLowerCase();    // "hello world!"

// concat()
var text1 = "Hello";
var text2 = "World";
text1.concat(" ", text2); // "Hello World"

// charAt()
var text = "HELLO WORLD";
text.charAt(0); // "H"
text[0];        // "H"
```

### 문자열 검색
```javascript
// indexOf()
let text = "Please locate my cat!";
text.indexOf("locate"); // 7

// includes()
let text2 = "Hello world, welcome to the universe.";
text2.includes("world"); // true
```

## JavaScript Numbers

### 숫자 출력 예시
```html
<!DOCTYPE html>
<html>
<body>
    <h2>JavaScript Numbers</h2>
    <p id="demo"></p>
    <script>
        var x = 3.14;
        var y = 3;
        document.getElementById("demo").innerHTML = x + "<br>" + y;
    </script>
</body>
</html>
```

## JavaScript Number Methods

### toString()
숫자를 문자열로 변환합니다.
```javascript
var x = 123;
x.toString();           // "123"
(123).toString();       // "123"
(100 + 23).toString();  // "123"
```

### Number.isInteger()
값이 정수인지 확인합니다.
```javascript
Number.isInteger(123);     // true
Number.isInteger(-123);    // true
Number.isInteger("123");   // false
```

### Number()
다양한 타입을 숫자로 변환합니다.
```javascript
Number(true);       // 1
Number(false);      // 0
Number("10");       // 10
Number(" 10");      // 10
Number("10 ");      // 10
Number(" 10 ");     // 10
Number("10.33");    // 10.33
Number("10,33");    // NaN
Number("10 33");    // NaN
Number("John");     // NaN
```

### parseInt()
문자열을 정수로 변환합니다.
```javascript
parseInt("-10");        // -10
parseInt("-10.33");     // -10
parseInt("10");         // 10
parseInt("10.33");      // 10
parseInt("10 20 30");   // 10
parseInt("10 years");   // 10
parseInt("years 10");   // NaN
```

