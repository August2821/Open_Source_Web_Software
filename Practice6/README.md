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

### `undefined`
`undefined`는 값이 할당되지 않은 변수에 자동으로 부여되는 값입니다.

언제 발생하나?
- 변수를 선언했지만 값을 할당하지 않은 경우
- 함수가 return 문 없이 종료된 경우
- 객체에 존재하지 않는 속성을 접근했을 경우
- 배열의 존재하지 않는 인덱스를 참조했을 경우

### `NaN` (Not-a-Number)
`NaN`은 숫자가 아닌 값을 숫자로 변환하려고 할 때 생기는 특수한 숫자값입니다. 즉, 수학적으로 잘못된 연산 결과를 나타냅니다.

언제 발생하나?
- 문자열을 숫자처럼 연산하려고 할 때
- 숫자 변환이 실패했을 때
- Math 관련 연산이 실패했을 때

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

### 문자열과 숫자의 더하기
JavaScript에서 숫자와 문자열을 더할 경우, 숫자는 문자열로 변환되어 연결됩니다.

```javascript
var x = 16 + "Volvo";  // 결과: "16Volvo"
var x = "Volvo" + 16;  // 결과: "Volvo16"
var x = 16 + 4 + "Volvo";  // 결과: "20Volvo"
var x = "Volvo" + 16 + 4;  // 결과: "Volvo164"

var x = 5 + 5;     // 결과: 10
var y = "5" + 5;   // 결과: "55"
var z = 5 + "Hello"; // 결과: "5Hello"
```

### 빼기 연산은 숫자로 변환
빼기 연산자는 피연산자들을 숫자로 변환하려고 시도합니다.

```javascript
var x = 5;
x = 5 + 7;      // 결과: 12, typeof x: number
x = 5 + "7";    // 결과: "57", typeof x: string
x = "5" + 7;    // 결과: "57", typeof x: string
x = 5 - 7;      // 결과: -2, typeof x: number
x = 5 - "7";    // 결과: -2, typeof x: number
x = "5" - 7;    // 결과: -2, typeof x: number
x = 5 - "x";    // 결과: NaN, typeof x: number
```

### 동적 타입
JavaScript는 동적 타입 언어입니다. 즉, 변수는 다양한 타입의 값을 가질 수 있습니다.

```javascript
var x;        // x는 undefined
x = 5;        // x는 숫자
x = "John";   // x는 문자열
```

### typeof 연산자
변수의 타입을 확인할 때 `typeof` 연산자를 사용할 수 있습니다.

```javascript
typeof "John"        // "string"
typeof "John Doe"    // "string"
typeof 0             // "number"
typeof 314           // "number"
typeof 3.14          // "number"
typeof (3)           // "number"
typeof (3 + 4)       // "number"
```

퀴즈: `typeof ""`의 결과는 무엇일까요? "string"

## JavaScript Strings

문자열은 따옴표(작은 따옴표 또는 큰 따옴표) 안에 작성된 문자들의 집합입니다.

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

## JavaScript String Methods

### length
문자열의 길이를 반환합니다.
```javascript
var txt = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";
var length = txt.length;  // 26
```

### slice()
문자열의 일부를 추출하여 새로운 문자열을 반환합니다.
```javascript
var str = "Apple, Banana, Kiwi";
str.slice(7, 13);     // "Banana"
str.slice(-12, -6);   // "Banana"
str.slice(7);         // "Banana, Kiwi"
```

### replace()
문자열의 일치하는 첫 부분을 새 값으로 교체합니다.
```javascript
var text = "Hi!";
var newText = text.replace("Hi", "Hello");  // "Hello"
```

### toUpperCase(), toLowerCase()
문자열을 대문자 또는 소문자로 변환합니다.
```javascript
var text1 = "Hello World!";
text1.toUpperCase();  // "HELLO WORLD!"
text1.toLowerCase();  // "hello world!"
```

### concat()
문자열을 연결합니다.
```javascript
var text1 = "Hello";
var text2 = "World";
text1.concat(" ", text2);  // "Hello World"
"Hello" + " " + "World!";  // "Hello World"
```

### charAt()
지정한 인덱스의 문자를 반환합니다.
```javascript
var text = "HELLO WORLD";
text.charAt(0);  // "H"
text[0];         // "H"
```

## JavaScript Strings Search

### indexOf()
지정한 문자열이 처음 나타나는 인덱스를 반환합니다.
```javascript
let text = "Please locate my cat!";
text.indexOf("locate");  // 7
```

### includes()
문자열이 포함되어 있는지 여부를 `true` 또는 `false`로 반환합니다.
```javascript
let text = "Hello world, welcome to the universe.";
text.includes("world");  // true
```

## JavaScript Numbers

JavaScript는 숫자 데이터 타입이 하나만 존재합니다. 정수와 부동소수 모두 같은 타입입니다.

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
숫자가 정수인지 확인합니다.
```javascript
Number.isInteger(123);    // true
Number.isInteger(-123);   // true
Number.isInteger('123');  // false
```

### Number()
값의 data type을 number로 변환합니다.
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
string을 int로 변환합니다. type은 number로 변환됩니다.
```javascript
parseInt("-10");       // -10
parseInt("-10.33");    // -10
parseInt("10");        // 10
parseInt("10.33");     // 10
parseInt("10 20 30");  // 10
parseInt("10 years");  // 10
parseInt("years 10");  // NaN
```

# JavaScript 함수 (JavaScript Functions)

## 함수란?

JavaScript에서 함수(Function)는 **입력을 받아 특정 작업을 수행하고 결과를 반환하는 일종의 블랙박스**입니다. 반복되는 코드를 줄이고 재사용성을 높이는 데 사용됩니다.

## 함수의 기본 문법

```javascript
function 함수이름(매개변수1, 매개변수2, ...) {
  // 실행할 코드
}
```

### 예시

```javascript
function add(x, y) {
  return x + y;
}
```

이 함수는 `x`와 `y`를 더한 값을 반환합니다.

## 함수 호출 (Function Invocation)

함수는 다음과 같은 방법으로 호출할 수 있습니다:

- 자바스크립트 코드에서 직접 호출
- 자동 실행 (Self-invoking)
- 이벤트 발생 시 호출

## 1. 자바스크립트 코드에서 직접 호출

### 예제

```html
<!DOCTYPE html>
<html>
<body>
  <h2>JavaScript Function</h2>
  <p>Convert from Fahrenheit to Celsius</p>
  <p id="demo"></p>

  <script>
    function toCelsius(fahrenheit) {
      return (5 / 9) * (fahrenheit - 32);
    }

    document.getElementById("demo").innerHTML = toCelsius(77);
  </script>
</body>
</html>
```

**설명:** `toCelsius(77)` 함수는 직접 호출되어 `77도 화씨`를 섭씨로 변환하고, 결과를 웹 페이지에 출력합니다.

## 2. 자동 실행 함수 (Self-invoking Function)

함수 표현식에 괄호 `()`를 붙이면 즉시 실행됩니다.

### 예제

```html
<!DOCTYPE html>
<html>
<body>
  <h2>JavaScript Function</h2>
  <p>Automatically invoked function</p>
  <p id="demo"></p>

  <script>
    (function () {
      document.getElementById("demo").innerHTML = "Hello! I called myself";
    })();
  </script>
</body>
</html>
```

**설명:** 위 함수는 정의되자마자 자동으로 실행되며, "Hello! I called myself"라는 메시지를 출력합니다.

## 3. 이벤트 발생 시 함수 호출

이벤트(예: 버튼 클릭) 발생 시 함수가 실행될 수 있습니다.

### 예제

```html
<script>
  function greeting(title, name) {
    alert("Hello " + title + " " + name + "!");
  }
</script>

<button onclick="greeting('Mr.', 'Hong')">Click Here</button>
```

**설명:** 버튼을 클릭하면 `greeting` 함수가 실행되며 알림창에 인사 메시지를 표시합니다.

## 함수의 지역 변수 (Local Variables)

함수 내에서 선언된 변수는 **해당 함수 안에서만 유효한 지역 변수(Local Variable)**가 됩니다.

### 예제

```javascript
function example() {
  let message = "Hello!";
  console.log(message);
}
console.log(message); // 오류 발생: message는 정의되지 않음
```

## 기본 매개변수 값 (Default Parameter Values)

매개변수에 기본값을 설정할 수 있습니다.

### 예제

```javascript
function multiply(a, b = 2) {
  return a * b;
}

console.log(multiply(5));    // 10 (5 * 2)
console.log(multiply(5, 3)); // 15 (5 * 3)
```

## 나머지 매개변수 (Rest Parameter)

`...` 문법을 사용하면 **여러 개의 인자를 배열로 받을 수 있습니다.**

### 예제

```javascript
function sum(...numbers) {
  return numbers.reduce((total, num) => total + num, 0);
}

console.log(sum(1, 2, 3, 4)); // 10
```

## 인자가 부족한 경우

함수를 호출할 때 전달된 인자의 수가 함수에서 정의한 매개변수보다 적을 경우, **누락된 매개변수는 `undefined`가 됩니다.**

### 예제

```javascript
function printInfo(name, age) {
  console.log("이름: " + name);
  console.log("나이: " + age);
}

printInfo("철수"); 
// 출력:
// 이름: 철수
// 나이: undefined
```

## JavaScript 배열 (Array)

### 배열 생성 (리터럴 방식)
```javascript
var cars = ["Saab", "Volvo", "BMW"];
```
- 배열은 대괄호 `[]` 안에 요소들을 쉼표로 구분하여 생성합니다.
- 위의 예시는 문자열로 구성된 자동차 이름 배열을 생성합니다.

### 배열 요소 접근 (인덱스 사용)
```javascript
var cars = ["Saab", "Volvo", "BMW"];
var car = cars[0];  // 결과: Saab
```
- 배열의 인덱스는 0부터 시작합니다.
- `cars[0]`은 첫 번째 요소인 `"Saab"`을 반환합니다.

### 배열 요소 변경
```javascript
var cars = ["Saab", "Volvo", "BMW"];
cars[0] = "Opel";  // 결과: ["Opel", "Volvo", "BMW"]
```
- 배열의 요소는 인덱스를 통해 수정할 수 있습니다.

### 배열 생성 (객체 방식)
```javascript
var cars = new Array("Saab", "Volvo", "BMW");
```
- `new Array()`를 사용하여 배열을 생성할 수 있습니다.
- 리터럴 방식과 동일한 배열이 생성됩니다.

```javascript
var points = new Array(40, 100, 1, 5, 25, 10);
var points = [40, 100, 1, 5, 25, 10];
```
- 위 두 방법은 동일한 배열을 생성합니다.

```javascript
var points = new Array(40); // 길이 40인 빈 배열
var points = [40];          // 요소 40을 가진 배열
```
- `new Array(40)`은 요소가 없는 40개의 공간을 가진 배열을 생성하므로 주의가 필요합니다.

## JavaScript 배열 메서드

### `pop()` - 마지막 요소 제거
```javascript
var fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.pop();  // 결과: ["Banana", "Orange", "Apple"]
```

### `push()` - 마지막에 요소 추가
```javascript
var fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.push("Kiwi");  // 결과: ["Banana", "Orange", "Apple", "Mango", "Kiwi"]
```

### `length` - 배열 길이 활용
```javascript
var fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits[fruits.length] = "Kiwi";  // 결과: ["Banana", "Orange", "Apple", "Mango", "Kiwi"]
```

### `concat()` - 배열 병합
```javascript
var fruits = ["Kiwi", "Apple"];
var vegs = ["Tomato", "Cucumber"];
var discuss = fruits.concat(vegs);  // 결과: ["Kiwi", "Apple", "Tomato", "Cucumber"]
```

### `splice()` - 요소 추가/제거
```javascript
var fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.splice(1, 2, "Lemon", "Kiwi");  
// 인덱스 1부터 2개 삭제 후 "Lemon", "Kiwi" 추가
// 결과: ["Banana", "Lemon", "Kiwi", "Mango"]
```

### `slice()` - 배열의 일부 추출
```javascript
var fruits = ["Banana", "Orange", "Lemon", "Apple", "Mango"];
var citrus = fruits.slice(3);  // 결과: ["Apple", "Mango"]
```

### `sort()` - 정렬
```javascript
var fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.sort();  // 결과: ["Apple", "Banana", "Mango", "Orange"]
```

### `sort()` - 숫자 정렬 시 주의
```javascript
var points = [40, 100, 1, 5, 25, 10];
points.sort();  // 결과: [1, 10, 100, 25, 40, 5] (문자열로 비교됨)
```

### 숫자 정렬 (compare 함수 사용)
```javascript
var points = [40, 100, 1, 5, 25, 10];
points.sort(function(a, b){ return a - b });  
// 결과: [1, 5, 10, 25, 40, 100]
```

## JavaScript 제어문 (Controls)

### 조건문 (if, else if, else, switch)
조건문은 조건에 따라 서로 다른 동작을 수행합니다.

```html
<h2>JavaScript Controls</h2>
<p id="demo"></p>

<script>
var time = new Date().getHours();
var greeting;

if (time < 10) {
  greeting = "Good morning";
} else if (time < 20) {
  greeting = "Good day";
} else {
  greeting = "Good evening";
}

document.getElementById("demo").innerHTML = greeting;
</script>
```

## JavaScript 반복문 (Loops)

### 반복문의 종류
- `for`: 지정된 횟수만큼 반복
- `for/in`: 객체의 속성을 반복
- `for/of`: 반복 가능한 객체(배열, 문자열 등)의 값을 반복
- `while`: 조건이 참인 동안 반복
- `do/while`: 일단 실행 후 조건이 참인 동안 반복

### `for...of` 예시
```javascript
let fruits = ["Banana", "Orange", "Apple"];
for (let fruit of fruits) {
  console.log(fruit);
}
// 결과: Banana, Orange, Apple
```

### `for...in` 예시
```javascript
let person = {fname:"John", lname:"Doe", age:25};
for (let key in person) {
  console.log(key + ": " + person[key]);
}
// 결과: fname: John, lname: Doe, age: 25
```

---

# JavaScript 객체 지향 패러다임

## JavaScript 객체란?
- 객체(Object)는 속성(properties)과 메서드(methods)를 가진 **독립적인 코드 단위**입니다.
- 객체는 실생활의 사물과 유사하게 행동하며, 정보를 저장하고 동작을 수행합니다.

### 예시: 자동차 객체
```javascript
var car = {
  brand: "Hyundai",
  model: "Avante",
  color: "white",
  start: function() {
    return "Engine started";
  }
};
```

## 객체 생성: 객체 리터럴(Object Literal)

JavaScript 객체는 객체 리터럴을 사용하여 생성할 수 있습니다.

### 예시
```javascript
var person = {
  firstName: "John",
  lastName: "Doe",
  age: 50,
  eyeColor: "blue"
};
```

## 객체의 속성(Properties)

- 객체는 **이름(name)**과 **값(value)**의 쌍으로 구성된 속성들을 가집니다.
- 이 속성들은 해당 객체의 **상태나 정보**를 표현합니다.

### 예시
```javascript
var person = {
  firstName: "Alice",
  age: 30
};
```

## 객체 속성 접근 방법

속성은 두 가지 방식으로 접근할 수 있습니다:

- 점 표기법: `objectName.propertyName`
- 대괄호 표기법: `objectName["propertyName"]`

### 예시
```javascript
console.log(person.firstName);    // Alice
console.log(person["age"]);       // 30
```

## 객체의 메서드(Methods)

- 메서드는 객체에 **속성처럼 저장된 함수**입니다.
- 객체가 수행할 수 있는 **동작(기능)**을 정의합니다.

### 예시
```javascript
var person = {
  firstName: "John",
  lastName : "Doe",
  id       : 5566,
  fullName : function() {
    return this.firstName + " " + this.lastName;
  }
};

console.log(person.fullName());  // John Doe
```

## this 키워드

- 함수 내에서 `this`는 해당 함수를 **소유한 객체**를 참조합니다.
- 위의 예시에서 `this.firstName`은 `person.firstName`을 의미합니다.

## call() 메서드

- `call()` 메서드는 한 객체의 메서드를 다른 객체에 적용할 수 있게 합니다.
- **첫 번째 인자**로 사용할 객체를 지정하며, **그 뒤에 전달할 인자들**을 각각 나열합니다.

### 예시
```javascript
var person = {
  fullName: function(city, country) {
    return this.firstName + " " + this.lastName + " from " + city + ", " + country;
  }
};

var person1 = {
  firstName: "Jane",
  lastName: "Smith"
};

console.log(person.fullName.call(person1, "Oslo", "Norway")); 
// Jane Smith from Oslo, Norway
```

## apply() 메서드

- `apply()`는 `call()`과 거의 동일하지만, **인자를 배열로 받습니다.**

### 예시
```javascript
console.log(person.fullName.apply(person1, ["Oslo", "Norway"])); 
// Jane Smith from Oslo, Norway
```

## call() vs apply() 차이점

| 메서드 | 인자 형식 |
|--------|------------|
| `call()` | 각각의 인자를 개별로 전달 |
| `apply()` | 인자들을 **배열 형태**로 전달 |

### 예시
```javascript
person.fullName.call(person1, "Seoul", "Korea");
person.fullName.apply(person1, ["Seoul", "Korea"]);
```

# JavaScript 객체 메서드 (Object Methods)

## 개요

JavaScript에서는 객체를 효율적으로 조작하고 처리하기 위한 여러 내장 메서드를 제공합니다. 아래는 주요 객체 메서드들과 각각의 기능 및 사용 예시입니다.

## `Object.assign(target, source)`

- 하나 이상의 **source 객체**의 속성을 **target 객체**로 복사합니다.
- 기존의 target 객체를 변경하며, 반환값은 target 객체입니다.

### 예시
```javascript
const target = { a: 1 };
const source = { b: 2, c: 3 };

const result = Object.assign(target, source);
console.log(result); // { a: 1, b: 2, c: 3 }
```

## `Object.create(proto)`

- 주어진 프로토타입 객체를 갖는 **새로운 객체**를 생성합니다.
- 상속 구조를 만들 때 유용합니다.

### 예시
```javascript
const person = {
  greet: function() {
    return "Hello";
  }
};

const student = Object.create(person);
student.name = "Alice";

console.log(student.greet()); // Hello
```

## `Object.entries(obj)`

- 객체의 **[key, value] 쌍의 배열**을 반환합니다.
- 반복 처리나 변환에 자주 사용됩니다.

### 예시
```javascript
const user = { name: "Tom", age: 25 };
const entries = Object.entries(user);
console.log(entries); // [ ['name', 'Tom'], ['age', 25] ]
```

## `Object.fromEntries(entries)`

- `[key, value]` 배열의 리스트로부터 객체를 생성합니다.
- `Object.entries()`의 반대 기능입니다.

### 예시
```javascript
const entries = [['name', 'Jane'], ['age', 30]];
const obj = Object.fromEntries(entries);
console.log(obj); // { name: 'Jane', age: 30 }
```

## `Object.keys(obj)`

- 객체의 **속성 이름(key)**만을 배열로 반환합니다.

### 예시
```javascript
const person = { name: "Mike", age: 28 };
console.log(Object.keys(person)); // ['name', 'age']
```

## `Object.values(obj)`

- 객체의 **속성 값(value)**만을 배열로 반환합니다.

### 예시
```javascript
const person = { name: "Mike", age: 28 };
console.log(Object.values(person)); // ['Mike', 28]
```

## `Object.groupBy(items, callback)`

- 배열이나 객체의 요소들을 **callback 함수의 반환값**에 따라 그룹화합니다.
- ES2024에서 도입된 새로운 메서드입니다.

### 예시
```javascript
const people = [
  { name: "Alice", age: 20 },
  { name: "Bob", age: 21 },
  { name: "Charlie", age: 20 }
];

const grouped = Object.groupBy(people, person => person.age);
console.log(grouped);
// {
//   20: [{ name: 'Alice', age: 20 }, { name: 'Charlie', age: 20 }],
//   21: [{ name: 'Bob', age: 21 }]
// }
```

## `for...in` 반복문

- 객체의 **모든 열거 가능한 속성(key)**을 순회합니다.

### 예시
```javascript
const person = { name: "David", age: 35 };

for (let key in person) {
  console.log(key + ": " + person[key]);
}
// name: David
// age: 35
```

## Object Properties (객체 속성)

### 속성 추가 또는 변경: `Object.defineProperty()`

객체에 **새로운 속성을 추가**하거나, 기존 속성의 **속성 값이나 메타데이터를 수정**할 수 있습니다.

#### 문법
```javascript
Object.defineProperty(object, property, descriptor)
```

#### 예시: 새로운 속성 추가
```javascript
const person = {};
Object.defineProperty(person, 'name', {
  value: 'Alice',
  writable: true,
  enumerable: true,
  configurable: true
});
console.log(person.name); // Alice
```

### 여러 속성 추가 또는 변경: `Object.defineProperties()`

한 번에 **여러 개의 속성**을 정의할 수 있습니다.

```javascript
const person = {};
Object.defineProperties(person, {
  firstName: {
    value: 'John',
    writable: true
  },
  lastName: {
    value: 'Doe',
    writable: true
  }
});
console.log(person.firstName); // John
```

### 속성 접근: `Object.getOwnPropertyDescriptor()`

특정 속성의 **설정값(descriptor)** 정보를 반환합니다.

```javascript
const obj = { x: 10 };
const desc = Object.getOwnPropertyDescriptor(obj, 'x');
console.log(desc);
// { value: 10, writable: true, enumerable: true, configurable: true }
```

### 모든 속성의 디스크립터 확인: `Object.getOwnPropertyDescriptors()`

객체 내의 모든 속성에 대한 디스크립터 정보를 반환합니다.

```javascript
const obj = { x: 1, y: 2 };
const descriptors = Object.getOwnPropertyDescriptors(obj);
console.log(descriptors);
```

### 객체의 모든 속성 이름을 배열로 반환: `Object.getOwnPropertyNames()`

열거 가능 여부와 관계없이 **모든 속성 이름(key)**을 반환합니다.

```javascript
const obj = { a: 1, b: 2 };
console.log(Object.getOwnPropertyNames(obj)); // ['a', 'b']
```

---

### 열거 가능한 속성만 배열로 반환: `Object.keys()`

객체에서 **열거 가능한 속성들만** 반환합니다.

```javascript
const obj = { a: 1, b: 2 };
console.log(Object.keys(obj)); // ['a', 'b']
```

---

### 프로토타입 접근: `Object.getPrototypeOf()`

객체의 **프로토타입(상속 체계)**에 접근할 수 있습니다.

```javascript
const obj = {};
const proto = Object.getPrototypeOf(obj);
console.log(proto); // [Object: null prototype] {...}
```

### Getter와 Setter 추가: `Object.defineProperty()`

객체에 **getter와 setter**를 정의할 수 있습니다.

```javascript
const person = {
  firstName: 'John',
  lastName: 'Doe'
};

Object.defineProperty(person, 'fullName', {
  get() {
    return this.firstName + ' ' + this.lastName;
  },
  set(name) {
    const parts = name.split(' ');
    this.firstName = parts[0];
    this.lastName = parts[1];
  }
});

console.log(person.fullName); // John Doe
person.fullName = 'Jane Smith';
console.log(person.firstName); // Jane
```

## JavaScript Class

### 클래스 정의

- `class` 키워드를 사용해 클래스를 정의할 수 있습니다.
- 클래스에는 반드시 `constructor()` 메서드를 포함해야 합니다.

```javascript
class Car {
  constructor(name, year) {
    this.name = name;
    this.year = year;
  }
}
```

### constructor() 메서드

- 클래스에서 객체가 생성될 때 자동으로 실행되는 **특수 메서드**입니다.
- 객체의 **초기 속성값을 설정**할 때 사용됩니다.
- `constructor`는 정확히 그 이름이어야 하며, 생략 시 JavaScript가 자동으로 빈 생성자를 추가합니다.

### 클래스는 객체가 아닌 **템플릿**

- 클래스 자체는 객체가 아니며, 객체를 생성하기 위한 **청사진(템플릿)**입니다.
- `new` 키워드를 사용하여 인스턴스를 생성합니다.

#### 예시
```javascript
class Car {
  constructor(name, year) {
    this.name = name;
    this.year = year;
  }

  getInfo() {
    return this.name + ' - ' + this.year;
  }
}

const myCar = new Car("Hyundai", 2023);
console.log(myCar.getInfo()); // Hyundai - 2023
```

### 클래스 메서드

- 클래스 내에 정의된 함수는 **메서드**라고 하며, 일반 객체의 메서드와 동일한 문법을 사용합니다.

```javascript
class Animal {
  constructor(name) {
    this.name = name;
  }

  speak() {
    return this.name + ' makes a noise.';
  }
}

const dog = new Animal('Dog');
console.log(dog.speak()); // Dog makes a noise.
```