# 🔎 BOJ-1644 소수의 연속합
## 💡 아이디어
- 에라토스테네스의 체로 소수 구하기
- 투 포인터를 활용해서 연속합 구하기
## ✔ 문제풀이
- 에라토스테네스의 체를 통해 `n`보다 같거나 작은수까지 소수 배열을 구함
- 투 포인터를 활용
    - 소수배열의 0번째 인덱스부터 탐색하여 하나씩 더해가기
    - 연속합이 `n`보다 같거나 작을때는 점점더해가고 `n`보다 클때는 가장 왼쪽의 인덱스의 소수를 연속합에서 빼기
    ```
    let sum = primeArray[right];
    while (primeArray[right] <= n) {
        if (sum === n) {
            cnt += 1;
            right += 1;
            sum += primeArray[right];
        } else if (sum < n) {
            right += 1;
            sum += primeArray[right];
        } else {
            sum -= primeArray[left];
            left += 1;
        }
    }
    ```
## 🤕 어려웠던 점
- 에라토스테네스의 체가 떠올랐지만 이게 무엇이었는지 기억이 나지 않아서 찾아보았다.