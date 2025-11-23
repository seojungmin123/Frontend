# String 객체

[length](#length) <br>
[charat()](#charat) <br>
[charCodeAt()](#charcodeat)

[concat()](#concat)

[search()](#search) <br>
[indexOf()](#indexof) <br>
[lastIndexOf()](#lastindexof) <br>
[includes()](#includes)

[replace()](#replace) <br>
[split()](#split) <br>
[slice()](#slice) <br>
[substring()](#substring)

[match()](#match)

[toLowerCase()](#tolowercase) <br>
[toUpperCase()](#touppercase)

[trim()](#trim) <br>
[trimEnd()](#trimend) <br>
[trimStart()](#trimstart)

[toString()](#tostring) <br>
[padStart()](#padstart) <br>
[padEnd()](#padend)

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
console.log('홍길순 :', a4); // -1 (값을 찾지못해 -1 반환)
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

<br>

## indexOf()

https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/String/indexOf

객체에서 주어진 값과 일치하는 첫 번째 인덱스를 반환함. (**일치하는 값이 없으면 -1을 반환**)

대소문자를 구분함.

```js
// searchValue : 찾으려는 문자열
// fromIndex : 문자열에서 찾기 시작하는 위치를 나타내는 인덱스 값 (생략가능)

str.indexOf(searchValue[, fromIndex])
str.search(searchValue[, fromIndex]) :
// indexOf와 같음, 근데 search는 정규표현식 처리 가능 (보통은 indexOf 사용)

---

let str = '안녕하세요 홍길동 입니다. 지금은 스트링 객체 연습중';

let a1 = str.indexOf('홍');
let a2 = str.indexOf('객체');
let a3 = str.indexOf('홍길동');
let a4 = str.indexOf('홍길순');
let a5 = str.indexOf('지금', 12);
let a6 = str.indexOf('객체', 20); // 시작위치 지정해주면 검색 더빠름

console.log('홍 :', a1); // 6 (인덱스 위치 반환)
console.log('객체 :', a2); // 23
console.log('홍길동 :', a3); // 6
console.log('홍길순 :', a4); // -1 (값을 찾지못해 -1 반환)
console.log('지금 :', a5); // 15
console.log('객체 :', a6); // 23

---

ex)
btn.addEventListener('click', function () {
                txt = t1.value;
                console.log(txt);
                if (str.indexOf(txt) > 0) {
                    box.textContent = `${txt} 글자를 찾음`;
                } else {
                    box.textContent = `${txt} 글자를 찾지못함`;
                }
            });
```

<br>

## lastIndexOf()

https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/String/lastIndexOf

indexOf인데 역순으로 탐색

<br>

## includes()

https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/String/includes

하나의 문자열이 다른 문자열에 포함되어 있는지를 판별한 후, true 또는 false로 반환함

검색 시 대소문자를 구분함

indexOf, search랑 비슷함

```js
// searchString : 이 문자열에서 찾을 다른 문자열. (정규표현식X)
// position : searchString을 찾기 시작할 위치. (기본값 0)

includes(searchString)
includes(searchString, position)
// 문자열을 찾아내면 true, 실패하면 false 반환

---

let str = '안녕하세요 홍길동 입니다. 지금은 스트링 객체 연습중';

let a1 = str.includes('홍'); // true
let a2 = str.includes('객체'); // true
let a3 = str.includes('홍길동'); // true
let a4 = str.includes('홍길순'); // false
let a5 = str.includes('지금'); // true

---

// 영문은 대소문자를 구별함
str = 'hi Html CSS JAVAscript react';

console.log(str.includes('hi')); // true
console.log(str.includes('HTML')); // false (대소문자 달라서)

---
ex)
btn.addEventListener('click', () => {
                txt = t1.value;
                console.log(txt);
                if (str.includes(txt)) {
                    box.textContent = `${txt} 글자를 찾음`;
                } else {
                    box.textContent = `${txt} 글자를 찾지못함`;
                }
            });
```

<br>

## replace()

https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/replace

단일, 일부 혹은 모든 일치 항목이 replacement로 대치된 새로운 문자열을 반환함

```js
replace(pattern, replacement)
replace(변경 전 문자열, 변경 후 문자열)

let newstr = str.replace('html', 'javascript');
console.log(newstr); // javascript css
```

<br>

## split() 

https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/String/split

String 객체를 첫번째 인수로 전달된 문자열로 분리하여 유사배열로 반환함

인수가 없을 경우, 전체의 문자열을 각각의 문자로 나누어 유사배열로 반환

```js
// separator : 원본 문자열을 끊어야 할 부분을 나타내는 문자열을 나타냄. (문자열이나 정규표현식)
// separator가 빈 문자열일 경우 str의 각각의 문자가 배열의 원소 하나씩으로 변환됨
// limit : 끊어진 문자열의 최대 개수를 나타내는 정수

split();
split(separator);
split(separator, limit);

---

str = '안녕하세요';
let a1 = str.split();
console.log(a1); // Array(1)

a1 = str.split('');
console.log(a1); // Array(5)

a1 = str.split(' ');
console.log(a1); // Array(1)

str = '우동 과일 사과 사탕 라면';
a1 = str.split(` `); // 공백 기준으로 분리
console.log(a1); // Array(5)

str = '김철수, 황미애, 서지수';
a1 = str.split(', '); // 콤마, 기준으로 분리해 배열처리
console.log(a1); // Array(3)

str = '010 - 0000 - 1111'; // 분리- 배열처리
a1 = str.split('-');
console.log(a1[0]); // 010 
console.log(a1[1]); //  0000 
console.log(a1[2]); //  1111

str = '901010-1111111';
a1 = str.split('-');
console.log(a1); // Array(2)
console.log(a1[0]); // 901010
console.log(a1[1]); // 111111
```

<br>

## slice()

https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/String/slice

substring() 과 동일

문자열의 일부를 추출하여 이를 새로운 문자열로 반환함. 원본 문자열은 수정하지 않음

음수의 인수를 전달할 수 있음

```js
//indexStart : 첫 번째 문자의 인덱스.
//indexEnd: 반환될 부분 문자열에서 제외될 첫 번째 문자열의 인덱스.
slice(indexStart)
slice(indexStart, indexEnd)

---

const str1 = "The morning is upon us."; // str1의 길이는 23

console.log(`${str1.slice(1, 8)}`); // he morn
console.log(`${str1.slice(4, -2)}`); // morning is upon u
console.log(`${str1.slice(12)}`); // is upon us.
console.log(`${str1.slice(30)}`); // ""

						 -9-8-7-6-5-4-3-2-1
const str2 = '안녕하세요 홍길동';
						  0 1 2 3 4 5 6 7 8

console.log(`${str.slice(0,3)}`); // 안녕하
console.log(`${str.slice(2,5)}`); // 하세요
console.log(`${str.slice(2)}`); // 하세요 홍길동
console.log(`${str.slice()}`); // 안녕하세요 홍길동
console.log(`${str.slice(-5,-1)}`); // 요 홍길
console.log(`${str.slice(-5)}`); // 요 홍길동
```

## substring()

https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/String/substring

string 객체의 시작 인덱스로 부터 종료 인덱스 전 까지 문자열의 부분 문자열을 반환함

```js
//indexStart : 반환문자열의 시작 인덱스
//indexEnd : 옵션. 반환문자열의 마지막 인덱스 (포함하지 않음, 끝위치 -1 까지 출력)

str.substring(indexStart[, indexEnd])

---

let str = '안녕하세요 홍길동 입니다.';

console.log(`${str.substring(0,3)}`); // 안녕하 (0,1,2까지, indexEnd는 포함X)
console.log(`${str.substring(2,5)}`); // 하세요
console.log(`${str.substring(2)}`); // 하세요 홍길동 입니다. (indexEnd가 생략됨)
```

만약 indexEnd 가 생략된 경우, substring() 문자열의 끝까지 모든 문자를 추출함

<br>

## match()

https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/String/match

문자열이 정규식과 매치되는 부분을 검색함

<br>

## toLowerCase()

https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/String/toLowerCase

문자열을 소문자로 변환

<br>

## toUpperCase()

https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/String/toUpperCase

문자열을 대문자로 변환

<br>

## trim()

https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/String/trim

문자열 양 끝 공백 제거 후,

원본 문자열을 수정하지 않고 새로운 문자열을 반환함

```js
let str = `   안녕 자바스크립트   `;

console.log(`|${str}|`); // |   안녕 자바스크립트   |
console.log(`|${str.trim()}|`); // |안녕 자바스크립트|
```

<br>

## trimEnd()

https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/String/trimEnd

문자열 마지막의 공백을 제거한 후, 

원본 문자열을 수정하지 않고 새로운 문자열을 반환함
```js
let str = `   안녕 자바스크립트   `;

console.log(`|${str}|`); // |   안녕 자바스크립트   |
console.log(`|${str.trimEnd()}|`); //  |   안녕 자바스크립트|
```

<br>

## trimStart()

https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/String/trimStart

문자열 시작부분의 공백을 제거한 후, 

원본 문자열을 수정하지 않고 새로운 문자열을 반환함
```js
let str = `   안녕 자바스크립트   `;

console.log(`|${str}|`); // |   안녕 자바스크립트   |
console.log(`|${str.trimStart()}|`); //  |안녕 자바스크립트   |
```

<br>

## toString()

https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/Object/toString

숫자, 불리언, 배열, 객체 등을 **문자열로 반환**함

```js
// toString : 문자열 반환, 10진수->2,8,16 반환
x = 255;

// 문자열 변경
let a1 = x.toString(); // 기본 10진수
console.log('x : ', x, '/', a1, typeof a1);
a1 = x.toString(2); // 2진수
a1 = x.toString(8); // 8진수
a1 = x.toString(16); // 16진수
console.log('a1 : ', a1);
```

<br>

## padStart()

https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/String/padStart

현재 문자열의 시작을 다른 문자열로 채워, 주어진 길이를 만족하는 새로운 문자열을 반환함

```js
// targetLength : 목표 문자열 길이. 현재 문자열의 길이보다 작다면 채워넣지 않고 그대로 반환.
// padString : 현재 문자열에 채워넣을 다른 문자열. 문자열이 너무 길어 목표 문자열 길이를
// 초과한다면 좌측 일부를 잘라서 넣음. 기본값은 " ". (U+0020)

str.padStart(targetLength [, padString])
// str.padStart(자리수, 채워질값)

---
str = '8';

console.log(str.padStart(8, '0')); // 00000008
console.log(str.padStart(8, '#')); // #######8
console.log(str.padStart(8, 0)); // 00000008
console.log(str.padStart(8, 0)); // 00000008
console.log(str.padStart(8, 'abc')); // abcabca8
```

<br>

## padEnd()

https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Global_Objects/String/padEnd

현재 문자열의 끝을 다른 문자열로 채워, 주어진 길이를 만족하는 새로운 문자열을 반환함

```js
// targetLength : 목표 문자열 길이. 현재 문자열의 길이보다 작다면 채워넣지 않고 그대로 반환.
// padString : 현재 문자열에 채워넣을 다른 문자열. 문자열이 너무 길어 목표 문자열 길이를
// 초과한다면 좌측 일부를 잘라서 넣음. 기본값은 " ". (U+0020)

str.padEnd(targetLength [, padString])
// str.padEnd(자리수, 채워질값)

---
str = '8';

console.log(str.padEnd(5, '0')); // 80000;
```

