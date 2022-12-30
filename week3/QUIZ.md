## 📝 3주차 퀴즈

### 빈 칸 채우기

ex) 스터디 리더는 (양아름) 입니다.

1. 배열과 비슷하지만 배열 메서드가 없는 객체를 (`array-like object`)라 한다.
2. (`arguments`)는 나머지 연산자가 존재하지 않을 때 모든 인수를 얻는 유일한 방법이었다.
3. 배열을 생성하는 방법 중 ES6에서 추가된 방법은 (`Array.of()`), (`Array.from()`) 이다.
4. 인덱스가 연속적이지 않은 배열을 (`성긴배열(희소배열)`)라고 한다.
5. 자바스크립트 타입 변경하는 방법에는 (`명시적 타입 변화`), (`암묵적 타입 변화`) 총 2가지가 있다.
6. ECMAScript가 아닌 JavaScript 언어 내부에서 정의된 작업을 (`추상 작업`)라고 한다. ES6에서는 재정의하여 사용할 순 있지만, 직접 실행시킬 수는 없다.

### O / X 퀴즈 (만약 X라면 이유도 작성하면 좋아요!)

ex) 스터디는 매주 목요일마다 진행됩니다.
X, 매주 금요일마다 진행됩니다.

1. V8 엔진을 사용하는 크롬을 기준으로 배열 비슷한 객체를 사용하는 것이 배열을 사용하는 것보다 좋다.
   **답**: X, V8 엔진에서 배열을 forEach로 호출하는 것보다 느리기 때문에 배열 비슷한 객체보다 배열을 사용하는 것이 좋다.

2. 배열 비슷한 객체를 배열로 변경하는 방법은 Array.of()를 사용하면 된다.
   **답**: X, 배열 비슷한 객체를 배열로 변경하는 방법은 '전개 연산자', 'Array.from()', 'slice()'가 있다.

3. `+` 연산자는 ToPrimitive 추상 작업이 일어난다.
   **답**: O, 원시타입이 아닌 항목에 대해서는 ToPrimitive 추상 작업이 일어난다.

4. ToPrimitive 추상 작업에는 파라미터의 PreferredType을 통해 3가지 선호 알고리즘이 존재한다.
   **답**: O, '문자 선호 알고리즘', '숫자 선호 알고리즘', '선호 없음 알고리즘' 3가지가 존재한다.

5. `-` 연산자는 ToPrimitive 추상 작업이 일어난다.
   **답**: O, `+` 연산자와 마찬가지로 원시타입이 아닌 항목에 대해서는 ToPrimitive 추상 작업이 일어난다.

### 코드 퀴즈

1. 배열 비슷한 객체를 간단히 코드로 구현해보세요!

```javascript
// 배열 비슷한 객체 구현해보기
const arrayLike = {
  0: "array",
  1: "like",
  2: "object"
};
```

2. 배열 생성하는 5가지 방법을 모두 이용해 간단히 코드로 구현해보세요!

```javascript
// 1) 배열 리터럴
const a = [1, 2, 3];  // [1, 2, 3]
// 2) 분해 연산자
const b = [...a, 4];  // [1, 2, 3, 4]
// 3) Array() 생성자
const c = new Array();  // []
const d = new Array(3); // [,,]
const e = new Array(1, 2, 3, "array"); // [1, 2, 3, "array"]
// 4) Array.of()
const f = Array.of(); // []
const g = Array.of(3); // [3]
// 5) Array.from()
// * 선택사항인 두 번째 인자를 사용한 코드를 구현해보세요!
const h = Array.from([1, 2, 3], x => x = x * 2); // [2, 4, 6];
```

3. ToPrimitive 추상 작업을 구현한 코드입니다. 주석으로 표현한 빈칸을 직접 채워보세요!
   (자바스크립트의 ToPrimitive 추상 작업을 임의로 구현한 코드로, 동일하지 않습니다.)

```javascript
const toPrimitive = (input, PreferredType) => {
  let hint = 'default';

  if (PreferredType === 'String') {
    hint = 'string';
  } else if (PreferredType === 'Number') {
    hint = 'number';
  }

  if (input[Symbol.toPrimitive]) {
    const getToPrimitive = input[Symbol.toPrimitive](hint);
    if (typeof getToPrimitive !== 'object') {
      return getToPrimitive();
    } else {
      throw new TypeError('Cannot convert object to primitive value');
    }
  } else {
    if (hint === 'default') {
      // 여기에는 어떤 코드가 들어갈까요?
      // 힌트: 선호 없음 알고리즘은 기본적으로 숫자를 더 선호합니다.
      hint = 'number';
    }
    return OrdinaryToPrimitive(input, hint);
  }
};

const OrdinaryToPrimitive = (input, hint) => {
  let methodNames = [];
  // 여기에는 어떤 코드가 들어갈까요?
  // 힌트: hint의 값에 따라 실행할 메서드의 순서가 다릅니다. 이 코드를 통해 선호하는 알고리즘을 지정할 수 있습니다.
  if (hint === 'number') {
    methodNames = ['valueOf', 'toString'];
  } else {
    methodNames = ['toString', 'valueOf'];
  }

  for (const methodName of methodNames) {
    const method = input[methodName];
    if (typeof method === 'function') {
      const result = method.call(input);
      if (typeof result !== 'object') {
        return result;
      }
    }
  }

  throw new TypeError('Cannot convert object to primitive value');
};
```
