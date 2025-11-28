
---

# 📚 DB_API_Spring_prac – 학습 암기/퀴즈 웹앱 개발 프로젝트

학생들이 암기 과목을 보다 능률적으로 학습하도록
**노트 → 키워드 선택 → 암기(타자) → 퀴즈 → 채점·통계**까지
학습 전 과정을 시스템화한 웹 기반 학습 서비스입니다.

---

# 👨‍💻 나의 역할 (My Contribution)

## ✔ 1. **키워드 기반 암기·퀴즈 시스템 핵심 설계**

> 이 프로젝트의 ‘지능형 학습 기능’을 담당한 핵심 개발 역할

* 노트에서 선택한 키워드를 metadata로 저장하는 구조 설계
* 키워드를 자동 “빈칸 문제”로 변환하는 알고리즘 설계
* 대소문자/띄어쓰기/기호를 허용하는 **정답 판정 로직** 구현
* 틀린 키워드를 자동 추적하는 **Weak Keyword Tracking 설계**
  → 오답노트, 재도전 기능 구현 가능하도록 구조화
* 단순한 텍스트 비교가 아니라 ‘의미 단위 암기’가 가능하도록 설계

---

## ✔ 2. **암기(타자 기반) 기능 로직 설계**

> “보고 따라 치기 → 오타 감지 → 실시간 피드백 → 기록 저장” 기능의 전체 로직 구현

* 문장 가리기 기능(Blind Mode) 설계
* 실시간 오타 비교 알고리즘 설계
* 정확도·WPM(타수) 계산 로직 설계
* 암기 중 진행 상태를 저장하는
  **MemorizationSession 테이블** 구조 설계

  * 시작 시각
  * 마지막 타이핑 라인
  * Session 완료 여부 저장

---

## ✔ 3. **DB 전체 설계 책임 (ERD 포함)**

프로젝트 전 기능이 문제없이 돌아가도록
**정규화 + 확장성 + 기능 흐름**을 모두 고려해 DB를 직접 설계했습니다.

### 🔍 설계한 핵심 테이블

* **User** – 회원 관리, 인증
* **Note / Category / Keyword** – 노트/키워드 구조
* **Quiz / QuizTry / QuizResult** – 문제·채점·정답률 구조
* **FrequentlyWrong** – 오답 키워드 저장
* **MemorizationSession** – 암기 기록(히스토리)
* **WrongKeywordHistory** – 틀린 문제 이력

### 🔧 설계 기준

* 키워드 기반 문제 생성이 가능하도록 정규화
* 재도전 시 성장을 비교할 수 있는 **History 기반 구조 적용**
* 자동 저장 기능 지원을 위한 updated_at 전략
* 대용량 텍스트·이미지 활용 대비한 구조 설계

---

## 📂 ✔ **ERD & DB 설계 이미지 삽입**

<p align="center">
  <img width="370" src="https://github.com/user-attachments/assets/6ebc1815-e8d3-4581-ac6d-f1c585cfef02" />
  <img width="374" src="https://github.com/user-attachments/assets/20bf3551-185d-4da4-a1b1-e31f9ac838d9" />
  <img width="366" src="https://github.com/user-attachments/assets/fece7a72-15fd-489c-b0e4-8cd3cd0ceced" />
  <img width="380" src="https://github.com/user-attachments/assets/b92648f8-bdcc-46b2-a975-2f1dc7066039" />
  <img width="385" src="https://github.com/user-attachments/assets/e810d442-3390-44f7-b229-8678cf6e6d4a" />
  <img width="356" src="https://github.com/user-attachments/assets/db623506-79eb-4323-8803-c716136eed1f" />
  <img width="364" src="https://github.com/user-attachments/assets/2d9923fb-667d-4185-b27b-c6d02ce14d00" />
  <img width="362" src="https://github.com/user-attachments/assets/522d81f6-04a6-4c38-93ae-a369f305d98d" />
  <img width="354" src="https://github.com/user-attachments/assets/de874a42-3b03-4bf9-880c-c864c90794a4" />
  <img width="364" src="https://github.com/user-attachments/assets/a0a993a4-34f1-406e-88cb-8cb6a896a658" />
</p>

> 위 이미지들은 ERD, 테이블 설계, 관계 구조, API 응답 포맷 설계 등
> **백엔드 기술 설계 전반을 수행했음을 시각적으로 보여주는 핵심 근거 자료**입니다.

---

## ✔ 4. **API 구조 및 백엔드 흐름 설계**

### 참여한 API

* 노트 CRUD
* 키워드 등록/삭제
* 문제 자동 생성 API
* 채점 API
* 재도전 API(전체/오답만)
* 정답률·오답 TOP10 통계 API
* 암기 세션(시작/진행/완료) API

### 설계 원칙

* 기능 중심 RESTful 구조
* 프론트 개발자가 사용하기 쉬운 직관적 엔드포인트
* 동적 문제 생성(고정형 문제 NO)
* 자동 저장(PATCH) + 이력 저장 구조 병행
* 학습 데이터를 최대한 보존하는 방향으로 구조화

---

# 📘 배운 점 (Key Learnings)

## ✔ 1. 기능 아이디어를 데이터 구조로 설계하는 능력 강화

“기능이 돌아가게 하려면 DB가 먼저 설계돼야 한다”는 원리를
실전 수준으로 체득한 프로젝트.

---

## ✔ 2. 규칙 기반으로도 지능형 학습 앱을 만들 수 있음을 경험

키워드 기반 빈칸 생성·오답 추천 등은
AI 없이도 **DB + 알고리즘 설계**로 충분히 구현 가능하다는 점을 배움.

---

## ✔ 3. Spring REST API의 실제 개발 흐름 이해

POST/PATCH/GET의 차이,
자동 저장 구조,
리소스 기반 URL,
세션처럼 상태를 저장하는 방식 등을 실전으로 이해.

---

## ✔ 4. 기록·통계 시스템의 복잡성과 설계 중요성 학습

정답률·성장 기록은 단순 계산이 아니라
**히스토리 구조, 통계 계산, 데이터 누적**이 핵심임을 깨달음.

---




