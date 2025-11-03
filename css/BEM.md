# BEM

클래스 명명 규칙

<br>

## BEM을 쓰는 이유?

1. 목적 또는 기능을 전달
2. 구성 요소의 구조를 전달
3. 선택자 명시도를 항상 낮은 수준으로 유지

<br>

## 어떻게 동작하는가?

<br>

## 1. 블록(Block)

구성요소의 가장 바깥쪽 상위요소를 블록으로 정의

### Naming
문자, 숫자, 대시(` - `)로 구성 가능

<br>

### HTML
block, box1, main-container 등등 모두 블록 역할
```html
<div class="block">
    ...
</div>
<div class="box1">
    ... 
</div>
<div class="main-container">
    ... 
</div>
```

<br>

### CSS

- 클래스 이름만 사용
- 태그 이름, ID 중첩 사용 금지
- 다른 블록에 대한 종속성 x

<br>

#### Good
```css
.block {
    background-color: #fff;
}
```

#### Bad
```css
div.block {
    background-color: #fff;
}
#id.block {
    background-color: #fff;
}
```

<br>

## 2. 요소(Element)

블록의 하위 요소이며 모든 요소는 상위 블록과 연결

### Naming
문자, 숫자, 대시(` - `) 및 밑줄(` _ `)로 구성 가능 <br>
`블록이름__요소이름` 의 형태로 작성

<br>

### HTML
```html
<div class="block">
    <div class="block__content"></div>
</div>
<div class="box1">
    <div class="box1__apple"></div>
</div>
<div class="main-container">
    <div class="main-container__item"></div>
</div>
```

<br>

### CSS
- 클래스 이름만 사용
- 태그 이름, ID 중첩 사용 금지

<br>

#### Good
```css
.block__content {
    background-color: #fff;
}
```

#### Bad
```css
.box1 .box1__apple {
    background-color: #fff;
}
div.box1__apple {
    background-color: #fff;
}
```

<br>

## 3. 수정자(Modifier)

### Naming
문자, 숫자, 대시(` - `) 및 밑줄(` _ `)로 구성 가능 <br>
`블록이름--수정자이름` 혹은 `요소이름--수정자이름` 의 형태로 작성 <br>
수정자의 이름이 길거나 공백이 있다면 하나의 대시를 사용 `블럭이름--border-black`

<br>

### HTML

#### Good
블록 혹은 요소의 클래스는 그대로 두고 수정자를 추가
```html
<div class="block block--size-big">
    <div class="block__content block__content--mod"></div>
</div>
<div class="box1 box1--size-small">
    <div class="box1__apple box1__apple--red"></div>
</div>
<div class="main-container main-container--bordered">
    <div class="main-container__item main-container__item--background-black"></div>
</div>
```

#### Bad
기존 블록 혹은 요소의 클래스는 아예 삭제하고 수정자를 추가
```html
<div class="block--size-big">
    <div class="block__content--mod"></div>
</div>
<div class="box1--size-small">
    <div class="box1__apple--red"></div>
</div>
<div class="main-container--bordered">
    <div class="main-container__item--background-black"></div>
</div>
```

<br>

### CSS
수정 시 수정자 클래스명 사용

#### 1. 블록 수정자를 기반으로 수정
```css
.block--size-big .block__content{
    background-color: #fff;
}
```

#### 2. 요소 수정자를 사용하여 수정
```css
.block__content--mod{
    background-color: #fff;
}
```

<hr>

숫자는 01,02 ...

ID는 카멜표기법 ( headerMenu )

class는 BEM 따라서 작성하기

<br>

참고
- [https://velog.io/@nemo/bem]
- [https://naradesign.github.io/bem-by-example.html]