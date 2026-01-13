# 🥗 Diet Agent  
AI 기반 개인 맞춤형 다이어트 관리 플랫폼

>보안상의 이유로 .env 파일을 제외하여 올렸습니다. 

---

## 📜 목차
- [프로젝트 개요](#-프로젝트-개요)
- [팀원 소개](#-팀원-소개)
- [핵심 목표](#-핵심-목표)
- [기술 스택](#-기술-스택)
- [프로젝트 구조](#-프로젝트-구조)
- [주요 기능](#-주요-기능)
- [서비스 흐름](#-서비스-흐름)
- [주요 유틸 설명](#-주요-유틸-설명)
- [트러블 슈팅 경험](#-트러블-슈팅-경험)
- [배포 방법](#-배포-방법-docker)
- [프로젝트 성과](#-프로젝트-성과)

---

## 📌 프로젝트 개요
>[목차로 돌아가기](#-목차)

**Diet Agent**는  
사용자의 신체 정보, 목표 체중, 목표 기간, 일상 기록 등을 기반으로  
👉 **식단 · 운동 · 일정 · 진행률 · AI 챗봇 상담을 통합 제공하는 다이어트 관리 웹 서비스**입니다.

단순한 추천을 넘어 실제 체중 변화, 목표 달성률을 **DB에 기록하고 시각적으로 관리**하는 것이 핵심 목표입니다.



## 👤 팀원 소개
>[목차로 돌아가기](#-목차)
<div align="center">

<table>
  <tr>
    <!-- PM / Developer -->
    <td align="center" width="230" style="vertical-align: top;">
      <b>김요원 (PM)</b>
      <div style="width:60%;margin:6px auto;border-bottom:1px solid #aaa;"></div>
      <sub><b>PM / Developer</b></sub><br>
      <sub>- 프로젝트 와이어프레임 설계 및 화면 흐름 기획,
        <br>- DB 테이블·컬럼 구현
        <br>- JWT 기반 인증 기능 구현 (React–Flask)
        <br>- 사용자 정보 관리 및 식단 기록 및 저장 기능 구현
        <br>- AI 챗봇 응답 로직 수정 및 기능 구현
        <br>- 대시보드 주간 추세 시각화
      </sub><br><br>
      <a href="https://github.com/kywww">
        <img src="https://img.shields.io/badge/GitHub-181717?style=flat&logo=github&logoColor=white">
      </a>
    </td>
 <!-- Developer -->
    <td align="center" width="230" style="vertical-align: top;">
      <b>정두균</b>
      <div style="width:60%;margin:6px auto;border-bottom:1px solid #aaa;"></div>
      <sub><b>Developer</b></sub><br>
      <sub>프로젝트 전체 일정·업무 관리
        <br>- DB 테이블·컬럼 구현
        <br>- JWT 기반 인증 기능 구현 (React–Flask)
        <br>- 사용자 정보 관리 및 식단 기록 및 저장 기능 구현
        <br>- AI 챗봇 응답 로직 수정 및 기능 구현
        <br>- 대시보드 주간 추세 시각화
      </sub><br><br>
      <a href="https://github.com/dooposip">
        <img src="https://img.shields.io/badge/GitHub-181717?style=flat&logo=github&logoColor=white">
      </a>
    </td>
    <!-- Developer -->
    <td align="center" width="230" style="vertical-align: top;">
      <b>이혜지</b>
      <div style="width:60%;margin:6px auto;border-bottom:1px solid #aaa;"></div>
      <sub><b>Developer</b></sub><br>
      <sub>피처 엔지니어링(preprocess) 고안,<br>
      모델 성능 분석 및 리더보드 해석,<br>
      환경과 판매품 상관 분석 그래프 구현</sub><br><br>
      <a href="https://github.com/lhj8-8">
        <img src="https://img.shields.io/badge/GitHub-181717?style=flat&logo=github&logoColor=white">
      </a>
    </td>
    <!-- Developer -->
    <td align="center" width="230" style="vertical-align: top;">
      <b>박종훈</b>
      <div style="width:60%;margin:6px auto;border-bottom:1px solid #aaa;"></div>
      <sub><b>Developer</b></sub><br>
      <sub>메인 대시보드 개발,<br>
      예측·발주 로직 및 세그먼트 구현,<br>
      ngrok 연동 및 UI/UX 개선</sub><br><br>
      <a href="https://github.com/dailyhune">
        <img src="https://img.shields.io/badge/GitHub-181717?style=flat&logo=github&logoColor=white">
      </a>
    </td>
  </tr>
</table>

</div>


---

---

## 🎯 핵심 목표
>[목차로 돌아가기](#-목차)

- 실제 서비스 수준의 **React + Flask 풀스택 구현**
- **JWT 인증 구조 직접 설계**
- DB 중심의 사용자 상태 관리
- 챗봇, 일정, 진행률을 하나의 흐름으로 연결
- Docker 기반 배포 환경 구축

---

## 🛠 기술 스택
>[목차로 돌아가기](#-목차)

### Frontend
- **React (Vite)**
- React Router DOM
- Axios
- CSS (컴포넌트 단위 스타일링)

### Backend
- **Python Flask**
- Flask Blueprint 구조
- PyJWT (JWT 인증)

### Database
- **SQLite**
- `sqlite3.Row` 기반 딕셔너리 조회

### Authentication
- **JWT Access Token 방식**
- LocalStorage 기반 로그인 유지

### DevOps / Deployment
- **Docker**
- Dockerfile 기반 컨테이너 배포

---

## 📂 프로젝트 구조
>[목차로 돌아가기](#-목차)

### Frontend
```
src/
├─ api/
│ └─ Axios.js
├─ components/
│ ├─ Header.jsx
│ ├─ Sidebar.jsx
│ ├─ Chatbot.jsx
│ ├─ FloatingActionBar.jsx
│ └─ MemoPanel.jsx
├─ pages/
│ ├─ IntroPage.jsx
│ ├─ LoginPage.jsx
│ ├─ SignupPage.jsx
│ ├─ MainPage.jsx
│ ├─ HomePage.jsx
│ ├─ DietPage.jsx
│ ├─ WorkoutPage.jsx
│ ├─ SchedulePage.jsx
│ ├─ MyInfoPage.jsx
│ └─ CommunityPage.jsx
├─ App.jsx
└─ main.jsx
```

---

### Backend

```
backend/
├─ app.py
├─ config.py
├─ db/
│ └─ database.py
├─ models/
│ ├─ user_model.py
│ ├─ chatbot_model.py
│ ├─ weight_model.py
│ └─ schedule_model.py
├─ routes/
│ ├─ user_routes.py
│ ├─ chatbot_routes.py
│ ├─ schedule_routes.py
│ └─ progress_routes.py
├─ services/
│ ├─ chatbot_service.py
│ ├─ progress_service.py
│ ├─ recommendation_service.py
│ └─ schedule_service.py
└─ utils/
├─ intent_detector.py
└─ parse_utils.py
```

---

## ⭐ 주요 기능
>[목차로 돌아가기](#-목차)

### ✅ 회원가입 / 로그인
- 이메일 & 비밀번호 기반 인증
- JWT Access Token 발급

---

### 🔐 JWT 인증 구조
- 로그인 시 토큰 발급
- LocalStorage 저장
- `/api/user/me`로 로그인 상태 복구
- 보호된 라우트(`RequireLogin`) 구현

---

### 📊 체중 기록 기반 실제 진행률 계산
- 현재 체중, 목표 체중, 목표 기간 DB 저장
- 날짜별 체중 기록 관리
- **실제 감량률 기반 진행률 계산**
- 홈 화면에 진행률 시각화

> 단순 고정 퍼센트가 아닌 **실제 데이터 기반 계산**

---

### 🤖 AI 챗봇 (DB Context 기반)
- 사용자 질문 → 의도 분석 (식단 / 운동 / 진행률 / 일반 대화)
- 챗봇 대화 로그 DB 저장
- 사용자의
  - 목표
  - 선호 음식
  - 알러지
  - 최근 진행 상황  
  을 반영한 **개인화된 답변**

---

### 🥗 식단 & 🏃 운동 추천
- 일정에 맞춰 식단/운동 추천
- 사용자 선호/비선호/알러지 반영
- 추천 결과 DB 저장

---

### 📅 캘린더 일정 연동
- 날짜별 식단 / 운동 스케줄 관리
- 캘린더 UI와 연동된 API
- 일정 수행 여부 기록

---

### 📝 메모 & 기록 관리
- 날짜별 개인 메모 작성
- 언제든 열 수 있는 플로팅 메모 패널
- DB 저장 기반 기록 유지

---

### 🌐 Docker 기반 배포
- Dockerfile 작성
- Flask 서버 컨테이너화
- 환경 독립적 실행 가능

---

## 🔄 서비스 흐름
>[목차로 돌아가기](#-목차)

1. 회원가입 / 로그인
2. JWT 발급 및 인증 유지
3. 사용자 목표 정보 입력
4. 체중 기록 시작
5. 진행률 자동 계산
6. 챗봇 상담 & 일정 관리
7. 모든 기록 DB 저장

---

## 🧩 주요 유틸 설명
>[목차로 돌아가기](#-목차)

### `parse_utils.py`
- 사용자 입력값 방어 처리
- 서버 에러(500) 예방
- 안전한 숫자 / 문자열 변환

---

### `intent_detector.py`
- 챗봇 질문 의도 분류
- 식단 / 운동 / 진행률 / 일반 대화 분기

---

## 🛠 트러블 슈팅 경험
>[목차로 돌아가기](#-목차)

### ❌ 로그인 후 화면 이동 문제
- 원인: 중복 navigate 처리
- 해결: 인증 흐름 App.jsx로 일원화

---

### ❌ 챗봇이 항상 식단만 응답
- 원인: 의도 분기 부족
- 해결: intent detector 개선

---

### ❌ 500 Internal Server Error
- 원인: 입력값 처리 미흡
- 해결: parse_utils 도입

---

## 🚀 배포 방법 (Docker)
>[목차로 돌아가기](#-목차)

```bash
docker build -t diet-agent .
docker run -p 5000:5000 diet-agent
```

---

## 📌 프로젝트 성과
>[목차로 돌아가기](#-목차)

실제 서비스 수준의 기능 구현

인증 · 상태 관리 · DB 설계 경험

프론트–백엔드 연동 이해

Docker 기반 배포 경험
