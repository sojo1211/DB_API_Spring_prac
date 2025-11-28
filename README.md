# DB_API_Spring_prac
### 11/16 추가 내용 표시

### 로그인 페이지

- 회원가입 페이지
    - 이메일 인증
    - 회원 등록
- 비밀번호 재설정 페이지

### 메인 페이지

- 최근 학습 페이지 나오게
- 어떤걸 할지 선택할수 있는 페이지
    - 작성 페이지
    - 암기 페이지
    - 퀴즈 페이지
    - 결과 페이지
- 마이 페이지 따로 없이 메인페이지에 정보들 보이게
- 리스트(안녕하세요)
    - 로그아웃
    - 비밀번호 재설정
    - 회원 탈퇴

### 노트 작성페이지

- 과목, 단원 설정
    - 카테고리 설정 처럼(과목이나 공부말고도 여러가지)
- 문단이나 글씨 서식 지원
- 자동 저장 기능
    - 몇초에 한번씩 진행할지
- 중요한 키워드를 선택해 표시하면, 자동으로 퀴즈 모드 시 **빈칸 문제**로 변환.
- 이미지, 동영상 하이퍼링크
- 파일불러오기
    - 텍스트, 이미지 전부다 불러오기 -이미지에서 텍스트 추출이 문제가 됨(pdf 안에 이미지가 있을 수 있고, 상하관계, 계층구조 등 시각적 정보는 모두 사라지고, 텍스트만 추출됨.)

### 암기 페이지

- 암기 모드
    - 카테고리나 PDF 불러와서 똑같이 따라치는 기능  -pdf 불러오는기능 없음(노트작성 페이지에만 있음)
    - 문장을 클릭하면 가릴수있는 기능
    - 오타 표시 (틀린부분 눈에 보이게 표시)
    - 자동 저장

### 퀴즈 페이지

- 퀴즈 모드
    - 주요 키워드 빈칸으로
    - 마침을 누르면 빈칸 채점
        - 채점기준
            - 대소문자, 띄어쓰기, 마침표(기호) 조금 달라도 허용
    - 재도전
        - 틀린것만 재도전
        - 전체 재도전
        - 재시험 결과 새롭게 저장(뱃지 같은 걸로 재시험 표시)
    - 단원별 틀린 문제 기록
        - 사용자가 틀린문제 저장, 제거
    - 채점 하기
        - 정답 박스 표시
            - 틀린 문제
            - 정답

### 결과 페이지

- 단원별(카테고리) 정답률
    - 퍼센트로 나오게
- 다시 풀기
    - 누르면 퀴즈 페이지 이동
<img width="616" height="740" alt="image" src="https://github.com/user-attachments/assets/5054bb4e-b4f4-4ce7-8077-6fc0d4f32acc" />
내역할 -키워드와 암기

DB 설계
<img width="370" height="439" alt="image" src="https://github.com/user-attachments/assets/6ebc1815-e8d3-4581-ac6d-f1c585cfef02" />
<img width="374" height="363" alt="image" src="https://github.com/user-attachments/assets/20bf3551-185d-4da4-a1b1-e31f9ac838d9" />
<img width="366" height="529" alt="image" src="https://github.com/user-attachments/assets/fece7a72-15fd-489c-b0e4-8cd3cd0ceced" />
<img width="380" height="749" alt="image" src="https://github.com/user-attachments/assets/b92648f8-bdcc-46b2-a975-2f1dc7066039" />
<img width="385" height="485" alt="image" src="https://github.com/user-attachments/assets/e810d442-3390-44f7-b229-8678cf6e6d4a" />
<img width="356" height="389" alt="image" src="https://github.com/user-attachments/assets/db623506-79eb-4323-8803-c716136eed1f" />
<img width="364" height="527" alt="image" src="https://github.com/user-attachments/assets/2d9923fb-667d-4185-b27b-c6d02ce14d00" />


