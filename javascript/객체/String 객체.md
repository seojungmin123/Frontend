# String 객체

<br>

## length

https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/String/length

UTF-16 코드 유닛을 기준으로 문자열의 총 길이(총 갯수)를 나타냄

공백도 1자리씩 인식함
```js
let str = "hello";
console.log(str.length); // 5
```
<br>

## charAt()

https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/String/charAt

**문자열에서 특정 인덱스에 위치**하는 유니코드 **단일문자 1개를 반환**함

인덱스 0부터. ( 0과 문자열의 길이 - 1 사이의 정수값 )

```js
str.charAt(index);
// 인덱스 지정X 시 기본값 0.

let str = '안녕하세요 홍길동 입니다.';
            console.log(`길이 : ${str.length}`);
            console.log(`0번 : ${str.charAt(0)}`); // 안
            console.log(`1번 : ${str.charAt(1)}`); // 녕
            console.log(`2번 : ${str.charAt(2)}`); // 하
            console.log(`3번 : ${str.charAt(3)}`); // 세
            console.log(`4번 : ${str.charAt(4)}`); // 요

            for (let i = 0; i < str.length - 1; i++) {}
            console.log(`${i}번 : ${str.charAt(i)}`);

// 만약 인덱스가 문자열 길이보다 큰 경우에는 빈 문자열 (예) " "  반환
```

<br>

## charCodeAt()

https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/charCodeAt

주어진 인덱스의 UTF-16 코드 단위를 표현하는 `0`과 `65535` 사이의 정수를 반환함

<br>

## concat()

https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/String/concat

잘 안씀

매개변수로 전달된 모든 문자열을 호출 문자열에 붙인 새로운 문자열을 반환함

문자열은 +연결, 굳이 concat 안씀

<br>

## search()

https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/search

객체에서 주어진 값과 일치하는 첫 번째 인덱스를 반환함. (일치하는 값이 없으면 -1을 반환)

대소문자를 구분함

**정규표현식 처리가 가능**함

```js
// searchValue : 찾으려는 문자열
// fromIndex : 문자열에서 찾기 시작하는 위치를 나타내는 인덱스 값 (생략가능)

str.indexOf(searchValue[, fromIndex])
str.search(searchValue[, fromIndex]) :
// indexOf와 같음, 근데 search는 정규표현식 처리 가능 (보통은 indexOf 사용)

---

let str = '안녕하세요 홍길동 입니다. 지금은 스트링 객체 연습중';

let a1 = str.search('홍');
let a2 = str.search('객체');
let a3 = str.search('홍길동');
let a4 = str.search('홍길순');
let a5 = str.search('지금', 12);
let a6 = str.search('객체', 20); // 시작위치 지정해주면 검색 더빠름

console.log('홍 :', a1); // 6 (인덱스 위치 반환)
console.log('객체 :', a2); // 23
console.log('홍길동 :', a3); // 6
console.log('홍길순 :', a4); // -1 (값을 찾지못해 -1 반환.)
console.log('지금 :', a5); // 15
console.log('객체 :', a6); // 23

---

// 정규표현식

str = 'hi Html CSS JAVAscript react';
let regex = /hi/;
a1 = str.search(regex);
console.log('/hi/ : ', a1); // /hi/ : 0

// 영문은 대소문자 구별해서 search하기 (정규표현식 i 플래그 사용)
// i : 대소문자 구별 없이 처리
regex = /HTML/i;
a1 = str.search(regex);
console.log('/HTML/ : ', a1); // /HTML/ : 3
```