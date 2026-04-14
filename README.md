# TripPocket

«AI 기반 한국 여행 코스/일정 추천 플랫폼»

TripPocket은 한국 여행 정보를 탐색하고, 조건에 맞는 여행 코스와 일정을 더 쉽게 찾을 수 있도록 설계한 서비스입니다.
여행지 탐색, 코스 추천, 일정 생성, 계산형 도구를 하나의 흐름 안에서 연결하는 것을 목표로 개발했습니다.

- 한국어: https://trip-pocket.pages.dev/ko/
- 영어: https://trip-pocket.pages.dev/en/

---

## 프로젝트 소개

기존 여행 서비스는 정보는 많지만, 사용자가 실제로 어디를 가고 어떤 순서로 움직일지 결정하는 데 시간이 많이 듭니다.

TripPocket은 이 문제를 해결하기 위해 다음에 집중했습니다.

- 여행지/관광지 정보를 구조화해 탐색 가능하게 만들기
- 조건 기반 추천과 일정 생성 흐름 만들기
- 여행 콘텐츠와 도구형 기능을 하나의 서비스로 연결하기
- AI를 활용해 일정 생성 경험을 더 자연스럽게 만들기

---

## 핵심 기능

- 지역별 여행지 탐색
- 여행 코스 조회 및 상세 보기
- 조건 기반 일정/코스 추천
- 여행 계산기(예산, 환율, 공휴일 등)
- 다국어 지원(한국어 / 영어)
- AI 기반 일정 생성 보조 기능

---

## 내가 집중한 포인트

### 1. 여행 정보를 “콘텐츠”가 아니라 “사용 가능한 구조”로 설계

단순 리스트형 정보 제공이 아니라, 사용자가 실제 여행 결정을 내릴 수 있도록
지역·코스·도구·가이드를 연결된 구조로 설계했습니다.

### 2. AI 기능을 서비스 로직 안에 안정적으로 연결

AI를 단순 문장 생성 도구로 쓰는 것이 아니라,
일정 생성과 추천 경험을 보조하는 방향으로 설계했습니다.

### 3. 확장 가능한 백엔드 구조

여행 데이터, 코스, 추천, 외부 연동 기능이 분리되도록 구성해
추후 기능 확장과 유지보수를 쉽게 만들었습니다.

### 4. 사용자 경험 중심의 프론트엔드 구성

홈, 지역, 코스, 계산기 등 주요 흐름을 명확히 나누고,
다국어 환경에서도 일관된 탐색 경험을 제공하도록 구성했습니다.

---

## 기술 스택

| 구분 | 기술 |
| --- | --- |
| Backend | Kotlin, Spring Boot |
| Frontend | Next.js 14, React, TypeScript |
| Database | PostgreSQL |
| Cache | Redis, Caffeine |
| Styling | Tailwind CSS |
| Testing | JUnit5, Playwright |
| Deployment | Cloudflare Pages, Oracle Cloud VM |

---

## 아키텍처

```text
Frontend (Next.js)
   ↓
Backend API (Spring Boot)
   ├─ 여행지/코스/추천 도메인
   ├─ 일정 생성 로직
   ├─ 외부 데이터 연동
   └─ 데이터 저장 및 캐시
```

---

## 프로젝트 구조

```text
trip-pocket/
├── src/main/kotlin/com/itkong/trippocket/
│   ├── api/
│   ├── domain/
│   ├── external/
│   └── common/
├── frontend/
│   ├── app/
│   ├── components/
│   └── lib/
├── docs/
└── build.gradle.kts
```

---

## 성과 관점에서 강조할 수 있는 부분

- 여행 추천/탐색 서비스의 전체 구조를 직접 설계
- 백엔드와 프론트엔드를 함께 연결하며 기능 흐름 구현
- AI 기능을 실제 사용자 경험에 맞게 서비스 안에 통합
- 다국어 및 확장성을 고려한 구조 설계

---

## 로컬 실행

### Backend

```bash
cp .env.example .env.local
./scripts/run-local.sh
```

### Frontend

```bash
cd frontend
npm install
npm run dev
```

---

## 테스트

```bash
./gradlew test
```

---

## License

Private
