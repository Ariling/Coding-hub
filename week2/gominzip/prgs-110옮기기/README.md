# 🔎 문제이름

prgs 110옮기기

## 💡 아이디어

- 값을 작게 만들기
- 가능한 경우들 생각해보기
  - 0000011111111 => 첫번째 11을 110으로
  - 1111111111111 => 첫번째 11을 110으로
  - 100100100100 => 0 뒤로
  - 1010101010101 => 1010101010101110 < 1010101010101101 0뒤로 1 앞으로
  - 10101111111111 => 첫번째 11을 110으로
  - 011 => 011011

## ✔ 문제풀이

1. 문자열에서 110 제거
2. 11이 있는지 확인 -> 앞에 있는 11부터, 11 앞에 110 삽입
3. 만약 11이 없다면 가장 마지막 0뒤로 110 삽입

## 🤕 어려웠던 점

- 아직 js에서 문자열 조작하는게 어렵다... 메서드랑 정규식 익히기
- 첫 풀이에서는 110 제거를 replace 사용

```js
while (replacedStr.includes("110")) {
  replacedStr = replacedStr.replace(/110/g, "");
}
```

해당 방식으로 하면 O(k \* n)의 복잡도 발생 -> 18번부터 시간초과...
따라서 O(n)으로 줄이기 위해 스택 방식 사용

```js
let stack = [];

for (let char of str) {
  stack.push(char);
  if (
    stack.length >= 3 &&
    stack[stack.length - 1] === "0" &&
    stack[stack.length - 2] === "1" &&
    stack[stack.length - 3] === "1"
  ) {
    stack.pop();
    stack.pop();
    stack.pop();
  }
}

let baseStr = stack.join("");
```
