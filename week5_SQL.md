# 📘 SQL_BASIC 5주차 정규 과제

SQL_BASIC 정규 과제는 매주 정해진 분량의 `초보자를 위한 BigQuery(SQL) 입문` 강의를 듣고, 핵심 개념을 정리한 뒤 간단한 SQL 문제를 직접 풀어보는 방식으로 진행합니다.

이번 주는 날짜/시간 데이터와 조건문을 학습합니다. 특히 `CASE WHEN`은 SQL 문제 풀이와 데이터 분석에서 자주 사용되므로, 직접 분류 기준을 만들고 결과를 확인하는 연습을 해주세요.

완성된 과제는 Github에 업로드하고, 링크를 스프레드시트 'SQL' 시트에 입력해 제출해주세요.

**👀 수행 인증란은 필수입니다.**

---

## 📚 SQL_BASIC_5th_TIL

### 섹션 5. 데이터 탐색 - 변환

### 4-4. 날짜 및 시간 데이터 이해하기

### 4-6. 조건문(CASE WHEN, IF)

---

## ✨ 선택 강의

- 4-5. 시간 데이터 연습문제: 날짜/시간 함수를 더 연습하고 싶을 때 선택 수강
- 4-7. 조건문 연습문제: CASE WHEN과 IF를 더 연습하고 싶을 때 선택 수강

---

## 🏁 전체 강의 수강 계획

| 주차 | 필수 강의 범위 | 선택 강의 | 완료 여부 |
| --- | --- | --- | --- |
| 1주차 | 1-1 ~ 2-1 | 1 | ✅ |
| 2주차 | 2-2 ~ 2-3 | 2-4 | ✅ |
| 3주차 | 2-5, 2-7 ~ 2-8 | 2-6 | ✅ |
| 4주차 | 3-2 ~ 4-3 | 3-4 | ✅ |
| 5주차 | 4-4 ~ 4-6 | 4-5, 4-7 | ✅ |
| 6주차 | 5-2 ~ 5-5 | 5-6 | 🍽️ |
| 7주차 | 필수 강의 없음 | 6-2, 6-3, 6-4, 6-5 | 🍽️ |

---

<br>

<!-- 여기까진 그대로 둬 주세요-->

---

# 1️⃣ 개념 정리

아래 키워드 중 중요하다고 생각한 개념을 2개 이상 골라 짧게 정리해주세요. 3개보다 더 많이 정리하고 싶다면 자유롭게 항목을 추가해도 좋습니다.

이번 주 키워드:
- DATE
- DATETIME
- TIMESTAMP
- EXTRACT
- DATETIME_TRUNC
- FORMAT_DATETIME
- CASE WHEN
- IF

## 01.

```
개념 이름: DATE
개념 설명:
-날짜만 표시하는 데이터
-시간이나 분,초가 없이 일자까지만 나타냄
-ex) 2023-12-31
예시 쿼리:2023-12-31
```

## 02.

```
개념 이름:DATETIME
개념 설명:
-DATE와 TIME까지 표시하는 데이터
-DATE+TIME 형태임
-Time Zone 정보 없음
-ex) 2023-12-31 14:00:00
예시 쿼리:2023-12-31 14:00:00
```

## (선택) 03.

```
개념 이름:TIMESTAMP
개념 설명:
- UTC부터 경과한 시간을 나타내는 값
- TIME ZONE정보를 가지고 있음
-ex) 2023-12-31 14:00:00 UTC -> UTC로부터 이만큼이 지난 데이터다 라는 뜻
- TIMESTAMP_MILLIS라는 함수를 쓰면 MILLISECOND를 TIMESTAMP로 바꿀 수 있음
- TIMESTAMP로 시간이 저장된 경우가 많음
- TIMESTAMP와 DATETIME 변환을 해야하는 경우가 많음 DATETIME(TIMESTAMP정보, ZONE정보) 이렇게하면 시간데이터끼리 변환할 수 있음
- TIMESTAMP와 DATETIME 구분 방법
  TIMESTAMP->UTC라고 나옴/한국시간-9시간/오전9시가 UTC기준 0시이다
  DATETIME-> T라고 나옴/한국시간과 동일
  CURRENT_TIMESTAMP->현재의 TIMESTAMP 알려주는 함수
헷갈린 점:
```

---

# 2️⃣ 수행 인증란

<img width="1067" height="654" alt="image" src="https://github.com/user-attachments/assets/f1723c27-ce7e-4689-a246-1494c3a4a469" />

---

# 3️⃣ 확인 문제

프로그래머스는 로그인이 필요하므로, 로그인 후 문제 풀이를 진행해주세요.

## 🧩 문제 1

문제 링크: [자동차 대여 기록에서 장기/단기 대여 구분하기](https://school.programmers.co.kr/learn/courses/30/lessons/151138)

풀이 과정:

```
- 장기/단기 대여를 나눈 기준:대여기간이 30일 이상이면 장기대여, 30일 미만이면 단기대여
- 사용한 날짜 계산 방식: DATEDIFF(END_DATE,START_DATE)+1로 시작일을 포함한 대여 일수 계산
- CASE WHEN으로 만든 컬럼:장기대여 또는 단기대여를 표시하는 컬럼
```

<img width="446" height="262" alt="image" src="https://github.com/user-attachments/assets/f2af26eb-6de9-45f4-9b6c-9683409ebe8a" />

## 🧩 문제 2

문제 링크: [한 해에 잡은 물고기 수 구하기](https://school.programmers.co.kr/learn/courses/30/lessons/298516)

풀이 과정:

```
- 문제에서 요구한 연도:2021년
- 사용한 날짜 조건:YEAR(TIME)=2021
- 집계한 대상:2021년에 잡은 모든 물고기의 수
```

<img width="308" height="237" alt="image" src="https://github.com/user-attachments/assets/a7d5cd2b-4b04-4d6d-ba84-e1b461385f7d" />


## 🧩 문제 3

문제 링크: [조건에 부합하는 중고거래 상태 조회하기](https://school.programmers.co.kr/learn/courses/30/lessons/164672)

풀이 과정:

```
- 날짜 조건: CREATED_DATE='2022-10-05'
- CASE WHEN으로 바꾼 값:SALE->판매중 RESERVED->예약중 DONE->거래완
- ELSE에 해당하는 경우:ELSE를 생략했으므로 위 조건에 해당하지 않으면 NULL로 표시
- 정렬 기준:게시글 ID기준 내림차순
```

<img width="331" height="266" alt="image" src="https://github.com/user-attachments/assets/6078f59e-82ef-4924-8f89-f91d1542162a" />

## 🧩 문제 4

문제 링크: [자동차 평균 대여 기간 구하기](https://school.programmers.co.kr/learn/courses/30/lessons/157342)

풀이 과정:

```
- GROUP BY 기준: 자동차 ID 별로 묶음
- 평균을 계산한 방식:DATEDIFF(END_DATE,START_DATE)+1로 대여 일수를 구한 뒤 평균을 계산하고 소수점 첫째 자리까지 반올림
- HAVING에 사용한 조건:평균 대여 기간이 7일 이상인 자동차만 선택
- 처음 헷갈렸던 점:자동차별로 계산한 평균에 조건을 걸때는 WHERE가 아니라 HAVING을 사용한다는것
```

<img width="430" height="286" alt="image" src="https://github.com/user-attachments/assets/a6547495-b182-4732-a5ee-3a1beb7f8c55" />

---

# 4️⃣ 이번 주 회고

```
1. 날짜 함수 중 가장 헷갈린 함수:DATEDIFF함수는 종료일과 시작일의 차이를 계산하며 시작일까지 포함하려면 +1을 해야한다는점이 헷갈렸다
2. CASE WHEN을 사용할 때 기억해야 할 문법:CASE WHEN 조건 THEN 결과 ELSE 나머지 결과 END 형태로 작성한다
3. 날짜/시간 데이터나 조건문을 활용해보고 싶은 분석 상황: 교통사고를 발생 시간에 따라 출근 퇴근 시간대로 나누고 사고 건수를 비교해보고 싶다
```

수고하셨습니다!



