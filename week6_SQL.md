# 📘 SQL_BASIC 6주차 정규 과제

SQL_BASIC 정규 과제는 매주 정해진 분량의 `초보자를 위한 BigQuery(SQL) 입문` 강의를 듣고, 핵심 개념을 정리한 뒤 간단한 SQL 문제를 직접 풀어보는 방식으로 진행합니다.

이번 주는 SQL 입문 과정의 핵심 고비인 `JOIN`을 학습합니다.

JOIN은 여러 테이블을 연결해서 분석 질문에 답하기 위해 반드시 필요한 개념입니다. 이번 주 과제에서는 정답 코드뿐 아니라 **어떤 테이블을 어떤 키로 연결했는지**를 꼭 기록해주세요.

완성된 과제는 Github에 업로드하고, 링크를 스프레드시트 'SQL' 시트에 입력해 제출해주세요.

**👀 수행 인증란은 필수입니다.**

---

## 📚 SQL_BASIC_6th_TIL

### 섹션 6. 다량의 자료를 연결 : JOIN

### 5-2. JOIN 이해하기

### 5-3. 다양한 JOIN 방법

### 5-4. JOIN 쿼리 작성하기

### 5-5. JOIN을 처음 공부할 때 헷갈리는 부분

---

## ✨ 선택 강의

- 5-6. JOIN 연습문제: JOIN 문제를 더 연습하고 싶을 때 선택 수강

---

## 🏁 전체 강의 수강 계획

| 주차 | 필수 강의 범위 | 선택 강의 | 완료 여부 |
| --- | --- | --- | --- |
| 1주차 | 1-1 ~ 2-1 | 1 | ✅ |
| 2주차 | 2-2 ~ 2-3 | 2-4 | ✅ |
| 3주차 | 2-5, 2-7 ~ 2-8 | 2-6 | ✅ |
| 4주차 | 3-2 ~ 4-3 | 3-4 | ✅ |
| 5주차 | 4-4 ~ 4-6 | 4-5, 4-7 | ✅ |
| 6주차 | 5-2 ~ 5-5 | 5-6 | ✅ |
| 7주차 | 필수 강의 없음 | 6-2, 6-3, 6-4, 6-5 | 🍽️ |

---

<br>

<!-- 여기까진 그대로 둬 주세요-->

---

# 1️⃣ 개념 정리

아래 키워드 중 중요하다고 생각한 개념을 2개 이상 골라 짧게 정리해주세요. 3개보다 더 많이 정리하고 싶다면 자유롭게 항목을 추가해도 좋습니다.

이번 주 키워드:
- JOIN
- INNER JOIN
- LEFT JOIN
- JOIN key
- alias
- NULL
- 다중 JOIN

## 01.

```
개념 이름: JOIN
개념 설명:
- n개의 테이블이 있을 때 공통적으로 가지는 key값을 기준으로 테이블을 합치는 것
- 컬럼이 계속 추가됨
- 여러 테이블 join이 가능함
- 헷갈리지 않게 단계적으로 join하는게 중요
- 보통 id 값을 key로 많이 사용
- 여러가지 데이터를 활용해서 분석해야하기 때문에 join을 해야함
예시 쿼리:
SELECT
  A.COL1,
  A.COL2,
  B.COL11,
  B.COL12
FROM table1 AS A
LEFT JOIN table2 AS B
ON A.KEY=B.KEY
```

## 02.

```
개념 이름: NULL
개념 설명:
- 값이 없음, 알 수 없음을 나타내는것
- 0이나 공백과 다르게 값이 아예 없는 것
- JOIN에선 연결할 값이 없을 경우에 나타난다
- LEFT JOIN 할때 조건에 맞는 값이 없어서 NULL이 나올 수 있음
예시 쿼리: X
```

## (선택) 03.

```
개념 이름:
개념 설명:
헷갈린 점:
```

---

# 2️⃣ 수행 인증란

아래 중 하나 이상을 첨부해주세요.

<img width="506" height="403" alt="image" src="https://github.com/user-attachments/assets/3e88efa5-c06a-490e-be7f-d6676be7c4fe" />


---

# 3️⃣ 확인 문제

프로그래머스는 로그인이 필요하므로, 로그인 후 문제 풀이를 진행해주세요.

## 🧩 문제 1

문제 링크: [조건에 맞는 도서와 저자 리스트 출력하기](https://school.programmers.co.kr/learn/courses/30/lessons/144854)

풀이 과정:

```
- 사용한 테이블: BOOK, AUTHOR
- JOIN key:AUTHOR_ID
- 날짜를 출력한 형식:YYYY-MM-DD 형식으로 출력
```


<img width="334" height="235" alt="image" src="https://github.com/user-attachments/assets/e7ba6991-389a-454b-8c3b-04db02568930" />


## 🧩 문제 2

문제 링크: [상품 별 오프라인 매출 구하기](https://school.programmers.co.kr/learn/courses/30/lessons/131533)

풀이 과정:

```
- 연결한 테이블: PRODUCT, OFFLINE_SALE
- JOIN key: PRODUCT_ID
- 집계한 값: 상품코드별 총매출
```

<img width="303" height="218" alt="image" src="https://github.com/user-attachments/assets/2f692ee9-fc35-4e8a-8695-8b42ac3644cc" />


## 🧩 문제 3

문제 링크: [없어진 기록 찾기](https://school.programmers.co.kr/learn/courses/30/lessons/59042)

풀이 과정:

```
- 기준이 되는 왼쪽 테이블: ANIMAL_OUTS
- LEFT JOIN이 필요한 이유: 입소 기록이 없는 동물도 입양 기록에서 유지하기 위해서 
- NULL이 발생하는 경우: 같은 ANIMAL_ID가 ANIMAL_INS에 없어 연결되는 입소 기록이 없는 경우에 NULL이 발생한
```

<img width="318" height="214" alt="image" src="https://github.com/user-attachments/assets/62b7be8f-aef3-422b-ab6c-eeb12a1ac84c" />

## 🧩 문제 4

문제 링크: [있었는데요 없었습니다](https://school.programmers.co.kr/learn/courses/30/lessons/59043)

풀이 과정:

```
- 사용한 테이블: ANIMAL_INS, ANIMAL_OUTS
- JOIN key:ANIMAL_ID
- 비교한 날짜 컬럼: O.DATETIME<I.DATETIME
- 정렬 기준: I.DATETIME 오름차순
```

<img width="271" height="189" alt="image" src="https://github.com/user-attachments/assets/d7b7d73f-e718-40c8-b22a-a4e52ca04a1f" />


---

# 4️⃣ 참고 자료

JOIN 개념이 헷갈린다면 아래 자료를 함께 참고해도 좋습니다.

1. https://data-marketing-bk.tistory.com/entry/SQL-JOIN-%ED%95%9C-%EB%B0%A9%EC%97%90-%EC%A0%95%EB%A6%AC-%EA%B0%9C%EB%85%90%EB%B6%80%ED%84%B0-%EC%BD%94%EB%93%9C%EA%B9%8C%EC%A7%80-%EC%9D%B4%EA%B2%83%EB%A7%8C-%EB%B3%B4%EC%9E%90
2. https://velog.io/@wijoonwu/JOIN

---

# 5️⃣ 이번 주 회고

```
1. INNER JOIN과 LEFT JOIN의 차이를 어떻게 이해했는지: INNER JOIN은 두 테이블에서 일치하는 행만 가져오고 LEFT JOIN은 왼쪽 테이블의 모든 행을 유지하고 일치하는 값이 없으면 NULL로 표시한다
2. JOIN 문제를 풀 때 가장 먼저 확인해야 할 것: KEY 값과 어떤 테이블을 기준으로 할지 확인한다.
3. JOIN 결과가 예상과 달랐던 경험이 있다면: X
```

수고하셨습니다!



