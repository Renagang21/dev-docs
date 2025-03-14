1. 핵심 서비스 저장소:
   - Renagang21/o4o-pharmacy-automation     # 약국 자동화 서비스 (Python)
	   - [[pharmacy automation 폴더 구조]]
   - Renagang21/o4o-platform                # O4O 플랫폼 (JavaScript)
	   - [[pharmacy o4o platform 폴더 구조  (크로스 플랫폼 지원)]]

2. 공통 인프라 저장소:
   - Renagang21/o4o-auth                    # 인증 서비스 (SSO)
   - Renagang21/o4o-payment                 # 결제 처리 서비스

3. 유틸리티 및 디자인 저장소:
   - Renagang21/common-utils                # 공통 유틸리티
     - /python                              # Python 유틸리티
     - /javascript                          # JavaScript 유틸리티
     - /shared                              # 언어 중립적 스키마 및 상수
   - Renagang21/common-design               # 디자인 시스템 및 컴포넌트

4. 문서 및 개발 지원:
   - Renagang21/dev-doc                     # 개발 문서

   ---

### pharmacy automation 폴더 구조
Renagang21/o4o-pharmacy-automation/
├── app/                      # FastAPI 애플리케이션
│   ├── api/                  # API 엔드포인트
│   │   ├── routes/           # 라우트 정의
│   │   └── controllers/      # 컨트롤러
│   ├── core/                 # 핵심 설정
│   │   ├── config.py         # 설정
│   │   ├── security.py       # 보안 관련
│   │   └── logging.py        # 로깅 설정
│   ├── db/                   # 데이터베이스 관련
│   │   ├── models/           # 데이터 모델
│   │   ├── session.py        # DB 세션mkdir apimkdir 
│   │   └── crud/             # CRUD 오퍼레이션
│   ├── services/             # 비즈니스 로직
│   │   ├── ocr/              # OCR 서비스
│   │   ├── analysis/         # 데이터 분석
│   │   └── ai/               # AI 서비스
│   ├── schemas/              # Pydantic 스키마
│   ├── utils/                # 유틸리티 함수
│   └── main.py               # 앱 진입점
├── tests/                    # 테스트
│   ├── api/                  # API 테스트
│   ├── services/             # 서비스 테스트
│   └── conftest.py           # 테스트 설정
├── migrations/               # 데이터베이스 마이그레이션
├── scripts/                  # 유틸리티 스크립트
│   ├── seed_data.py          # 데이터 시드
│   └── backup.py             # 백업 스크립트
├── docs/                     # 문서화
│   ├── api/                  # API 문서
│   └── development/          # 개발 가이드
├── .github/                  # GitHub 워크플로우
├── pyproject.toml            # 의존성 관리
├── Dockerfile                # 컨테이너 구성
├── docker-compose.yml        # 개발 환경 설정
└── README.md                 # 프로젝트 설명

### pharmacy o4o platform 폴더 구조  (크로스 플랫폼 지원)
Renagang21/o4o-platform/
├── apps/                               # 클라이언트 앱
│   ├── web/                            # 웹 애플리케이션
│   │   ├── admin-portal/               # 웹용 관리자 포털
│   │   │   ├── src/
│   │   │   │   ├── components/         # 컴포넌트
│   │   │   │   ├── pages/              # 페이지
│   │   │   │   │   ├── dashboard/      # 메인 대시보드
│   │   │   │   │   ├── pharmacy/       # 약국 관리 섹션
│   │   │   │   │   ├── seller/         # 판매자 관리 섹션
│   │   │   │   │   ├── supplier/       # 공급자 관리 섹션
│   │   │   │   │   └── platform/       # 플랫폼 관리 섹션
│   │   │   │   ├── features/           # 기능별 모듈
│   │   │   │   ├── contexts/           # 컨텍스트
│   │   │   │   ├── services/           # API 서비스
│   │   │   │   ├── hooks/              # 커스텀 훅
│   │   │   │   ├── utils/              # 유틸리티 함수
│   │   │   │   ├── App.jsx             # 메인 앱 컴포넌트
│   │   │   │   └── main.jsx            # 진입점
│   │   │   ├── public/                 # 정적 파일
│   │   │   ├── package.json            # 의존성
│   │   │   └── vite.config.js          # 빌드 설정
│   │   │
│   │   ├── pharmacy-portal/            # 웹용 약국 포털
│   │   ├── seller-portal/              # 웹용 판매자 포털
│   │   ├── supplier-portal/            # 웹용 공급자 포털
│   │   └── consumer-portal/            # 웹용 소비자 포털
│   │
│   └── mobile/                         # 모바일 애플리케이션
│       ├── pharmacy-app/               # 약국용 모바일앱 (React Native)
│       │   ├── src/
│       │   │   ├── screens/            # 화면
│       │   │   ├── components/         # 컴포넌트
│       │   │   ├── navigation/         # 내비게이션
│       │   │   ├── services/           # API 서비스
│       │   │   ├── hooks/              # 커스텀 훅
│       │   │   ├── utils/              # 유틸리티 함수
│       │   │   └── App.jsx             # 메인 앱
│       │   ├── android/                # 안드로이드 네이티브 코드
│       │   ├── ios/                    # iOS 네이티브 코드
│       │   └── package.json            # 의존성
│       │
│       ├── seller-app/                 # 판매자용 모바일앱
│       ├── supplier-app/               # 공급자용 모바일앱
│       └── consumer-app/               # 소비자용 모바일앱
│
├── packages/                           # 공유 패키지
│   ├── core/                           # 핵심 비즈니스 로직 (플랫폼 독립적)
│   │   ├── src/
│   │   │   ├── auth/                   # 인증 로직
│   │   │   ├── api/                    # API 인터페이스
│   │   │   ├── models/                 # 데이터 모델
│   │   │   └── utils/                  # 공통 유틸리티
│   │   └── package.json
│   │
│   ├── ui-web/                         # 웹용 UI 컴포넌트
│   │   ├── src/
│   │   │   ├── components/             # 웹 컴포넌트
│   │   │   ├── hooks/                  # 웹 훅
│   │   │   └── styles/                 # 웹 스타일
│   │   └── package.json
│   │
│   ├── ui-mobile/                      # 모바일용 UI 컴포넌트
│   │   ├── src/
│   │   │   ├── components/             # 모바일 컴포넌트
│   │   │   ├── hooks/                  # 모바일 훅
│   │   │   └── styles/                 # 모바일 스타일
│   │   └── package.json
│   │
│   ├── admin/                          # 관리자 기능 코어 로직
│   │   ├── src/
│   │   │   ├── services/               # 비즈니스 서비스
│   │   │   ├── utils/                  # 관리자 유틸리티
│   │   │   └── index.js
│   │   └── package.json
│   │
│   ├── pharmacy/                       # 약국 관련 코어 로직
│   ├── seller/                         # 판매자 관련 코어 로직
│   ├── supplier/                       # 공급자 관련 코어 로직
│   ├── consumer/                       # 소비자 관련 코어 로직
│   │
│   ├── template-engine/                # 템플릿 엔진
│   │   ├── src/
│   │   │   ├── components/             # 템플릿 컴포넌트
│   │   │   ├── templates/              # 템플릿 정의
│   │   │   ├── editor/                 # 편집기 로직
│   │   │   └── index.js
│   │   └── package.json
│   │
│   └── api-client/                     # API 클라이언트
│       ├── src/
│       │   ├── clients/                # API 클라이언트
│       │   ├── hooks/                  # API 훅
│       │   └── index.js
│       └── package.json
│
├── server/                             # 백엔드 서버 코드
│   ├── api/                            # API 서버
│   │   ├── src/
│   │   │   ├── controllers/            # API 컨트롤러
│   │   │   ├── middlewares/            # 미들웨어
│   │   │   ├── routes/                 # 라우트 정의
│   │   │   ├── services/               # 비즈니스 로직
│   │   │   ├── models/                 # 데이터 모델
│   │   │   ├── utils/                  # 유틸리티
│   │   │   └── server.js               # 서버 진입점
│   │   ├── package.json
│   │   └── nodemon.json                # 개발 서버 설정
│   │
│   ├── modules/                        # 기능별 모듈
│   │   ├── admin/                      # 관리자 API 모듈
│   │   │   ├── src/
│   │   │   │   ├── controllers/        # 컨트롤러
│   │   │   │   │   ├── pharmacy.js     # 약국 관리 컨트롤러
│   │   │   │   │   ├── seller.js       # 판매자 관리 컨트롤러
│   │   │   │   │   ├── supplier.js     # 공급자 관리 컨트롤러
│   │   │   │   │   └── platform.js     # 플랫폼 관리 컨트롤러
│   │   │   │   ├── routes/             # 라우트
│   │   │   │   ├── services/           # 서비스
│   │   │   │   └── index.js
│   │   │   └── package.json
│   │   │
│   │   ├── commerce/                   # 이커머스 모듈
│   │   │   ├── src/
│   │   │   │   ├── api/                # 모듈 API
│   │   │   │   ├── services/           # 비즈니스 로직
│   │   │   │   └── index.js
│   │   │   └── package.json
│   │   │
│   │   ├── tenant/                     # 테넌트 관리 모듈
│   │   ├── pharmacy/                   # 약국 관련 모듈
│   │   ├── supplier/                   # 공급자 관련 모듈
│   │   └── ...                         # 기타 비즈니스 모듈
│   │
│   └── gateway/                        # API 게이트웨이
│       ├── src/
│       │   ├── routes/                 # 라우트 정의
│       │   ├── proxy/                  # 프록시 설정
│       │   ├── middlewares/            # 미들웨어
│       │   └── server.js               # 게이트웨이 진입점
│       └── package.json
│
├── tools/                              # 개발 도구
│   ├── generators/                     # 코드 생성 도구
│   │   ├── component/                  # 컴포넌트 생성기
│   │   ├── module/                     # 모듈 생성기
│   │   └── app/                        # 앱 생성기
│   │
│   ├── scripts/                        # 유틸리티 스크립트
│   │   ├── setup.js                    # 초기 설정 스크립트
│   │   ├── build.js                    # 빌드 스크립트
│   │   └── deploy.js                   # 배포 스크립트
│   │
│   └── config/                         # 공통 설정
│       ├── eslint/                     # ESLint 설정
│       ├── prettier/                   # Prettier 설정
│       └── tsconfig/                   # TypeScript 설정
│
├── docs/                               # 문서화
│   ├── architecture/                   # 아키텍처 문서
│   ├── api/                            # API 문서
│   ├── development/                    # 개발 가이드
│   └── README.md                       # 메인 문서
│
├── tests/                              # 통합 테스트
│   ├── e2e/                            # 엔드투엔드 테스트
│   ├── integration/                    # 통합 테스트
│   └── setup/                          # 테스트 설정
│
├── infrastructure/                     # 인프라 코드
│   ├── docker/                         # Docker 구성
│   │   ├── api/                        # API 서비스 Dockerfile
│   │   ├── gateway/                    # 게이트웨이 Dockerfile
│   │   └── docker-compose.yml          # 개발 환경 설정
│   │
│   └── k8s/                            # Kubernetes 설정
│       ├── api/                        # API 서비스 매니페스트
│       ├── gateway/                    # 게이트웨이 매니페스트
│       └── apps/                       # 앱 매니페스트
│
├── .github/                            # GitHub 관련 설정
│   ├── workflows/                      # GitHub Actions 워크플로우
│   │   ├── ci.yml                      # CI 파이프라인
│   │   ├── apps.yml                    # 앱 배포
│   │   └── api.yml                     # API 배포
│   │
│   └── ISSUE_TEMPLATE/                 # 이슈 템플릿
│
├── .eslintrc.js                        # ESLint 설정
├── .prettierrc                         # Prettier 설정
├── package.json                        # 루트 패키지 구성
├── lerna.json                          # Lerna 설정 (사용 시)
├── nx.json                             # Nx 설정 (사용 시)
└── README.md                           # 프로젝트 README