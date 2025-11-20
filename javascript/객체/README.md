# 객체

객체란 현실세계의 객체를 컴퓨터 언어로 변경한 것. ( 객체 : 눈에 보이는 모든 사물 )

객체에는 속성(key)과 메소드(method)가 있음

- 객체.속성(key) : 고유값, 기본값
- 객체.메소드() : 행동

ex) 

강아지객체.속성 : 성별, 종, 털색, 나이... <br>
강아지객체.메소드() : 뛰기, 걷기, 구르기, 꼬리흔들기...

값(value)으로 숫자, 문자, boolean, null, undefined, 함수, 배열, object 등 모두 가능

object를 만드려면 {} 중괄호 사용

object 내부에서는 = 말고 : 사용

각 항목 뒤에는 콤마( , ) 사용. < 뒤에 다른 property가 올 수 있기 때문

( 마지막 항목에도 , 붙이기 < 수정할 때 용이함 )

```js
// 객체 object
const player = {
	name: "jungmin", // 키(key) : 값(value)
	points: 10,
	fat: true,
	['tel']: '010-1111-2222',
	info(){
			console.log(`${this.name}의 연락처는 ${this.tel}입니다.`);
	},
};

// 접근 방법!!!!!!!!!!
player.name; // 방법 1
player["name"]; // 방법 2
/*
객체명이랑 속성, 메소드 연결할때
객체명.키(속성) <- . 써도되고
객체명['키'] <- [] 대괄호 써도 됨 (react는 대괄호가 주)
*/

//속성 출력
console.log(`이름 : ${cat.name}`);
console.log(`나이 : ${cat.age}`);
console.log(`털색 : ${cat['color']}`);
console.log(`음식 : ${cat['food']}`);

//메소드 출력
cat.run();
cat.eat();
cat.sleep();

// 추가, 수정
console.log(player); // {name: "jungmin", points: 10, fat: true}

player.fat = false; // object 항목 업데이트 true > false
player.points = player.points + 15; // object 항목 업데이트 10 + 15

player.lastName = "potato"; // object 항목 추가 방법1
player['color'] = "white"; // object 항목 추가 방법2

console.log(player); // {name: "jungmin", points: 25, fat: false, lastName: "potato"}

// 삭제
delete player.fat;

// 객체의 값을 반환해서 넘겨줄 수 있음.
const fn1 = () => {
    return {
        name: '유재석',
        age: 22,
        addr: '울산',
        tel: '010-3333-4444',
    };
};
const fn2 = () => {
    return () => {
        return {
            name: '김고은',
            age: 20,
            addr: '서울',
            tel: '010-1111-2222',
        };
    };
};

```

---

### 객체타입

1. **원시타입**
    
    원시타입은 값을 기억함
    number, bigint, string, boolean, null, undefined, symbol >> 값은 변수에 직접 저장됨
    
2. **참조타입**
    
    참조타입은 주소를 기억함
    array, function, object >> 값은 객체나 배열이 저장된 메모리 주소를 가리키는 포인터임
    
<br>

### 객체 종류

- **JS object** :
    
    JS Engine 메모리 안에 데이터 구조, 클라이언트에서 처리
    
    ```js
    let 객체명 = {
        키 : 값,
        키 : 값 <- 숫자, '문자', 배열, 객체, 논리 등이 들어갈 수 있음.
        메소드 : function(){
            행동의 명령들
        },
        메소드 : 익명함수(){
            
        }
        메소드(){ <- 이렇게도 사용 가능.
    
        }
    }
    ```
    
- **JSON** :
    
    객체 내용을 기술하기 위한 text파일, 서버와 클라이언트가 데이터를 주고받음
    
    주석 못씀. 공백을 무시함
    
    **키, 문자값은 꼭 "이중따옴표"로 감싸야함.**
    
    ```js
    let 객체명 = {
        "키" : "값",
        "키" : "문자",
        "키" : 숫자, 논리값,
        "키" : 배열, 객체
    }
    ```
    
    +
    
    JSON은 .json 확장자
    JSON은 함수를 값으로 할당X
    
- 파싱, 변환 방법
    
    JSON을 JS object로 파싱 : JSON.parse()
    JS object를 JSON으로 변환 : JSON.stringify()
    
<br>

### 객체구조

- **1. 복합구조**
    
    객체 안에 배열, 객체 등 들어감
    
    ```js
    let obj1 = {
        name: '인평',
        since: '2025',
        depart: ['AI소프트웨어과', '에코자동차과', '자동차바디튜닝과'],
        info: {
            age: 18,
            addr: '인천',
        },
    };
    console.log(obj1.name);
    console.log(obj1.since);
    console.log(obj1.depart[0]);
    console.log(obj1.depart[2]);
    console.log(obj1.info.age);
    console.log(obj1.info.addr);
    console.log(obj1.info['age']);
    console.log(obj1['info'].addr);
    ```
    
- **2. 계층구조**
    
    값 = 변수 => 객체 연결
    
    객체나 배열 등을 객체 안에 담아서, 연결해서 사용
    
    ```js
    // 값 = 변수 => 객체 연결
    // 객체나 배열 등을 객체 안에 담아서, 연결해서 사용
    const pos = { x: 50, y: 20 };
    const sizeObj = { width: 100, height: 200 };
    const obj2 = {
        center: pos,
        size: sizeObj,
        color: 'pink',
    };
    console.log(obj2.center.x);
    console.log(obj2.center.y);
    console.log(obj2.size.width);
    ```
    
- **3. 목록구조**
    
    ```js
    const x = { name: '이재명', age: 61, addr: '안동' };
    const y = { name: '윤석열', age: 64, addr: '서울' };
    const classObj1 = {
        list: [x, y],
    };
    // 둘이 같음.
    const classObj2 = {
        list: [
            { name: '이재명', age: 61, addr: '안동' },
            { name: '윤석열', age: 64, addr: '서울' },
        ],
    };
    for (let i = 0; i < classObj1.list.length; i++) {
        console.log(`이름 : ${classObj1.list[i].name}`);
        console.log(`나이 : ${classObj1.list[i].age}`);
        console.log(`주소 : ${classObj1.list[i].addr}`);
    }
    ```
    

---
<br>

- **object - 단축 프로퍼티**
    
    (객체 속성의 이름과 값이 동일한 경우, 속성 이름을 생략할 수 있음)
    
    ```js
    const name = 'clark';
    const age = 20;
    
    const person = {
    	name: name,
    	age: age,
    	gender: 'male',
    }
    ```
    
    ```jsx
    const name = 'clark';
    const age = 20;
    
    const person = {
    	name, // name: name,
    	age, // age: age,
    	gender: 'male',
    }
    
    ```
    

- **object - 프로퍼티의 존재 여부 확인 ( in 연산자 사용 )**
    
    어떤 값이 넘어올지 확신할 수 없을 때 사용
    
    ```js
    const person = {
    	name: 'clark',
    	age: 20,
    }
    
    // 확인해보기
    person.birthDay; // undefined
    
    'birthDay' in person; // false
    'age' in person ; // true
    ```
    
    ```js
    // 응용해보기
    
    function isAdult(user) {
    	if (!('age' in user) || user.age < 20) { //user안에 age가 없거나 age가 20보다 작은 경우
    		return false;
    	}
    	return true;
    }
    
    const Mike = {
    	name : 'Mike',
    	age : 30,
    };
    
    const Jane = {
    	name : 'Jane',
    };
    
    console.log(isAdult(Jane)); // false
    console.log(isAdult(Mike)); // true 
    ```