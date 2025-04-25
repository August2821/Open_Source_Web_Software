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

