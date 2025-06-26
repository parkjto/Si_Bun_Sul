# 🍽️ Si Bun Sul - 주문 시스템

## 📋 프로젝트 개요

**Si Bun Sul**은 Spring Boot 기반의 웹 주문 시스템으로, 레스토랑이나 카페에서 사용할 수 있는 직관적이고 효율적인 주문 관리 시스템입니다. 사용자(고객)와 관리자(점주) 두 가지 역할을 지원하며, 실시간 주문 처리와 메뉴 관리 기능을 제공합니다.

## 🚀 주요 기능

### 👤 사용자 기능
- **메뉴 조회**: 카테고리별 메뉴 확인
- **장바구니 관리**: 메뉴 추가/수정/삭제
- **주문 처리**: 실시간 주문 확인 및 결제
- **반응형 UI**: 모바일 친화적인 인터페이스

### ⚙️ 관리자 기능
- **관리자 인증**: 로그인/회원가입/비밀번호 찾기
- **메뉴 관리**: 메뉴 추가/수정/삭제
- **카테고리 관리**: 메뉴 카테고리 관리
- **주문 관리**: 실시간 주문 현황 확인
- **결제 관리**: 결제 상태 관리

## 🛠️ 기술 스택

### Backend
- **Java 21**: 최신 Java 버전 사용
- **Spring Boot 3.3.5**: 웹 애플리케이션 프레임워크
- **Spring Data JPA**: 데이터베이스 ORM
- **Spring WebFlux**: 반응형 웹 지원
- **Spring Thymeleaf**: 서버 사이드 템플릿 엔진
- **Spring Validation**: 데이터 검증
- **Lombok**: 보일러플레이트 코드 제거

### Database
- **MySQL**: 관계형 데이터베이스
- **Hibernate**: JPA 구현체

### Frontend
- **HTML5/CSS3**: 마크업 및 스타일링
- **JavaScript**: 클라이언트 사이드 로직
- **Bootstrap 5**: 반응형 UI 프레임워크
- **Thymeleaf**: 서버 사이드 렌더링

## 📁 프로젝트 구조

```
Si_Bun_Sul/
├── src/main/java/com/sys/OrderSystem/
│   ├── Controller/           # 웹 컨트롤러
│   │   ├── AdminController.java
│   │   ├── CategoryController.java
│   │   ├── MenuController.java
│   │   ├── MenuManagementController.java
│   │   ├── OrderApiController.java
│   │   ├── OrderController.java
│   │   └── OrderSystemController.java
│   ├── Entity/              # JPA 엔티티
│   │   ├── Administrator.java
│   │   ├── Category.java
│   │   ├── Menu.java
│   │   ├── Order.java
│   │   ├── OrderItem.java
│   │   └── Payment.java
│   ├── Repository/          # 데이터 접근 계층
│   │   ├── AdministratorRepository.java
│   │   ├── CategoryRepository.java
│   │   ├── MenuRepository.java
│   │   ├── OrderItemRepository.java
│   │   ├── OrderRepository.java
│   │   └── PaymentRepository.java
│   ├── Service/             # 비즈니스 로직
│   │   ├── AdministratorService.java
│   │   ├── CategoryService.java
│   │   ├── MenuService.java
│   │   └── OrderService.java
│   └── DTO/                 # 데이터 전송 객체
│       └── BasketDTO.java
├── src/main/resources/
│   ├── templates/           # Thymeleaf 템플릿
│   │   ├── index.html       # 메인 페이지
│   │   ├── menu.html        # 메뉴 페이지
│   │   ├── login.html       # 로그인 페이지
│   │   ├── join.html        # 회원가입 페이지
│   │   ├── dashboard.html   # 관리자 대시보드
│   │   ├── menumanagement.html
│   │   └── ordermanagement.html
│   ├── static/              # 정적 리소스
│   │   ├── images/          # 메뉴 이미지
│   │   └── img/             # UI 이미지
│   └── application.properties
└── build.gradle            # Gradle 빌드 설정
```

## 🗄️ 데이터베이스 스키마

### 주요 엔티티 관계
- **Administrator**: 관리자 정보
- **Category**: 메뉴 카테고리 (한식, 중식, 양식, 일식 등)
- **Menu**: 메뉴 정보 (카테고리와 1:N 관계)
- **Order**: 주문 정보 (테이블별 주문 관리)
- **OrderItem**: 주문 상세 항목 (Order와 Menu를 연결)
- **Payment**: 결제 정보

## 🚀 설치 및 실행

### 사전 요구사항
- Java 21 이상
- MySQL 8.0 이상
- Gradle 7.0 이상

### 1. 데이터베이스 설정
```sql
CREATE DATABASE ordersystem;
```

### 2. 애플리케이션 설정
`src/main/resources/application.properties` 파일에서 데이터베이스 연결 정보를 수정하세요:

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/ordersystem
spring.datasource.username=your_username
spring.datasource.password=your_password
```

### 3. 애플리케이션 실행
```bash
# 프로젝트 루트 디렉토리에서
./gradlew bootRun
```

### 4. 접속
- **메인 페이지**: http://localhost:8081
- **관리자 페이지**: http://localhost:8081/login

## 📱 주요 페이지 설명

### 1. 메인 페이지 (`/`)
- 사용자와 관리자 모드 선택
- 반응형 디자인으로 모바일 친화적

### 2. 메뉴 페이지 (`/menu`)
- 카테고리별 메뉴 표시
- 실시간 장바구니 관리
- 주문 확인 및 결제

### 3. 관리자 로그인 (`/login`)
- 관리자 인증
- 세션 기반 로그인 관리

### 4. 메뉴 관리 (`/menumanagement`)
- 메뉴 추가/수정/삭제
- 이미지 업로드 지원
- 카테고리별 메뉴 관리

### 5. 주문 관리 (`/ordermanagement`)
- 실시간 주문 현황 확인
- 주문 상태 관리
- 결제 처리

## 🔧 API 엔드포인트

### 주문 관련 API (`/api`)
- `GET /api/basket/{tableId}`: 장바구니 조회
- `POST /api/basket/add`: 장바구니에 메뉴 추가
- `POST /api/basket/update`: 장바구니 수량 수정
- `POST /api/basket/remove`: 장바구니에서 메뉴 제거
- `POST /api/basket/clear`: 장바구니 비우기
- `POST /api/orders/confirm`: 주문 확인
- `GET /api/orders/list`: 완료된 주문 목록

## 🎨 UI/UX 특징

### 반응형 디자인
- Bootstrap 5를 활용한 모바일 친화적 인터페이스
- 사이드바 기반 네비게이션
- 실시간 장바구니 사이드바

### 사용자 경험
- 직관적인 메뉴 카드 레이아웃
- 실시간 수량 조절 기능
- 부드러운 애니메이션 효과
- 명확한 가격 표시

## 🔒 보안 기능

- **세션 기반 인증**: 관리자 로그인 세션 관리
- **입력 검증**: Spring Validation을 통한 데이터 검증
- **SQL 인젝션 방지**: JPA를 통한 안전한 데이터베이스 접근

## 📊 성능 최적화

- **JPA 지연 로딩**: 필요한 데이터만 로드
- **트랜잭션 관리**: `@Transactional` 어노테이션 활용
- **이미지 최적화**: 적절한 이미지 크기 및 포맷 사용

## 🚧 향후 개선 계획

- [ ] 실시간 알림 시스템 (WebSocket)
- [ ] 결제 시스템 연동
- [ ] 재고 관리 시스템
- [ ] 고객 리뷰 시스템
- [ ] 매출 통계 및 분석


---

**Si Bun Sul** - 맛있는 주문 경험을 제공하는 스마트 주문 시스템 🍽️
