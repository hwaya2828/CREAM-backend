## 🎖  Team CREAM

### 🗓  기간

- 2주 (2021.5.24 - 2021.6.4)

### 🍭  인원

- 인원 : 프론트 3명 & 백엔드 2명

### 🎬  시연 영상

- **[CREAM](https://www.youtube.com/watch?v=kR4HfsWcevo&list=PLZTmS1zO_K1Zj4ZRa-eu3Ugt-DfGC7eXC&index=5)**

### 🔍  선정 의도

- 한정판 의류품 경매 플랫폼 'KREAM'에서 영감을 얻은 경매 시스템 기반 커머스 사이트 구현
- 경매의 가격 수치 변동 특성을 반영한 데이터를 그래프로 시각・도식화하여 구현

### 💡  구현 기능

- **Backend**
    - 소셜 로그인 (카카오톡)
    - 회원 정보 조회
    - 상품 리스트
    - 상품별 상세 데이터
    - 상품별 판매 입찰 & 구매 입찰 내역
    - 상품별 거래 내역
    - 추천 상품
    - 즉시 거래 & 입찰
    - 조건에 따른 상품 필터링
    - 검색
    - AWS EC2 & RDS를 이용한 배포

### 💎  맡은 역할

- 환경 설정
    - 프로젝트 초기 세팅
        - `Django`를 사용하여 프로젝트를 진행하기 위한 초기 세팅
        - `Conda` 가상 환경을 생성 및 실행하고 `Git`으로 관리할 수 있도록 설정
        - `MySQL Database` 생성 및 연동
    - 모델링
        - `AQuery`를 이용하여 프로젝트의 기획에 맞춘 모델링 완료
    - Database 초기 세팅
        - `CSV 파일`을 생성하여 `MySQL Database` 기초 설정 및 관리
        - 초기 세팅이 완료된 Database는 `dump`를 활용하여 `SQL 파일`로 보관

- 기능 구현
    - **소셜 로그인 (카카오톡)**
        - `카카오톡`에서 제공해주는 `API`를 이용하여 전달 받은 `Access Token`을 보내 사용자 정보를 취득
        - `get_or_create`을 사용하여 사용자가 처음 로그인 한 경우 회원 정보를 저장하고, 회원 정보가 존재 하는 경우에는 그 정보를 가져오도록 구현
        - `Database`에 저장된 회원 정보를 이용하여 `JWT`로 새로운 `Access Token`을 생성하여 전달
    - **회원 정보 조회**
        - `Access Token`에서 사용자의 정보를 얻어 유저의 데이터 전송
    - **상품 리스트 & 조건에 따른 상품 필터링 & 검색**
        - 상품 리스트를 전달해야 하는 기능들을 종합하여 하나의 `API`로 통합
        - `if else 삼항표현식`을 사용하여 조건에 따라 선택적으로 데이터 전송
        - `query parameter`를 `Q객체`에 담아 조건에 맞게 `filtering`된 상품 데이터 전송
        - `request.GET.get()`과 `request.GET.getlist()` method를 사용하여 하나 혹은 다중의 조건을 전달 받아 상품의 `filtering`에 적용
        - 검색에는 `__contains`를 사용하여 상품명을 `filtering`하도록 구현
        - 필터링에는 `__in`을 사용하여 `request.GET.getlist()`에서 받아온 조건들을 적용하도록 구현
        - `select_related`와 `prefetch_related` 를 사용하여 각각 정참조 • 역참조 되어 있는 데이터까지 한 번에 가져오도록 하여 `Query`를 줄일 수 있도록 구현

- 시스템 테스트
    - **Unit Test**
        - `Django`의 `TestCase`을 이용한 `Unit Test` 구현

- 배포
    - **AWS RDS**
        - `my_settings.py`에 담겨 따로 관리되고 있는 `Database` 정보를 `settings.py`에서 `import`하여 프로젝트에 연결된 `Database`를 `RDS`로 연결
    - **AWS EC2**
        - `GitHub`에 있는 해당 프로젝트의 `Repository`를 `EC2`에 `Clone`
        - `EC2`에서 프로젝트가 구동될 수 있도록 `miniconda`를 설치하여 새로운 가상환경을 생성하고 `requirements.txt`를 이용하여 필요한 패키지를 설치
        - `Gunicorn`을 설치하고 작동시켜 배포

### 🔮  적용 기술

- **Backend**
  - Python 3.9
  - Django 3.2.4
  - MySQL 8.0.23
  - AWS EC2
  - AWS RDS

- **Cooperation Tool**
  - Git
  - Github
  - Slack
  - Trello
  - AQuery
  - Postman


