# matmatgotgot_project

### 구조
matgot-aws/
├── docker-compose.yml
├── .env.example
│
├── matmatgotgot_back/                  # Spring Boot 백엔드
│   ├── Dockerfile
│   ├── build.gradle
│   ├── settings.gradle
│   ├── gradlew
│   └── src/main/
│       ├── java/com/twotwo/matmatgotgot/
│       │   ├── MatmatgotgotApplication.java
│       │   ├── domain/
│       │   │   ├── admin/               # 관리자 (신고 처리)
│       │   │   │   ├── controller/
│       │   │   │   ├── entity/
│       │   │   │   ├── mapper/
│       │   │   │   └── service/
│       │   │   ├── board/               # 커뮤니티 게시판
│       │   │   │   ├── controller/      # BoardController, NaverController
│       │   │   │   ├── entity/
│       │   │   │   ├── mapper/
│       │   │   │   └── service/
│       │   │   ├── main/                # 메인 페이지
│       │   │   │   ├── controller/
│       │   │   │   ├── dto/response/
│       │   │   │   ├── mapper/
│       │   │   │   └── service/
│       │   │   ├── member/              # 회원 (JWT 인증)
│       │   │   │   ├── controller/
│       │   │   │   ├── dto/
│       │   │   │   │   ├── request/
│       │   │   │   │   └── response/
│       │   │   │   ├── entity/
│       │   │   │   ├── mapper/
│       │   │   │   └── service/
│       │   │   ├── receiptocr/          # 영수증 OCR (Clova)
│       │   │   │   ├── config/
│       │   │   │   ├── controller/
│       │   │   │   ├── dto/
│       │   │   │   └── service/
│       │   │   ├── restaurant/          # 식당 등록·리뷰
│       │   │   │   ├── controller/
│       │   │   │   ├── dto/
│       │   │   │   │   ├── request/
│       │   │   │   │   └── response/
│       │   │   │   ├── entity/
│       │   │   │   ├── mapper/
│       │   │   │   └── service/
│       │   │   └── trip/                # 맛집 투어 코스
│       │   │       ├── controller/
│       │   │       ├── dto/
│       │   │       │   ├── request/
│       │   │       │   └── response/
│       │   │       ├── mapper/
│       │   │       └── service/
│       │   ├── global/
│       │   │   ├── config/              # MyBatis, S3, CORS
│       │   │   ├── exception/           # GlobalExceptionHandler, ErrorCode
│       │   │   ├── response/            # ApiResponse
│       │   │   └── util/               # S3FileUtil, EmailSender, DateUtils
│       │   └── security/
│       │       ├── JwtTokenProvider.java
│       │       ├── JwtAuthFilter.java
│       │       ├── SpringSecurityConfig.java
│       │       ├── CustomUserDetailsService.java
│       │       ├── GoogleOAuthService.java
│       │       └── GoogleUserProfile.java
│       └── resources/
│           ├── application.properties
│           ├── mapper/
│           │   ├── AdminMapper.xml
│           │   ├── BoardMapper.xml
│           │   ├── MainMapper.xml
│           │   ├── MemberMapper.xml
│           │   ├── restaurant/RestaurantMapper.xml
│           │   └── trip/TripMapper.xml
│           └── templates/
│               └── joinEmail.html
│
└── matmatgotgot_front/                 # React 프론트엔드
    ├── Dockerfile
    ├── nginx.conf
    ├── package.json
    ├── vite.config.js
    └── src/
        ├── App.jsx
        ├── main.jsx
        ├── store/
        │   └── useAuthStore.js          # Zustand 인증 상태
        ├── api/
        │   ├── index.js                 # axios 인스턴스
        │   ├── memberApi.js
        │   └── routeApi.js
        ├── assets/
        │   ├── img/                     # 공통 아이콘 SVG
        │   ├── logo/                    # 서비스·소셜 로그인 로고
        │   ├── main/                    # 메인 배너 이미지
        │   ├── board/
        │   └── restaurant/
        ├── components/
        │   ├── commons/                 # Header, Footer
        │   ├── main/                    # Slide, MyCourse, CardTemp
        │   ├── board/                   # BoardList, NaverMap
        │   ├── member/                  # BoardLikeList, BoardReports
        │   ├── restaurant/              # RestaurantItem, ReviewCommentItem
        │   ├── trip/                    # CourseCollect, SelectedCourseList
        │   └── ui/                     # Button, Pagination, TextEditor, ReportModal
        └── pages/
            ├── main/                    # Main, Main_login
            ├── member/                  # LoginPage, JoinPage, MypagePage, Finding
            ├── board/                   # BoardListPage, BoardViewPage, BoardWritePage
            ├── restaurant/              # RestaurantMain, RestaurantView, ReviewRegist
            ├── trip/                    # TripMain, CreateCourse, CourseDetail, EditCourse
            ├── admin/                   # AdminPage
            └── else/                   # FAQ, 공지사항, 이용약관, 개인정보처리방침
