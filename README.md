# 🥗 Diet Agent  
AI 기반 개인 맞춤형 다이어트 관리 플랫폼
<br>(Docker 배포 주소: ddd)
<br>(문서 파일: ddd.pdf)

>보안상의 이유로 .env 파일을 제외하여 올렸습니다. 

---

## 📜 목차
- [프로젝트 개요](#-프로젝트-개요)
- [팀원 소개](#-팀원-소개)
- [핵심 목표](#-핵심-목표)
- [기술 스택](#-기술-스택)
- [프로젝트 구조](#-프로젝트-구조)
- [서비스 흐름](#-서비스-흐름)
- [주요 기능](#-주요-기능)
- [주요 유틸 설명](#-주요-유틸-설명)
- [트러블 슈팅 경험](#-트러블-슈팅-경험)
- [배포 방법](#-배포-방법-docker)
- [프로젝트 소감](#-프로젝트-소감)

---

## 📌 프로젝트 개요
>[목차로 돌아가기](#-목차)

**Diet Agent**는  
사용자의 신체 정보, 목표 체중, 목표 기간, 일상 기록 등을 기반으로  
👉 **식단 · 운동 · 일정 · 진행률 · AI 챗봇 상담 등을 통합 제공하는 다이어트 관리 웹 서비스**입니다.

단순한 추천을 넘어 실제 데이터들을 **DB에 기록하고 시각적으로 관리**하는 것이 핵심 목표입니다.

---

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
      <sub>- 프로젝트 와이어프레임 설계 및 <br>화면 흐름 기획,
        <br>- DB 테이블·컬럼 공동 구현
        <br>- JWT 기반 인증 기능 구현 (React–Flask)
        <br>- 사용자 정보 관리 및 식단 기록 및 <br>저장 기능 구현
        <br>- AI 챗봇 응답 로직 수정, 기능 공동 구현
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
      <sub>- 프론트엔드 전반 UI/UX 설계 및 구현
        <br>- React 기반 카드형 콘텐츠, 캘린더, 
        <br>모달 중심의 인터페이스 구현 
        <br>- 디자인, 컴포넌트 구조 설계
        <br>- 사용자 친화적 화면플로우 및 UX 구성
        <br>- DB 테이블, 컬럼 공동 구현
        <br>- AI 챗봇 응답 로직 수정 및 <br>기능 공동 구현
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
      <sub>- 백엔드(Flask) 전체 디렉토리
        <br>구조 설계 및 파일 구현
        <br>- DB 관리 파일(schema_extra.sql, <br>database.py) 구현
        <br>- 시드데이터 csv 파일 생성
        <br>- React로 대시보드 초안 구현
        <br>- 오늘의 코칭 프로그래밍
        <br>- 문서작업 및 README 작성
      </sub><br><br>
      <a href="https://github.com/lhj8-8">
        <img src="https://img.shields.io/badge/GitHub-181717?style=flat&logo=github&logoColor=white">
      </a>
    </td>
    <!-- Developer -->
    <td align="center" width="230" style="vertical-align: top;">
      <b>박종훈</b>
      <div style="width:60%;margin:6px auto;border-bottom:1px solid #aaa;"></div>
      <sub><b>Developer</b></sub><br>
      <sub>- 커뮤니티 개발 값 정규화, 
        <br>금지어, 이상 입력 차단
        <br>추천 시간 필터 보조
        <br>- 몇 파일에 뭉쳐있던 것들을 <br>fiexd 기능별 분리
        <br>- DB성능/ 초기데이터 추가
      </sub><br><br>
      <a href="https://github.com/dailyhune">
        <img src="https://img.shields.io/badge/GitHub-181717?style=flat&logo=github&logoColor=white">
      </a>
    </td>
  </tr>
</table>

</div>


---

## 🎯 핵심 목표
>[목차로 돌아가기](#-목차)

- 서비스 수준의 **React + Flask 풀스택 구현**
- **JWT 인증 구조 설계**
- **DB 중심**의 사용자 상태 관리
- 사용자의 정보와 **챗봇**, 일정을 연결한 코칭
- **Docker** 기반 배포 환경 구축

---

## 🛠 기술 스택
>[목차로 돌아가기](#-목차)

### Frontend
- **React (Vite)**
- React Router DOM
- Axios
- CSS 기반 컴포넌트 스타일링

### Backend
- **Python Flask**
- Flask Blueprint 구조
- PyJWT (JWT 인증)

### Database
- **MySQL**
- `sqlite3.Row` 기반 딕셔너리 조회

### Authentication
- **JWT Access Token 방식**
- LocalStorage 기반 로그인 유지
- 보호된 라우트 처리 (RequireLogin)

### DevOps / Deployment
- **Docker**
- Dockerfile 기반 컨테이너화
- 환경 독립적 실행 구조

---

## 📂 프로젝트 구조
>[목차로 돌아가기](#-목차)

>주요 파일을 중심으로 구조를 잡고, 나머지는 요약 설명으로 작성했습니다.

### Frontend
```
frontend/                                   # React + Vite 프론트엔드
├── src/
│   ├── api/
│   │   └── Axios.jsx                       # Axios 공통 설정, Bearer Token 자동 첨부
│   │
│   ├── components/                         # 재사용 UI 컴포넌트
│   │   ├── cards/
│   │   │   ├── GoalStatusCard.jsx          # 목표카드 UI
│   │   │   ├── RecommendationCard.jsx      # 추천카드 UI
│   │   │   ├── TodayDietTable.jsx          # 식단카드 UI
│   │   │   ├── TodayScheduleCard.jsx       # 스케줄카드 UI
│   │   │   └── UserInfoCard.jsx            # 내정보카드 UI
│   │   │
│   │   ├── chat                            # 챗봇 답변 상세 설정
│   │   ├── news                            # 뉴스박스 UI
│   │   ├── BottomRightFab.jsx              # 우측 하단 버튼 UI
│   │   ├── Chatbot.jsx                     # 챗봇 페이지
│   │   ├── FloatingActionBar.jsx           # 우측 플로팅 버튼
│   │   ├── Header.jsx                      # 상단 헤더
│   │   ├── MemoPanel.jsx                   # 메모 UI
│   │   ├── WeeklyTrendCard.jsx             # 주간 체중 변화율 UI
│   │   └── WorkoutRecommend.jsx            # 운동 추천 UI
│   │
│   ├── data                                # 추천 운동 data
│   │  
│   ├── hooks                               # 챗봇, 프로필, 일정 등의 상태 및 로직 분리
│   │
│   ├── pages/                              # 페이지 단위 컴포넌트
│   │   ├── ChatPage.jsx                    # 챗봇 페이지
│   │   ├── CommunityPage.jsx               # 공지사항 / 문의
│   │   ├── DietPage.jsx                    # 다이어트 관리 메인 페이지
│   │   ├── DietTabPage.jsx                 # 다이어트 식단 관리 서브 페이지
│   │   ├── GuestChatPage.jsx               # 비회원 챗봇 체험 페이지
│   │   ├── HomePage.jsx                    # 홈 화면(뉴스카드) 페이지
│   │   ├── IntroPage.jsx                   # 인트로 화면 페이지
│   │   ├── LoginPage.jsx                   # 로그인 페이지
│   │   ├── MainPage.jsx                    # 메인 대시보드
│   │   ├── MyInfoPage.jsx                  # 내 정보 페이지
│   │   ├── Programs.jsx                    # 프로그램 소개 페이지
│   │   ├── SchedulePage.jsx                # 일정 관리 페이지
│   │   ├── SelfCheckPage.jsx               # 자가진단 페이지
│   │   ├── SettingsPage.jsx                # 설정 페이지(다크모드 변경)
│   │   ├── Sidebar.jsx                     # 좌측 사이드바 네비게이션
│   │   ├── SignupPage.jsx                  # 회원가입 페이지
│   │   └── WorkoutPage.jsx                 # 다이어트 운동 관리 서브 페이지
│   │
│   ├── styles                              # 대시보드css
│   │
│   ├── utils                               # 카드뉴스 정보
│   │ 
│   ├── App.jsx                             # 라우팅, 인증 흐름, 로그인 상태 관리
│   └── main.jsx                            # React 진입점
│
└── index.html                              # HTML 엔트리 파일
```

<br>

### Backend

```
backend/                               # Flask 기반 백엔드 서버
├── data/                              # csv data
│
├── db/
│   ├── agent.db                       # SQLite 데이터베이스 파일
│   ├── database.py                    # SQLite 연결 및 RowFactory 설정
│   └── schema_extra.sql               # SQLite 연결 및 RowFactory 설정
│
├── models/                            # DB 접근 로직(Model 계층)
│   ├── activity_model.py              # users 테이블 CRUD
│   ├── calorie_model.py               # users 테이블 CRUD
│   ├── chatbot_model.py               # 챗봇 대화 로그 저장
│   ├── diet_model.py                  # 체중, 목표, 진행률 데이터 처리
│   ├── food_model.py                  # 음식 선호 정보 저장/조회
│   ├── memo_model.py                  # 음식 선호 정보 저장/조회
│   ├── recommendation_model.py        # 음식 선호 정보 저장/조회
│   ├── schedule_model.py              # 일정 데이터 DB 처리
│   ├── settings_model.py              # 일정 데이터 DB 처리
│   ├── summary_model.py               # 일정 데이터 DB 처리
│   ├── user_model.py                  # users 테이블 CRUD
│   └── workout_model.py               # 운동 기록 DB 처리
│
├── routes/                            # API 라우트(Controller 계층)
│   ├── activity_routes.py             # 회원가입, 로그인, JWT 발급
│   ├── ai_engine.py                   # 회원가입, 로그인, JWT 발급
│   ├── ai_tools.py                    # 회원가입, 로그인, JWT 발급
│   ├── auth_routes.py                 # 회원가입, 로그인, JWT 발급
│   ├── calendar_routes.py             # 회원가입, 로그인, JWT 발급
│   ├── calorie_routes.py              # AI 챗봇 대화 API
│   ├── chatbot_routes.py              # AI 챗봇 대화 API
│   ├── community_routes.py            # 공지사항, 문의, 관리자 문의 답변 API
│   ├── diet_routes.py                 # 다이어트 목표, 체중 변화, 진행률 계산 API
│   ├── memo_routes.py                 # 다이어트 목표, 체중 변화, 진행률 계산 API
│   ├── plan_routes.py                 # 다이어트 목표, 체중 변화, 진행률 계산 API
│   ├── preference_routes.py           # 음식 선호(likes/dislikes/allergies) API
│   ├── recommendation_routes.py       # 내 정보 조회(/user/me) 등 사용자 관련 API
│   ├── schedule_routes.py             # 일정 CRUD 및 캘린더 연동 API
│   ├── user_routes.py                 # 내 정보 조회(/user/me) 등 사용자 관련 API
│   ├── weeklytrend_routes.py          # 내 정보 조회(/user/me) 등 사용자 관련 API
│   └── workout_routes.py              # 운동 기록 저장 및 조회 API
│
├── services/                          # 비즈니스 로직 계층
│   ├── calorie_service.py             # 일일 섭취/소모 칼로리 계산
│   ├── planning_service.py            # 일정 기반 자동 추천 로직
│   ├── progress_service.py            # 일정 기반 자동 추천 로직
│   ├── recommendation_service.py      # 일정 기반 자동 추천 로직
│   ├── schedule_service.py            # 일정 기반 자동 추천 로직
│   └── workout_service.py             # 챗봇 프롬프트 및 응답 처리
│
├── utils/                             # 입력값 검증, 타입 변환, 예외 방어 처리              
│      
├── app.py                             # Flask 앱 엔트리 포인트, Blueprint 등록 및 서버 실행
└── config.py                          # HTML 엔트리 파일

```

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

## ⭐ 주요 기능
>[목차로 돌아가기](#-목차)

문서작업이미지5번삽입

### ✅ 회원가입 / 로그인
- 이메일 & 비밀번호 기반 인증
- JWT Access Token 발급

-이미지-

### 🔐 JWT 인증 구조
- 로그인 시 토큰 발급
- LocalStorage 저장
- `/api/user/me`로 로그인 상태 복구
- 보호된 라우트(`RequireLogin`) 구현

-이미지-

### 📊 체중 기록 기반 실제 진행률 계산
- 현재 체중, 목표 체중, 목표 기간 DB 저장
- 날짜별 체중 기록 관리
- **실제 감량률 기반 진행률 계산**
- 홈 화면에 진행률 시각화

> 단순 고정 퍼센트가 아닌 **실제 데이터 기반 계산**

-이미지-

### 🤖 AI 챗봇 (DB Context 기반)
- 사용자 질문 → 의도 분석 (식단 / 운동 / 진행률 / 일반 대화)
- 챗봇 대화 로그 DB 저장
- 사용자의
  - 목표
  - 선호 음식
  - 알러지
  - 최근 진행 상황  
  을 반영한 **개인화된 답변**

-이미지-

### 🥗 식단 & 🏃 운동 추천
- 일정에 맞춰 식단/운동 추천
- 사용자 선호/비선호/알러지 반영
- 추천 결과 DB 저장

-이미지-

### 📅 캘린더 일정 연동
- 날짜별 식단 / 운동 스케줄 관리
- 캘린더 UI와 연동된 API
- 일정 수행 여부 기록

-이미지-

### 📝 메모 & 기록 관리
- 날짜별 개인 메모 작성
- 언제든 열 수 있는 플로팅 메모 패널
- DB 저장 기반 기록 유지

---

## 🧩 주요 유틸 설명
>[목차로 돌아가기](#-목차)

문서작업이미지6번삽입

### `intent_detector.py`
- 챗봇 질문 의도 분류
- 식단 / 운동 / 진행률 / 일반 대화 분기

---

## 🛠 트러블 슈팅 경험
>[목차로 돌아가기](#-목차)

문서작업이미지7번삽입

### ❌ 로그인 후 화면 이동 문제
- 원인: 중복 navigate 처리
- 해결: 인증 흐름 App.jsx로 일원화

-이미지-

### ❌ 챗봇이 항상 식단만 응답
- 원인: 의도 분기 부족
- 해결: intent detector 개선

---

## 🚀 배포 방법 (Docker)
>[목차로 돌아가기](#-목차)

문서작업이미지8번삽입

```bash
docker build -t diet-agent .
docker run -p 5000:5000 diet-agent
```

---

## 📌 프로젝트 소감
>[목차로 돌아가기](#-목차)

이미지 삽입
