# 🔎 PRGS-충돌 위험 찾기
## 💡 아이디어
- 구현
## ✔ 문제풀이
- 자료구조
    - `position` : 1번부터 n번까지의 출발지 및 도착지의 역할을 하는 위치 (Map 사용)
    - `robots` : 로봇의 번호를 key값으로 하여 경유지를 포함한 `path`와 `index`를 set으로 갖는 Map사용
    - `board` : 로봇이 몇개가 있는지 세는 2차원 배열 -> 로봇이 2개 이상있다면 충돌로 판정 (checkCollision 함수)
    - `robotQueue` : 다음에 이동가능한 로봇의 번호를 담은 큐
    - `tmpQueue` : 한 회차 이동을 한 후에 `robotQueue`로 대체하기 위한 일시적인 큐
    - `finish` : 이동이 끝난 로봇들을 카운트
- 풀이
    - 자료구조의 값들을 채운 뒤에 맨 처음 0초부터 충돌이 있을 수 있으므로 `board`를 채우고 충돌 확인
    - 그 후에 while문을 통해 한칸씩 이동하면서 `board`를 채우며 조건에 맞게 이동 및 경유지에 도착하면 `index`를 증가시킴

## 🤕 어려웠던 점
- `routes`가 시작과 끝만 가는 줄 알았는데 경유지가 있다는 것을 뒤늦게 알았고, 그것을 수정하는 것이 어려웠다.
- 많은 자료구조를 사용해서 복잡했다.
- 만약, 시간복잡도와 메모리의 제한이 있었다면 어떻게 풀어야할지 조금 암담하다.