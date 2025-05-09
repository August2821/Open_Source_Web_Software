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

### 열거 가능한 속성만 배열로 반환: `Object.keys()`

객체에서 **열거 가능한 속성들만** 반환합니다.

```javascript
const obj = { a: 1, b: 2 };
console.log(Object.keys(obj)); // ['a', 'b']
```

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

- 클래스 자체는 객체가 아니며, 객체를 생성하기 위한 **템플릿**입니다.
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

---

# JavaScript DOM(Document Object Model)

## DOM이란?
- DOM(Document Object Model)은 HTML 문서를 트리 구조로 표현한 계층적 모델입니다.
- 브라우저는 HTML 문서를 로드한 뒤 DOM 트리를 생성하며, JavaScript는 이 DOM을 통해 웹 페이지를 동적으로 제어할 수 있습니다.

### 예시
```html
<!DOCTYPE html>
<html>
  <body>
    <h1 id="title">안녕하세요!</h1>
  </body>
</html>
```

이 HTML은 다음과 같은 DOM 트리 구조로 표현됩니다:

```
document
└── html
    ├── head
    └── body
        └── h1 (id="title")
```

## Document
- HTML 문서가 브라우저에 로드되면 `document` 객체로 변환됩니다.
- `document` 객체는 DOM의 루트 노드이며, 모든 노드에 접근할 수 있는 출발점입니다.

## Property (속성)
- 속성은 값을 가져오거나 변경할 수 있는 요소입니다.
- 예를 들어 HTML 요소의 내용을 변경하는 것이 대표적인 속성 조작입니다.

## Method (메서드)
- HTML 요소에 대해 수행할 수 있는 동작입니다.
- 예: HTML 요소 추가, 삭제 등

## Document, Methods and Property Example
```javascript
document.getElementById("demo").innerHTML = "Hello World!";
```
- `getElementById`는 메서드입니다.
- `innerHTML`은 속성입니다.

## JavaScript로 동적인 웹 페이지 구현
JavaScript는 DOM을 이용해 다음을 수행할 수 있습니다:
- HTML 내용 변경
- HTML 요소 및 속성 변경
- CSS 스타일 변경
- HTML 요소 및 속성 추가/삭제
- HTML 이벤트에 반응
- 새로운 HTML 이벤트 생성

## HTML 요소 찾기 및 접근

### ID로 찾기
```javascript
document.getElementById("demo");
```

### 태그 이름으로 찾기
```javascript
document.getElementsByTagName("p");
```

### 클래스 이름으로 찾기
```javascript
document.getElementsByClassName("example");
```

### CSS 선택자로 찾기
```javascript
document.querySelectorAll(".example p");
```

## HTML 요소 찾기 예시

### ID로 찾기
```html
<p id="demo">텍스트</p>
<script>
  const element = document.getElementById("demo");
  element.innerHTML = "변경된 텍스트";
</script>
```

### 태그 이름으로 찾기
```html
<p>첫 번째</p>
<p>두 번째</p>
<script>
  const elements = document.getElementsByTagName("p");
  elements[1].innerHTML = "두 번째 변경";
</script>
```

### 클래스 이름으로 찾기
```html
<p class="item">1</p>
<p class="item">2</p>
<p class="item">3</p>
<script>
  const items = document.getElementsByClassName("item");
  items[2].innerHTML = "세 번째 아이템";
</script>
```

## HTMLCollection 객체
- `getElementsByTagName`과 `getElementsByClassName`은 `HTMLCollection`을 반환합니다.
- 배열처럼 index로 접근하고 `length`를 사용할 수 있지만, 실제 배열은 아닙니다.

```javascript
const collection = document.getElementsByClassName("item");
for (let i = 0; i < collection.length; i++) {
  console.log(collection[i].innerHTML);
}
```

> **주의:** `push()`, `pop()` 같은 배열 메서드는 사용할 수 없습니다.

## 프로그램 결과 예시
```html
<p class="fruit">사과</p>
<p class="fruit">바나나</p>
<p class="fruit">오렌지</p>
<script>
  const fruits = document.getElementsByClassName("fruit");
  alert(fruits[1].innerHTML); // 바나나
</script>
```

## 리스트의 세 번째 요소 접근
```html
<ul>
  <li>첫 번째</li>
  <li>두 번째</li>
  <li>세 번째</li>
</ul>
<script>
  const items = document.getElementsByTagName("li");
  alert(items[2].innerHTML); // 세 번째
</script>
```

## CSS 선택자로 요소 찾기
```html
<div class="box">Box 1</div>
<div class="box">Box 2</div>
<script>
  const boxes = document.querySelectorAll(".box");
  boxes[1].innerHTML = "두 번째 박스";
</script>
```

## NodeList 객체
- `querySelectorAll`은 `NodeList`를 반환합니다.
- `NodeList`도 `length`와 index를 사용할 수 있지만 배열은 아닙니다.
- 배열 메서드는 사용할 수 없습니다.

## HTML 문서 객체
```javascript
document.body           // <body> 요소 반환
document.head           // <head> 요소 반환
document.forms          // 모든 <form> 요소 반환
document.images         // 모든 <img> 요소 반환
document.scripts        // 모든 <script> 요소 반환
document.title          // 문서 제목 반환
```

### 예시
```javascript
console.log(document.body.innerHTML);
```

## HTML 콘텐츠 변경
```javascript
document.getElementById("myText").innerHTML = "변경됨";
```

## HTML 속성 변경
```javascript
document.getElementById("myImage").src = "newimage.jpg";
```

## form 값 설정
```javascript
document.getElementById("username").value = "홍길동";
```

## 연습: 비밀번호 확인
```html
<input type="password" id="pw1">
<input type="password" id="pw2">
<p id="result"></p>
<script>
  const pw1 = document.getElementById("pw1").value;
  const pw2 = document.getElementById("pw2").value;
  if (pw1 === pw2) {
    document.getElementById("result").innerHTML = "비밀번호 일치";
  } else {
    document.getElementById("result").innerHTML = "불일치";
  }
</script>
```

## CSS 스타일 변경
```javascript
document.getElementById("box").style.color = "red";
```

### 이벤트 발생 시 스타일 변경
```javascript
document.getElementById("box").onclick = function() {
  this.style.backgroundColor = "yellow";
};
```

## display 및 position 속성 변경
```javascript
document.getElementById("myDIV").style.display = "none";       // 요소 숨김
document.getElementById("myDIV").style.position = "absolute";  // 위치 고정
```

## 배경색 토글 버튼 예시
```html
<body id="myBody" style="background-color: white;">
  <button onclick="toggleBg()">배경 토글</button>
  <script>
    function toggleBg() {
      const body = document.getElementById("myBody");
      if (body.style.backgroundColor === "white") {
        body.style.backgroundColor = "black";
      } else {
        body.style.backgroundColor = "white";
      }
    }
  </script>
</body>
```

---

# JavaScript DOM Navigation

## HTML 문서의 모든 것은 노드(Node)이다

HTML 문서에서 각각의 구성 요소는 모두 "노드(Node)"로 구성된 트리 구조로 표현됩니다.

- 전체 문서는 **문서 노드(Document Node)**  
- 각 HTML 요소는 **요소 노드(Element Node)**  
- HTML 요소 내부의 텍스트는 **텍스트 노드(Text Node)**  
- 주석은 **주석 노드(Comment Node)**  

### 예시
```html
<!-- 주석 노드 -->
<p id="text">안녕하세요</p>
```

이 구조는 다음과 같이 분해됩니다:
- `<p>`: 요소 노드
- `"안녕하세요"`: 텍스트 노드
- `<!-- ... -->`: 주석 노드

## 트리 구조에서의 노드 관계

DOM은 계층 구조(hierarchical structure)를 가집니다.

- 부모(Parent): 상위 노드
- 자식(Child): 하위 노드
- 형제(Sibling): 같은 부모를 가진 노드들

### 계층적 구조 예시
```html
<div>
  <p>첫 번째 문장</p>
  <p>두 번째 문장</p>
</div>
```

- `div`는 `p`들의 **부모**
- 각 `p`는 `div`의 **자식**
- 두 `p`는 서로 **형제 노드**

## 노드 간의 관계 요약

- 트리 구조의 최상단 노드는 **루트 노드(root node)**  
- 모든 노드는 **하나의 부모**를 가짐 (루트 노드는 제외)
- 노드는 **여러 자식**을 가질 수 있음
- 같은 부모를 가진 노드들은 **형제 노드**

## 노드 탐색을 위한 주요 속성 (Node Properties)

| 속성/메서드 | 설명 |
|-------------|------|
| `parentNode` | 부모 노드를 반환 |
| `childNodes[n]` | 자식 노드 중 n번째 노드를 반환 |
| `firstChild` | 첫 번째 자식 노드를 반환 |
| `lastChild` | 마지막 자식 노드를 반환 |
| `nextSibling` | 다음 형제 노드를 반환 |
| `previousSibling` | 이전 형제 노드를 반환 |
| `textContent` | 해당 노드의 텍스트 콘텐츠를 반환 |
| `nodeValue` | 텍스트 또는 주석 노드의 실제 값 반환 |
| `nodeName` | 노드의 이름 반환 (예: `DIV`, `P`) |
| `nodeType` | 노드 유형을 숫자로 반환 (1: 요소, 3: 텍스트 등) |

## 노드 탐색 예제

HTML 예시:
```html
<title id="demo">DOM Tutorial</title>
```

JavaScript 예시:
```javascript
const el = document.getElementById("demo");

// 방법 1
let value1 = el.innerHTML;

// 방법 2
let value2 = el.firstChild.nodeValue;

// 방법 3
let value3 = el.childNodes[0].nodeValue;
```

## 요소 추가 및 삭제 (DOM 조작)

| 메서드 | 설명 |
|--------|------|
| `document.createElement("tagname")` | 새로운 요소 생성 |
| `document.createTextNode("text")` | 텍스트 노드 생성 |
| `parent.appendChild(node)` | 자식 노드로 추가 |
| `parent.removeChild(child)` | 자식 노드를 제거 |
| `parent.replaceChild(new, old)` | 기존 노드를 새로운 노드로 교체 |

## DOM 조작의 기본 원리

1. 요소 생성  
   ```javascript
   const newDiv = document.createElement("div");
   ```

2. 속성 및 텍스트 추가  
   ```javascript
   newDiv.textContent = "새로운 박스";
   newDiv.setAttribute("class", "box");
   ```

3. 문서에 삽입  
   ```javascript
   document.body.appendChild(newDiv);
   ```

## 요소 추가 예시 (createElement + appendChild)

```html
<div id="container"></div>

<script>
  const container = document.getElementById("container");
  const newP = document.createElement("p");
  newP.textContent = "새 문장";
  container.appendChild(newP);
</script>
```

## 텍스트 노드를 활용한 추가 예시

```html
<div id="content"></div>

<script>
  const p = document.createElement("p");
  const text = document.createTextNode("텍스트 노드로 추가됨");
  p.appendChild(text);
  document.getElementById("content").appendChild(p);
</script>
```

## 요소 삭제 예시

```html
<ul id="list">
  <li>첫 번째</li>
  <li>두 번째</li>
</ul>

<script>
  const ul = document.getElementById("list");
  const li = ul.getElementsByTagName("li")[0];
  ul.removeChild(li);
</script>
```

## 요소 교체 예시 (replaceChild)

```html
<div id="box">기존 박스</div>

<script>
  const newDiv = document.createElement("div");
  newDiv.textContent = "새 박스";

  const oldDiv = document.getElementById("box");
  document.body.replaceChild(newDiv, oldDiv);
</script>
```

## 실습 예제: 간단한 To-Do 리스트 만들기

```html
<input id="taskInput" type="text">
<button onclick="addTask()">추가</button>
<ul id="todoList"></ul>

<script>
  function addTask() {
    const input = document.getElementById("taskInput");
    const newTask = document.createElement("li");
    newTask.textContent = input.value;

    const list = document.getElementById("todoList");
    list.appendChild(newTask);
    input.value = "";
  }
</script>
```

## HTML 요소 탐색 방법: HTMLCollection vs NodeList

| 구분 | HTMLCollection | NodeList |
|------|----------------|----------|
| 반환 방법 | `getElementsByTagName`, `getElementsByClassName` | `querySelectorAll` |
| 포함 노드 | 요소 노드(Element Node)만 포함 | 요소, 속성, 텍스트 노드 포함 가능 |
| 접근 방식 | 이름(name), id, index | index만 가능 |
| 실시간 반영 | 예 (DOM 변경 시 자동 반영됨) | 아니오 (정적 리스트) |

### 예시
```javascript
const collection = document.getElementsByClassName("item"); // HTMLCollection
const nodelist = document.querySelectorAll(".item"); // NodeList

console.log(collection.length);  // 가능
console.log(nodelist.length);   // 가능
```

---

# JavaScript Events

JavaScript는 **이벤트(event)**가 발생했을 때 실행됩니다. 이벤트는 사용자의 행동에 반응하여 웹 페이지를 동적으로 만듭니다.

## JavaScript는 이벤트가 발생할 때 실행될 수 있다

웹 페이지에서 어떤 동작(예: 클릭, 입력 등)이 발생하면 JavaScript 코드가 실행되도록 설정할 수 있습니다.

## 이벤트의 종류

- 사용자가 마우스를 클릭할 때 (`onclick`)
- 웹 페이지가 로드될 때 (`onload`)
- 이미지가 로드될 때 (`onload`)
- 마우스가 요소 위로 움직일 때 (`onmouseover`)
- 입력 필드가 변경될 때 (`onchange`)
- HTML 폼이 제출될 때 (`onsubmit`)
- 사용자가 키를 누를 때 (`onkeydown`, `onkeyup`, `onkeypress`)

## 사용자가 마우스를 클릭했을 때

### `onclick` 이벤트

```html
<button onclick="alert('버튼이 클릭되었습니다!')">클릭하세요</button>
```

- `onclick`은 클릭 시 실행될 동작을 지정합니다.

## 입력 필드가 변경되었을 때

### `onchange` 이벤트

```html
<input type="text" onchange="alert('내용이 변경되었습니다')">
```

- 사용자가 입력한 값을 변경하고 포커스를 벗어날 때 실행됩니다.

## 이미지 확대 (이벤트 발생 시)

### `onmouseover` & `onmouseout`

```html
<img src="sample.jpg" width="200" 
     onmouseover="this.style.width='300px'" 
     onmouseout="this.style.width='200px'">
```

- `onmouseover`: 마우스가 이미지 위에 있을 때 실행됩니다.
- `onmouseout`: 마우스가 이미지 밖으로 나갔을 때 실행됩니다.

## addEventListener() 메서드

`addEventListener()`는 이벤트가 발생했을 때 실행할 함수를 등록합니다.

### 구문

```javascript
element.addEventListener("이벤트", 함수, useCapture);
```

- `"이벤트"`: 이벤트 이름 (`click`, `mouseover` 등)
- `함수`: 실행할 함수
- `useCapture` (선택): true면 캡처링, false면 버블링 (기본값)

### 예시

```javascript
const btn = document.getElementById("myBtn");
btn.addEventListener("click", function() {
  alert("버튼 클릭됨!");
});
```

```javascript
const image = document.getElementById("myImage");
image.addEventListener("mouseover", function() {
  image.style.width = "300px";
});
image.addEventListener("mouseout", function() {
  image.style.width = "200px";
});
```

## Practice 5: 글자 수 세는 간단한 예제 (Character Counter)

```html
<textarea id="myTextarea" rows="4" cols="50"></textarea>
<p id="counter">0자</p>

<script>
  const textarea = document.getElementById("myTextarea");
  const counter = document.getElementById("counter");

  textarea.addEventListener("input", function() {
    counter.textContent = textarea.value.length + "자";
  });
</script>
```

- 사용자가 텍스트를 입력할 때마다 글자 수를 표시합니다.
- `input` 이벤트는 입력이 변경될 때마다 발생합니다.