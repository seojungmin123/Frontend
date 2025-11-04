#1 Emmet(에밋)
몇가지 코드를 입력하면 자동으로 완성해주는 기능

모든 에밋 : https://docs.emmet.io/cheat-sheet/

<br>

## 자주쓰이는것들

### html

- 자식요소 ( > )<br>
`div>ul>li`
```html
<div>
    <ul>
        <li></li>
    </ul>
</div>
```

<br>

- 형제요소 ( + )<br>
`div>p+span`
```html
<div>
    <p></p>
    <span></span>
</div>
```

<br>

- 올라가기 ( ^ )<br>
`div>ul>li^p+a`
```html
<div>
   <ul>
       <li></li>
   </ul>
   <p></p>
   <a href=""></a>
</div>
```

(여러번 가능)<br>
`div>ul>li^^div`
```html
<div>
   <ul>
       <li></li>
   </ul>
</div>
<div></div>
```

<br>

- 반복하기 ( * )<br>
`div>ul>li*3`
```html
<div>
   <ul>
       <li></li>
       <li></li>
       <li></li>
   </ul>
</div>
```

<br>

- 그룹화 ( () )<br>
`div>(header>ul>li*2)+footer`
```html
<div>
   <header>
       <ul>
           <li></li>
           <li></li>
       </ul>
   </header>
   <footer></footer>
</div>
```

<br>

### html 속성

- 클래스 .class <br>
`div.container`
```html
<div class="container"></div>
```

<br>

- 아이디 #id<br>
`span#Hello`
```html
<span id="hello"></span>
```

<br>

- 속성 [attr] <br>
`td[title="bye" colspan=5]`
```html
<td title="bye" colspan="5"></td>
```

<br>

- 넘버링 $ <br>
순서대로 나열 <br>
`ul>li.item$5`
```html
<ul>
   <li class="item1"></li>
   <li class="item2"></li>
   <li class="item3"></li>
   <li class="item4"></li>
   <li class="item5"></li>
</ul>
```

- 넘버링 \$ @ <br>
뒤의숫자부터 시작 <br>
`ul>li.item$@5*5`
```html
<ul>
   <li class="item5"></li>
   <li class="item6"></li>
   <li class="item7"></li>
   <li class="item8"></li>
   <li class="item9"></li>
</ul>
```

<br>

- 텍스트 {} <br>
`.name{seo}`
```html
<div class="name">seo</div>
```

<br>

### CSS

- p -> %

- e -> em

- :a -> auto

```css
h100p

/* emmet 변환 ▼ */

height: 100%;
```

```css
m10p30e5

/* emmet 변환 ▼ */

margin: 10% 30em 5px;
```

```css
m0:auto

/* emmet 변환 ▼ */

margin: 0 auto;
```

<br>

참고
- [https://inpa.tistory.com/entry/HTML-%F0%9F%8E%A8-Emmet-%EB%AC%B8%EB%B2%95-%EC%A0%95%EB%A6%AC]