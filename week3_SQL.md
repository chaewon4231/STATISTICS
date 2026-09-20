# 📘 SQL_BASIC 3주차 정규 과제

SQL_BASIC 정규 과제는 매주 정해진 분량의 `초보자를 위한 BigQuery(SQL) 입문` 강의를 듣고, 핵심 개념을 정리한 뒤 간단한 SQL 문제를 직접 풀어보는 방식으로 진행합니다.

이번 주는 집계 함수와 `GROUP BY`, `HAVING`을 학습합니다.

완성된 과제는 Github에 업로드하고, 링크를 스프레드시트 'SQL' 시트에 입력해 제출해주세요.

**👀 수행 인증란은 필수입니다.**

---

## 📚 SQL_BASIC_3rd_TIL

### 섹션 3. 데이터 탐색 - 조건, 추출, 요약

### 2-5. 집계(GROUP BY + HAVING + SUM/COUNT)

### 2-7. 정리

### 2-8. 새로운 집계 함수 소개(GROUP BY ALL, 2024-02-26에 나온 함수)

---

## ✨ 선택 강의

- 2-6. 연습 문제: 집계와 조건 조회를 더 연습하고 싶을 때 선택 수강

---

## 🏁 전체 강의 수강 계획

| 주차 | 필수 강의 범위 | 선택 강의 | 완료 여부 |
| --- | --- | --- | --- |
| 1주차 | 1-1 ~ 2-1 | 1 | ✅ |
| 2주차 | 2-2 ~ 2-3 | 2-4 | ✅ |
| 3주차 | 2-5, 2-7 ~ 2-8 | 2-6 | ✅ |
| 4주차 | 3-2 ~ 4-3 | 3-4 | 🍽️ |
| 5주차 | 4-4 ~ 4-6 | 4-5, 4-7 | 🍽️ |
| 6주차 | 5-2 ~ 5-5 | 5-6 | 🍽️ |
| 7주차 | 필수 강의 없음 | 6-2, 6-3, 6-4, 6-5 | 🍽️ |

---

<br>

<!-- 여기까진 그대로 둬 주세요-->

---

# 1️⃣ 개념 정리

아래 키워드 중 중요하다고 생각한 개념을 2개 이상 골라 짧게 정리해주세요. 3개보다 더 많이 정리하고 싶다면 자유롭게 항목을 추가해도 좋습니다.

이번 주 키워드:
- COUNT
- SUM
- AVG
- MAX
- MIN
- GROUP BY
- HAVING
- 집계 기준

## 01.

```
개념 이름: GROUP BY
개념 설명:
- 같은 값끼리 모아서 그룹화 하는것.
- 중복이 있다면 중복을 없애서 하나의 데이터를 만듦.  
- 특정 컬럼을 기준으로 모으면서 다른 컬럼에선 집계가 가능하다. (합,평균,MAX,MIN)
- 평균, 수를 집계하는걸 많이 씀(정확한 검증을 위해서 둘 다 쓰는 경우가 많은것같음 평균만 가지고 판단하기에는 특수값 때문에 평균이 달라질 수 있으니까)
- 내림차순으로 정렬(ORDER BY)도 가능
- 그룹화 한 값에 조건 설정 가능 (집계 후 조건에는 HAVING 쓰기)
- 집계할 컬럼을 SELECT에 명시하고 그 컬럼을 꼭 GROUP BY에 작성해야함
예시 쿼리:
SELECT
  집계할_컬럼1
  집계함수(COUNT,MAX,MIN 등)
FROM TABLE
GROUP BY
  집계할_컬럽1

```

## 02.

```
개념 이름: HAVING
개념 설명:
- GROUP BY 한 후 조건을 설정하고 싶은 경우 사용
- 집계를 하면서 형성된 컬럼에 조건을 달고 싶을 때 HAVING 사용
- 쿼리의 FROM절에 다른 쿼리가 들어갈수도 있음(WHERE절로 바꾸는거 가능)
- WHERE절과 HAVING절의 차이
  * WHERE은 TABLE(원본)데이터의 조건을 설정하고 싶을때 사용
  * HAVING은 GROUP BY랑 거의 같이 쓰이고 집계후에 사용
예시 쿼리:
SELECT
  컬럼1,컬럼2
  COUNT(컬럼1)AS COL1_COUNT
FROM <TABLE>
GROUP BY 컬럼1, 컬럼2
HAVING
  COL1_COUNT>3
```

## (선택) 03.

```
개념 이름:
개념 설명:
헷갈린 점:
```

---

# 2️⃣ 수행 인증란

<img width="1051" height="556" alt="image" src="https://github.com/user-attachments/assets/893e79e5-e8b8-488a-b4e4-2341d48eb259" />


---

# 3️⃣ 확인 문제

프로그래머스는 로그인이 필요하므로, 로그인 후 문제 풀이를 진행해주세요.

## 🧩 문제 1

문제 링크: [최댓값 구하기](https://school.programmers.co.kr/learn/courses/30/lessons/59415)

풀이 과정:

```
- 문제 요구사항: 동물 보호소에 가장 최근에 들어온 동물의 시각을 조회하기 
- 사용한 SQL 절: select, from 절과 최댓값을 구하는 집계 함수인 Max()함수를 사용하였다.
- 새로 배운 점: 집계함수를 사용하여 특정값을 조회할 수 있다는 점을 배웠다. 
```

<<img width="435" height="264" alt="image" src="https://github.com/user-attachments/assets/3ba938e1-8ad7-4c69-8256-b9b12bcdb9cd" />
>

## 🧩 문제 2

문제 링크: [가장 비싼 상품 구하기](https://school.programmers.co.kr/learn/courses/30/lessons/131697)

풀이 과정:

```
- 사용한 집계 함수: Max()
- 집계 대상 컬럼: Price
- 결과를 검증한 방법: 가장 큰 금액이 22000이 나오는지 확인하고, 요구사항대로 컬럼명이 MAX_price로 변경되어 나오는지 검증했다.   
```

<img width="446" height="344" alt="image" src="https://github.com/user-attachments/assets/da9d4732-8402-4631-b1cd-265e49cad82a" />

## 🧩 문제 3

문제 링크: [고양이와 개는 몇 마리 있을까](https://school.programmers.co.kr/learn/courses/30/lessons/59040)

풀이 과정:

```
- 그룹화 기준: ANIMAL_TYPE
- WHERE와 HAVING 중 사용한 절: 사용하지 않았다.
- 처음 틀렸다면 틀린 이유: 집계 결과를 COUNT 로 별칭 지정하지 않아서 틀렸었다.
- 새로 배운 SQL 패턴: COUNT함수를 이용해 범주별 개수를 세는 패턴을 배웠다. 
```

<img width="432" height="418" alt="image" src="https://github.com/user-attachments/assets/184d06a3-59d1-4029-9ba4-6477778c0d45" />

---

# 4️⃣ 이번 주 회고

```
1. 문제를 SQL로 옮길 때 가장 어려웠던 부분: AS를 이용해 컬럼명을 문제 요구사항에 맞게 바꾸는 부분이 가장 어려웠다. 
2. WHERE와 HAVING의 차이를 어떻게 이해했는지:
  * WHERE은 TABLE(원본)데이터의 조건을 설정하고 싶을때 사용
  * HAVING은 GROUP BY랑 거의 같이 쓰이고 집계후에 사용
3. 다음 주에 더 연습하고 싶은 문제 유형: GROUP BY 와 HAVING 절을 함께 사용해서 그룹별 집계 조건을 다루는 복잡한 조건의 문제들을 연습해보고 싶다. 
```

수고하셨습니다!




