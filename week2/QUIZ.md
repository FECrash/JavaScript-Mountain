## 📝 2주차 퀴즈

### 빈 칸 채우기

ex) 스터디 리더는 (**양아름**) 입니다.

1. var 변수 생성 과정은 ()이고, let과 const의 변수 생성 과정은 ()이다.
2. let, const를 초기화 전에 사용할 수 없도록 ES6에서 추가한 기능은 ()이다.
3. 프로퍼티 접근 표현식에는 두 가지가 있는데 ()와 ()이다.
4. && 연산자는 왼쪽에 있는 첫 번째 피연산자부터 평가하기에 ()를 이용하면 `2 > 5 && 3 > 1`이라는 코드는 오른쪽이 실행되지 않는다.
5. false 같은 값은 (), (), (), (), (), ()가 있다.
6. number는 () 타입이다.
7. object는 () 타입이다.
8. 표현식은 ()를 통해 값으로 바뀌지만, 문은 ()을 통해 어떤 동작을 수행한다.

### O / X 퀴즈 (만약 X라면 이유도 작성하면 좋아요!)

ex) 스터디는 매주 목요일마다 진행됩니다.
X, 매주 금요일마다 진행됩니다.

1. 호이스팅은 자바스크립트 언어를 개발한 초기부터 존재했다.  
   **답**:

2. null은 true 같은 값이다.  
   **답**:

3. 자바스크립트에서 사용되지 않는 메모리는 개발자가 직접 삭제해야 한다.  
   **답**:

4. 점 식별자 문법을 이용하면 계산 결과로 나오는 변수 값으로도 객체에 접근할 수 있다.  
   **답**:

5. 자바스크립트 변수 타입은 크게 나누면 2가지가 있다.  
   **답**:

### 코드 퀴즈

1. 아래 코드는 표현식 일까요? 문 일까요? (어떤 표현식, 문인지 작성하면 더 좋아요!)

```javascript
10 + 30; // 답:
('Hello!'); // 답:

const grade = 'B'; //답:
grade; // 답:

true && false; // 답:

const isGenius = () => true; // 답:
isGenius(); //답:
```

1. 아래 `console.log(areum === copyAreum)`에서는 어떤 값이 출력될까요?

```javascript
const areum = {
  name: '양아름',
  email: 'areumsheep@gmail.com',
};
const copyAreum = [...areum];

console.log(areum === copyAreum);
```

**답**:

3. 아래 `console.log(함수_선언문())`, `console.log(함수_표현식())`에서는 어떤 값이 출력될까요?

```javascript
console.log(함수_선언문());
console.log(함수_표현식());

function 함수_선언문() {
  return '함수 선언문';
}
const 함수_표현식 = function () {
  console.log('함수 표현식');
};
```

4. 아래 `console.log(a)`, console.log(b)`에서는 어떤 값이 출력될까요?

```javascript
var a = 1;
var b;

function a() {
  console.log('123');
}
function b() {
  console.log('123');
}

console.log(a);
console.log(b);
```

> 출처: https://velog.io/@surim014/JavaScript%EC%97%90%EC%84%9C%EC%9D%98-Hoisting%EC%9D%B4%EB%9E%80-%EB%AC%B4%EC%97%87%EC%9D%B8%EA%B0%80
