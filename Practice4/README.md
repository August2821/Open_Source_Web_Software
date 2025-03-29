# CSS의 `position` 속성

CSS의 `position` 속성은 요소의 배치 방법을 결정하는 속성입니다. `position` 속성을 사용하면 요소를 문서 흐름에서 벗어나 원하는 위치에 배치할 수 있습니다.

## `position`의 속성 값

### 1. `static`
- 기본값이며, 요소가 문서의 일반적인 흐름에 따라 배치됩니다.
- `top`, `left`, `right`, `bottom`, `z-index` 속성이 적용되지 않습니다.

```css
.element {
    position: static;
}
```

### 2. `relative`
- 요소가 원래 위치를 기준으로 상대적으로 이동합니다.
- `top`, `left`, `right`, `bottom` 값을 사용하여 이동할 수 있습니다.
- 원래 위치가 유지되므로, 다른 요소들은 영향을 받지 않습니다.

```css
.element {
    position: relative;
    top: 10px;
    left: 20px;
}
```

### 3. `absolute`
- 요소가 문서 흐름에서 제거되고, 가장 가까운 `relative`, `absolute`, `fixed` 조상 요소를 기준으로 배치됩니다.
- 조상 요소 중 `position`이 설정되지 않은 경우, `body`를 기준으로 배치됩니다.

```css
.parent {
    position: relative;
}

.child {
    position: absolute;
    top: 50px;
    left: 100px;
}
```

### 4. `fixed`
- 요소가 뷰포트를 기준으로 고정됩니다.
- 스크롤을 하더라도 요소의 위치가 변하지 않습니다.

```css
.element {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    background-color: black;
    color: white;
}
```

### 5. `sticky`
- 스크롤 위치에 따라 `relative`와 `fixed` 속성이 동적으로 변합니다.
- 특정 스크롤 위치에 도달하기 전에는 `relative`, 도달 후에는 `fixed`처럼 동작합니다.

```css
.element {
    position: sticky;
    top: 50px;
    background-color: yellow;
}
```

## 정리
| 속성 값  | 설명 |
|----------|------------------------------------------------|
| `static`  | 기본값, 일반적인 문서 흐름을 따름 |
| `relative` | 원래 위치를 기준으로 상대적으로 이동 |
| `absolute` | 문서 흐름에서 제거되고 조상 요소를 기준으로 배치 |
| `fixed` | 뷰포트를 기준으로 고정, 스크롤해도 위치 유지 |
| `sticky` | 특정 스크롤 위치에서 `fixed`처럼 동작 |

