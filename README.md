# TripPocket

**한국 여행 추천 & 도구 플랫폼**

검색 유입이 되고, 실제로 유용하며, 수익화가 가능한 한국 여행/생활 추천 플랫폼.

- 한국어: https://trip-pocket.itkong.uk/ko/
- 영어: https://trip-pocket.itkong.uk/en/

---

## 프로젝트 개요

TripPocket은 한국 여행에 필요한 정보를 **자동 수집하고 판단을 도와주는 도구형 서비스**입니다.

날씨·공휴일·환율·관광지 데이터를 수집하여 추천, 계산, 비교 기능을 제공하며,
가이드·계산기·지역 정보를 촘촘한 내부링크로 연결해 검색 유입과 체류시간을 높입니다.

---

## 현재 사이트 문제 요약

| 문제 | 영향 |
|------|------|
| 홈이 소개형 성격이 강하고 도구형 결과가 약함 | 첫 방문자 이탈, 검색 유입 약화 |
| 가이드 허브가 카드 나열 중심이라 얇음 | 구글이 "얇은 콘텐츠"로 판단할 수 있음 |
| 계산기 허브가 링크 소개 수준 | 허브 자체의 검색 유입 가치 없음 |
| 여행지 허브의 설명 밀도 부족 | 지역 리스트 페이지로만 기능 |
| 일부 여행 정보 최신성 검수 미비 | K-ETA, 비자, 환전 정보 오래되면 신뢰도 하락 |
| 영어 페이지가 단순 번역 수준 | 외국인 검색 유입 불가 |
| 페이지 간 내부링크 부족 | 크롤링 깊이 얕고 체류시간 짧음 |

---

## 개선 목표

1. 각 페이지가 검색엔진에서 **고유한 페이지**로 인식되게 만든다
2. 허브 페이지를 얇은 링크 모음이 아니라 **실제 정보 페이지**로 바꾼다
3. "정보 모음"이 아니라 **"판단을 도와주는 여행 도구"**로 느껴지게 만든다
4. 한국어/영어 모두 **검색 유입**이 가능하도록 구조를 강화한다
5. 최신성 민감 정보에 **검수 구조**를 만들어 오래된 정보가 남지 않게 한다
6. 콘텐츠 품질을 먼저 높여 **AdSense를 붙여도 가치가 떨어지지 않게** 한다
7. 가이드·계산기·지역 페이지가 **내부링크로 촘촘히 연결**되게 만든다

---

## 페이지 유형

```
홈 (/ko/, /en/)
├── 가이드 허브 (/ko/guides/)
│   └── 가이드 상세 (/ko/guides/first-time-korea/)  ← 6개
├── 계산기 허브 (/ko/calculators/)
│   └── 계산기 상세 (/ko/calculators/travel-budget/)  ← 3개
├── 여행지 허브 (/ko/regions/)
│   └── 지역 상세 (/ko/regions/seoul/)  ← 8개
├── 오늘 추천 (/ko/today/)
├── 주말 추천 (/ko/weekend/)
├── 코스 빌더 (/ko/course/)
└── 교통 검색 (/ko/transport/)
```

---

## 기술 스택

| 구분 | 기술 | 배포 |
|------|------|------|
| Backend | Kotlin + Spring Boot 3.4 (JDK 21) | Oracle Cloud VM (Docker) |
| Frontend | Next.js 14 (App Router, SSG) | Cloudflare Pages |
| Database | PostgreSQL 17 | Docker |
| Cache | Spring Cache + Redis | Docker |
| CI/CD | GitHub Actions | 자동 배포 (backend: push to main) |

---

## 외부 API 연동

| API | 용도 | 갱신 주기 |
|-----|------|-----------|
| Open-Meteo | 14일 날씨 예보 + 시간별 날씨 | 매일 06:00 |
| TourAPI (한국관광공사) | 관광지 정보 + 상세 | 매주 월 03:00 |
| Nager.Date | 공휴일 | 매일 00:10 |
| Currency API | 환율 (USD, JPY, EUR 등 8종) | 매일 07:00 |
| 한국 교통 포털 | KTX/고속버스/시외버스 시간표 | 실시간 |

---

## SEO / 콘텐츠 / 수익화 개선 방향

### SEO
- 허브 페이지 본문 밀도 강화 (가이드·계산기·여행지)
- 페이지별 고유 title, meta description, h1
- JSON-LD 구조화 데이터 확장 (FAQ, HowTo, TouristDestination)
- hreflang 한국어/영어 교차 연결
- 내부링크 밀도 3배 이상 강화

### 콘텐츠
- 가이드: 최소 1,500자 이상 고유 본문 + 목차 + FAQ
- 계산기: 결과 해석 + 평균 예시 + 관련 가이드 연결
- 지역: 왜 가야 하는지 + 예산 감각 + 교통 팁 + 외국인 팁
- 최신성 민감 정보: "최종 확인일" 표기 + 검수 프로세스

### 수익화
1. 1단계: 콘텐츠 품질 강화 → AdSense 승인
2. 2단계: 숙소/보험/교통/eSIM 제휴 링크 자연 연결
3. 3단계: 프리미엄 일정표, PDF 체크리스트

---

## 우선순위

| 순서 | 작업 | 기간 |
|------|------|------|
| Phase 1 | 문서 작성 + 정보구조 재설계 + 메타 전략 | 즉시 |
| Phase 2 | 홈·허브 페이지 콘텐츠 강화 + 내부링크 | 1주 |
| Phase 3 | 대표 가이드 5개 + 지역 4개 + 계산기 3개 본문 강화 | 2주 |
| Phase 4 | 구조화 데이터 + FAQ + 영어 고도화 + 광고 최적화 | 1개월 |

---

## 프로젝트 구조

```text
trip-pocket/
├── src/main/kotlin/com/itkong/trippocket/
│   ├── api/              # REST 컨트롤러
│   ├── domain/           # 도메인 (Region, Weather, Holiday, Exchange, Attraction)
│   ├── external/         # 외부 API 클라이언트
│   ├── batch/            # 스케줄러 / 배치
│   ├── board/            # 보드 추천 + 스코어링
│   ├── recommendation/   # 추천 엔진
│   ├── seo/              # SEO 서비스
│   └── common/           # 공통 설정, 보안, i18n
├── frontend/             # Next.js 프론트엔드
│   ├── app/              # App Router 페이지
│   ├── components/       # UI 컴포넌트
│   └── lib/              # i18n, API, analytics
├── docs/                 # 기획·전략 문서
└── build.gradle.kts
```

---

## 문서 모음

| 문서 | 내용 |
|------|------|
| `docs/product.md` | 제품 포지션, 핵심 사용자, 차별점 |
| `docs/seo-improvement.md` | SEO 문제 진단 및 개선 전략 |
| `docs/content-plan.md` | 콘텐츠 강화 계획 + 템플릿 |
| `docs/information-architecture.md` | URL·메뉴·내부링크 구조 |
| `docs/tasks.md` | 우선순위별 작업 목록 |
| `docs/API_SPECS.md` | API 사양 |
| `docs/PRODUCT_GROWTH_PLAN.md` | 고도화 기획안 |

---

## 로컬 실행

### Backend

```bash
cp .env.example .env.local
./scripts/run-local.sh
```

서버: `http://localhost:9080`

### Frontend

```bash
cd frontend
npm install
npm run dev
```

프론트: `http://localhost:9002`

---

## 테스트

```bash
./gradlew test
```

---

## License

Private
