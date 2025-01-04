# 🔎 BOJ-10825 국영수
## 💡 아이디어
- 객체를 만들어서 정렬로 비교
## ✔ 문제풀이
- 주어진 입력값을 이름과 각 과목의 점수값을 갖고있는 객체들을 저장하는 배열로 저장
- 조건에 맞게 정렬 후 출력
## 🤕 어려웠던 점
- 처음 제출 결과 때 소요시간이 `4000ms`가 나와서 당황했다.
    - 기존코드
        ```
        score.forEach((student) => {
            console.log(student.name);
        });
        ```
    - 수정코드
        ```
        console.log(score.map((student) => student.name).join('\n'));
        ```
- 개선 후에 결과는 400ms로 줄었다. 무려 10배의 차이를 줄인 것인데 `console.log`를 할때 앞으로는 `join`을 활용해서 한번에 출력할 수 있도록 하는 것으로 해야겠다.
![image](https://github.com/user-attachments/assets/b8c1f30b-8d25-4794-8724-92f4d2991655)