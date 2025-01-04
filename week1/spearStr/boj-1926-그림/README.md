# 🔎 BOJ-1926 그림
## 💡 아이디어
- DFS로 탐색
## ✔ 문제풀이
- 2차원 배열 `paper`를 전체 탐색
    - `paper[i][j]`값이 `1`이고 방문한 적이 없는(`visit[i][j]`값이 `false`) 경우에만 `DFS` 탐색
## 🤕 어려웠던 점
- 아직 파이썬 문법이 남아있어서 혼동이 온다.
    ```
    console.log(ans.length === 0 ? 0 : Math.max(...ans));
    ```
    - Math.max()를 이용할 때 전개 연산자로 ans배열을 풀어줘야 한다.