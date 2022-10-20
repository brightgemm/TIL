# ADsP 자격증





## 1. 데이터의 이해

   

### 01. 데이터의 이해

#### 데이터의 특성

- 존재적 특성: 객관적 사실
- 당위적 특성: 추론, 예측, 전망, 추정을 위한 근거

#### 데이터의 유형

- 정성적: 비정형
- 정량적: 정형
  - 수치로 명확하게 표현되는 데이터. 양이 커도 DBMS에 저장, 검색, 분석하기 쉬움
- **[기출]**: 데이터의 유형은 정성, 정량. 암묵지, 형식지(X)

#### 지식경영의 핵심이슈

- 암묵지: 개인의 내면화된 지식 -> 조직 지식으로 공통화
- 형식지: 언어, 기호, 숫자로 표출화된 지식 -> 개인 지식으로 연결화
- 암묵지와 형식지의 상호작용: 공통화 -> 표출화 -> 연결화 -> 내면화
  - 표출화:개인의 내재된 경험을 객관적인 데이터로 문서나 매체에 저장, 가공, 분석하는 과정

#### DIKW

- 데이터 > 정보 > 지식 > 지혜

   

#### 데이터베이스

- 정형데이터 관리 -> 빅데이터 출현으로 비정형데이터 관리까지 포함

#### 데이터베이스 구성요소

- 메타데이터: 데이터에 관한 구조화된 데이터. 다른 데이터를 설명해 주는 데이터
- 인덱스: 데이터베이스의 테이블에서 고속 검색, 레코드 접근과 관련한 효율적인 순서 매김 동작에 대한 기초 제공

#### 데이터베이스 특징

- **intergrated**: 중복없는 통합 데이터
- **sorted**: 저장 매체에 저장
- **shared**: 복수의 이용자가 서로 다른 목적으로. 복잡
- **changeable**: 데이터 삽입, 삭제, 갱신 등. 현재의 정확한 데이터 유지해야 함
- 기계가독성, 검색가독성, 원격조작성
- 신속한 정보획득, 경제적으로 검색 가능
- 체계적인 축적, 내용 추가 및 갱신 용이
- 정보기술 발전에 영향
- 경제, 산업 발전에 영향

#### 기업 내부 데이터베이스

- OLTP(On-Line Transaction Processing): 호스트 컴퓨터가 DB 엑세스 및 관리. 데이터 갱신 위주
- OLAP(On-Line Analytical Processing): 정보 위주의 분석 처리.  데이터 조회 위주, 대화식 처리
- **CRM**(Customer Relationship Management): 고객관계관리
- SCM(Supply Chain Management): 공급망 관리
  - 기업이 외부 공급업체 또는 제휴업체와 통합된 정보시스템으로 연계하여 시간과 비용을 최적화시키기 위한 것
  - 자재 구매, 생산, 제고, 유통, 판매, 고객 데이터로 구성
- BA(Business Analytics): 경영 의사결정을 위한 통계적, 수학적 분석에 초점을 둔 기법
- 제조분야
  - **ERP**(Enterprise Resource Planning): 전사적 자원 관리. 인사, 재무, 생산 등 통합 시스템으로 관리
  - CRM: 고객 중심 자원 극대화
  - **BI**(Business Intelligence): 기업 보유 데이터를 분석하여 의사결정에 활용하는 프로세스. **데이터 기반의 의사결정을 지원하기 위한 리포트 중심의 도구**
  - RTE(Real Time Enterprise): 회사 전 부분의 정보를 하나로 통합. 실시간 기업 경영시스템
- 금융부문
  - EAI(Enterprise Application Integration): 상호 연관된 앱을 연동하여 중앙집중적 정보 관리
  - EDW(Enterprise Data Warehouse): DW를 전사적으로 확장. BPR(업무 재설계), CRM, BSC(균형성과표) 등 분석 앱의 원천
- 유통부문
  - **KMS**(Knowledge Management System): 지식관리시스템
    - 조직 내 구성원들이 축적하고 있는 노하우 등 암묵적 지식을 형식지로 표출화 될 수 있도록 지원하는 등, 조직의 경쟁력 향상을 위해 지식자원을 체계화하고 원활하게 공유가 될 수 있도록 지원하는 시스템
  - RFID(Radio Frequency ID): 주파수를 이용해 ID 식별. 전자태그
- EDI(Electric Data Interchange): 표준화된 양식을 통해 전자적 신호로 바꿔 컴퓨터로 거래처에 전송하는 시스템
- VAN(Value Added Network): 부가가치통신망. 독자적인 네트워크로 정보 교환, 축적, 전송 등
- CALS(Commerce At Light Speed): 전자상거래 구축을 위한 경영통합정보시스템. 컴퓨터를 활용한 자동화시스템
- 물류부문
  - CVO(Commercial Vehicle Operation System): 화물운송정보
  - PORT-MIS: 항만운영정보시스템
  - KROIS: 철도운영정보시스템
- 지리/교통부문
  - GIS: 지리정보시스템
  - RS: 원격탐사
  - GPS
  - ITS: 지능형교통시스템
  - LBS: 위치기반서비스
  - SIM: 공간정보관리
- 의료부문
  - PACS(Picture Archiving and Communication System)
  - U-health
- 교육부문
  - NEIS

#### 데이터웨어하우스(DW)

- 기업 내의 의사결정지원 어플리케이션에 정보 기반을 제공하는 하나의 통합된 데이터 저장 공간
- 기업의 의사결정 과정을 지원하기 위한 주제 중심적으로 통합적이며 시간성을 가지는 비휘발성 데이터의 집합
- 특성
  - 데이터의 주제 지향성
  - 데이터 통합
  - 데이터의 시계열성
  - 데이터의 비휘발성

   

   

### 02. 데이터의 가치와 미래

#### 빅데이터의 정의

> 관점에 따라 3가지로 정의

- 좁은 범위의 정의: 3V (Volume, Variety, Velocity) + (Value, Visualization, Veracity) 
- 중간 범위의 정의: + 기술 변화(데이터 처리, 저장, 분석 기술 및 아키텍쳐, 클라우드 컴퓨팅) 포함
- 넒은 범위의 정의: + 인재, 조직 변화(데이터사이언티스트 등장)

#### 빅데이터 출현 배경

- 고객데이터의 축적
- 거대 데이터 활용 증가
- 기술 아키텍처 및 통계 도구 발전
- 모바일 혁명

#### 빅데이터 비유

- 산업혁명의 석탄, 철
- 21세기의 원유
- 렌즈
- 플랫폼

#### 빅데이터로 인한 변화

- 사전처리 -> 사후처리
- 표본조사 -> 전수조사
- 질 -> 양
- 인과관계 -> 상관관계

#### 빅데이터 활용

- 연관규칙학습
- 유형분석
- 유전자 알고리즘
- 기계학습
- 회귀분석
- 감정분석
- 소셜네트워크분석(사회관계망분석)



##### [기출] 비즈니스 모델

- 플랫폼형 비즈니스 모델: 서비스, 기술 등의 기반 위에 다른 이해관계자들이 보완적인 상품, 서비스, 기술을 제공하는 생태계 구축을 목표로 하는 모델
- 가치사슬형 비즈니스 모델: 가치사슬상의 중요 분야를 수직계열화해서 기업의 효율성 증진 Ex) 자라
- 사회적 가치 기반형 비즈니스 모델
- 고객 중심형 비즈니스 모델



#### 빅데이터 시대의 위기 요인 및 통제 방안

- 사생활 침해 -> 동의에서 책임으로
- 책임 원칙 훼손 -> 결과 기반 책임 원칙 고수
- 데이터 오용 -> 알고리즘 접근 허용

   

   

### 03. 가치창조를 위한 데이터사이언스와 전략 인사이트

#### 데이터 사이언스

- 데이터로부터 의미있는 정보를 추출해내는 학문. 다양한 유형의 데이터를 대상으로 분석 및 효과적인 구현과 전달 과정까지 포함
- 데이터 사이언스의 구성요소
  - Analytics: 수학, 확률모델 머신러닝, 분석학 등
  - 비즈니스 분석: 비즈니스 컨설팅 영역. 커뮤니케이션, 프레젠테이션, 스토리텔링, 시각화 등
  - IT: 데이터 처리와 관련된 IT 영역. 시그널 프로세싱, 프로그래밍, 데이터 엔지니어링, DW 등

#### 데이터 사이언티스트의 역할 및 역량

- 데이터 홍수 속에서 소스를 찾고 대용량 데이터를 구조화, 연결해야 함
- 강력한 호기심 필요. 문제의 이면을 파고들어 질문과 가설을 세우는 능력
- 스토리텔링, 커뮤니케이션, 창의력, 열정, 직관력, 비판적 시각, 글쓰기 능력, 대화능력 등 필요

- Hard Skill
  - 빅데이터에 대한 이론적 지식
  - 분석 기술에 대한 숙련
- Soft Skill
  - 통찰력 있는 분석
  - 설득력 있는 전달
  - 다분야간 협력

#### 인문학 열풍의 이유

- 컨버전스 -> 디버전스: 단순세계화에서 복잡한 세계화로의 변화
- 생산 -> 서비스: 비즈니스 중심이 제품생산에서 서비스로 이동
- 생산 -> 시장창조: 공급자 중심의 기술경쟁에서 무형자산의 경쟁으로 변화

   

### 04. 빅데이터 상식

#### DBMS

- Data Base Management System

- 데이터베이스를 관리하여 응용 프로그램들이 DB를 공유하며 사용할 수 있는 환경을 제공하는 소프트웨어
- DB 구축 틀 제공, 효율적인 데이터 검색, 저장 기능 제공
- Ex. 오라클, 인포믹스, 액세스 등

#### DBMS 종류

- 관계형 DBMS
  - 데이터를 컬럼과 로우를 이루는 하나 이상의 테이블로 정리. 프라이머리키가 각 로우 식별
  - 로우는 레코드 또는 튜플로 부르며, 일반적으로 각 테이블/관계는 하나의 entity type을 대표함
  - 로우는 그 entity 종류의 인스턴스를 대표, 컬럼은 인스턴스의 속성을 대표
- 객체지향 DBMS
  - 정보를 객체 형태로 표현하는 DB 모델
  - 사용자 정의 데이터 및 멀티미디어 데이터 등 복잡한 데이터 구조를 표현, 관리
- 네트워크 DBMS
  - 레코드와 레코드 사이의 관계를 노드와 간선으로 표현하는 그래프를 기반으로 하는 DB 모델
- 계층형 DBMS
  - 트리 구조를 기반으로 하는 계층 DB 모델

   

#### SQL

- Structured Query Language
- DB에 접근할 수 있는 DB 하부 언어

#### SQL 집계함수

- AVG: 평균
- COUNT: 개수 (**수치형, 문자형 모두 가능**)
- SUM: 합계
- STDDEV: 분산
- MIN: 최솟값
- MAX: 최댓값

#### SQL 구문

- 데이터 정의 언어(DDL)
  - CREATE, ALTER, DROP, TRUNCATE

- 데이터 조작 언어(DML)
  - SELECT, INSERT, UPDATE, DELETE

 

#### 개인정보 비식별 기술

- 데이터 마스킹: 홍길동 -> 홍**
- 가명처리: 홍길동 -> 임꺽정
- 총계처리: 데이터의 총합만 노출. 개별 데이터 노출X
- 데이터값 삭제: 홍길동 35세 서울거주 한국대 졸업 -> 35세 서울거주
- 데이터 범주화: 홍길동 35세 -> 홍씨 30대

   

#### 데이터 무결성

- Data Integrity. 데이터의 일관성, 유효성, 신뢰성을 보장하기 위해 데이터 변경 시 제한 두기
- 개체 무결성
- 참조 무결성
- 범위 무결성

   

#### 데이터 레이크

- Data Lake
- 대용량의 정형 및 비정형 데이터 저장소
- 별도로 정제되지 않은 자연스러운 상태의 아주 큰 데이터 세트

   

#### 블록체인

- 거래정보를 하나의 덩어리로 보고 이를 차례로 연결한 거래장부
- 거래에 참여하는 모든 사용자에게 거래내역을 보내 주며 거래 때마다 이를 대조하여 데이터 위조 방지

   

#### 빅데이터 분석기술

- 하둡: 여러 개의 컴퓨터를 하나인 것처럼 묶어 대용량 데이터 처리하는 기술. 분산파일시스템
- Apache Spark: 실시간 분산형 컴퓨팅 플랫폼. in-memory 방식으로 처리 속도가 빠름
- Smart Factory: 공장 내 설비와 기계에 IoT 설치. 실시간 공정 데이터
- 머신러닝, 딥러닝: 인공지능, 인공신경망
- **맵리듀스**:  HDFS(분산파일 시스템)에 저장된 데이터들을 SQL으르 이용해 사용자 질의를 실시간으로 처리하는 기술. 예) Apache Hive, Facebook-Presto 등

   

#### 데이터 단위

- 바이트 < 킬로바이트 < 메가 < 기가 < 테라 < 페타 < 엑사 < 제타 < 요타   *외우기: Easy PESY*

#### 데이터 유형

- 정형: 형태(고정된 필드) 있음, 연산 가능, 주로 RDBMS에 저장
  - Ex. ERP, CRM, SCM
- 반정형: 형태(스키마, 메타데이터) 있음, 연산 불가, **주로 파일로 저장**
  - 로그 데이터, 모바일 데이터, 센싱 데이터
- 비정형: 형태 없음, 주로 NoSQL에 저장
  - 영상, 음성, 이미지




#### 빅데이터 가치 산정이 어려운 이유

- 새로운 가치 창출
- 데이터 활용 방식
- 분석 기술의 발전

 

 

## 2. 데이터 분석 기획

### 01. 데이터 분석 기획의 이해

#### 분석기획의 특징

- 분석기획: 분석 수행 전 과제 정의, 관리 방안 등 사전에 계획하는 일련의 작업
- What, Why, How에 대한 계획 수립
- 데이터 사이언티스트는 수학/통계학적 지식 + 정보기술 + 도메인 지식 필요

#### 분석 대상과 방법

<table>
  <tr>
    <td colspan=2>분석 대상(What)</td>
  </tr>
  <tr>
    <td>known</td>
    <td>unknown</td>
  </tr>
  <tr>
    <td>Optimization</td>
    <td>Insight</td>
    <td>known</td>
    <td rowspan=2>분석 방법(How)</td>
  </tr>
  <tr>
    <td>Solution</td>
    <td>Discovery</td>
    <td>unknown</td>
  </tr>
</table>

#### 목표시점별 분석 기획 방안

- 과제 중심적 접근 방식: 당면한 과제를 빠르게 해결. 단기적
- 장기적인 마스터 플랜 방식: 지속적인 분석과제 정의. 중장기적
- 의미있는 분석 = 분석 기술 + IT 및 프로그래밍 + 도메인 전문성 + 의사소통

<table>
  <tr>
    <td></td>
    <td>과제 중심적 접근 방식</td>
    <td>마스터 플랜 방식</td>
  </tr>
  <tr>
    <td>1차 목표</td>
    <td>speed/test</td>
    <td>accuracy/deploy</td>
  </tr>
  <tr>
    <td>과제 유형</td>
    <td>quick/win</td>
    <td>long term view</td>
  </tr>
  <tr>
    <td>접근 방식</td>
    <td>문제 해결</td>
    <td>문제 정의</td>
  </tr>
</table>

#### 분석 기획 시 고려사항

- 가용 데이터(Available Data): 데이터 확보 우선. 데이터 유형에 따라 방법이 다르므로 유형 분석이 선행되어야 함
  - transaction data, human-generated data, mobile data, machine and sensor data
- 적절한 활용방안과 유즈케이스(Proper Business Use Case): 기존의 유사 분석 시나리오 및 솔루션 활용
  - 고객 분석, 소셜미디어 분석, 플랜트 및 시설 관리, 파이프라인 관리, 가격최적화, 사기 탐지
- 장애 요소들에 대한 사전 계획 수립(Low Berrier of Execution): 지속적인 변화 관리 필요
  - cost, simplicity, performance, culture

   

#### 분석 방법론

- 방법론의 구성: 절차, 방법, 도구와 기업, 템플릿과 산출물
- 데이터 기반 의사결정의 장애요소
  - 경험과 감에 따른 의사결정
  - 고정관념, 편향된 생각, 프레이밍 효과(문제의 표현 방식에 따라 동일한 내용임에도 개인의 선택이 달라질 수 있는 현상)
- 방법론 생성과정
  - 암묵지 -> 형식화 -> 형식지 -> 체계화 -> 방법론 -> 내재화 -> 암묵지
- 방법론 적용 업무의 특성에 따른 모델
  - 폭포수 모델: 단계를 순차적으로 진행
  - 프로토타입 모델: 점진적으로 시스템 개발하는 방식. 고객의 요구 분석이 어려울 때 일부분을 우선 개발 -> 성능 평가 -> 개선 작업
  - **나선형 모델**: 반복을 통해 점증적으로 개발하는 방법. 처음 시도하는 프로젝트에 적용 쉬움. 복잡도 상승으로 프로젝트 진행이 어려울 수 있음
- 방법론의 구성(빅데이터 분석의 계층적 프로세스)
  - 단계(단계별 완료 보고서) > 태스크(보고서) > 스텝(보고서 구성요소)
  - 단계: 최상위 계층. 완성된 단계별 산출물 생성. 각 단계는 버전관리 등으로 통제
  - 태스크: 단계를 구성하는 단위 활동. 물리적, 논리적 단위로 품질검토 항목이 됨
  - 스텝: WBS의 워크 패키지에 해당. 입력자료, 처리 및 도구, 출력자료로 구성된 단위 프로세스

#### KDD 분석 방법론

- KDD(Knowledge Discovery in Database): 프로파일링 기술을 기반으로 데이터로부터 통계적 패턴 등을 찾기 위해 체계적으로 정리한 **데이터 마이닝 프로세스**
- 분석 절차
  - **데이터셋 선택(Selection)**: 비즈니스 도메인에 대한 이해와 프로젝트 목표 설정, 목표데이터 구성
  - **데이터 전처리(Preprocessing)**: 잡음, 이상치, 결측치 식별 및 처리. 추가로 요구되는 데이터가 있을 시 selection 재실행
  - **데이터 변환(Transformation)**: 분석 목적에 맞게 변수 생성, 데이터 차원 축소, 학습용/검증용 데이터 분리
  - **데이터 마이닝(Data Mining)**: 분석 목적에 맞는 데이터마이닝 기법 선택하여 알고리즘 실행. 필요에 따라 전처리/변환 재실행
  - **데이터 마이닝 결과 평가(Interpretation/Evaluation)**: 결과에 대한 해석과 평가, 목적과의 일치성 확인

#### CRISP-DM 분석 방법론

- Cross Industry Standard PRocess for Data Mining: **계층적** 프로세스 모델. 4가지 레벨과 6단계로 이루어짐
- 4레벨 구조
  - Phases > Generic Tasks > Specialized Tasks >Process Instances
  - 최상위 레벨은 여러 단계(Phases)로 구성. 각 단계는 일반화 태스크(Generic Tasks)를 포함
  - 일반화 테스크는 데이터마이닝의 단일 프로세스를 완전하게 수행하는 단위. 세분화 태스크(Specialized Tasks)로 구성
    - Ex. 데이터 정제(=일반화 태스크)는 범주형 데이터 정제와 연속형 데이터 정제(=세분화 태스크)로 구성됨
  - 프로세스 실행(Process Instances)는 데이터마이닝을 위한 구체적인 실행 포함
- 프로세스 6단계
  - **업무 이해(Business Understanding)**: 비즈니스 관점에서 목적과 요구사항 이해. 데이터 분석을 위한 문제정의
  - **데이터 이해(Data Understanding)**: 데이터 수집, 속성 분석, 인사이트 발견
  - **데이터 준비(Data Preparation)**: 수집된 데이터에서 분석기법에 적합한 데이터 선택(시간 소요)
  - **모델링(Modeling)**: 모델링 기법과 알고리즘 선택, 파라미터 최적화, 모델 평가
  - **평가(Evaluation)**: 분석결과 평가, 모델링 과정 평가, 모델 적용성 평가
  - **전개(Deployment)**: 실 업무에 적용 계획 수립, 유지보수 계획 수립, 프로젝트 종료 보고서 및 리뷰

#### KDD VS CRISP-DM

<table>
  <tr>
    <td>KDD</td>
    <td>CRISP-DM</td>
  </tr>
  <tr>
    <td>분석대상 비즈니스 이해</td>
    <td>업무 이해</td>
  </tr>
  <tr>
    <td>데이터셋 선택</td>
    <td rowspan=2>데이터의 이해</td>
  </tr>
  <tr>
    <td>데이터 전처리</td>
  </tr>
  <tr>
    <td>데이터 변환</td>
    <td>데이터 준비</td>
  </tr>
  <tr>
    <td>데이터마이닝</td>
    <td>모델링</td>
  </tr>
  <tr>
    <td>데이터마이닝 결과 평가</td>
    <td>평가</td>
  </tr>
  <tr>
    <td>데이터마이닝 활용</td>
    <td>전개</td>
  </tr>
</table>



#### 빅데이터 분석 방법론

- 빅데이터 분석 계층적 프로세스
  - 단계(Phase) > 태스크(Task) > 스탭(step)
- 분석 방법론 5단계
  - 분석기획 -> 데이터 준비 -> 데이터 분석 -> 시스템 구현 -> 평가 및 전개
  - 분석기획
    - 비즈니스 이해 및 범위설정 -> 비즈니스 이해 및 도메인 문제점, 프로젝트 범위 정의서(SOW)
    - 프로젝트 정의 및 계획수립 -> 프로젝트 정의서, 모델 운영 이미지 설계서, 모델 평가 기준, 프로젝트 수행계획서, WBS
    - 프로젝트 위험계획 수립 -> 식별된 위험목록, 위험관리 계획서
  - 데이터 준비
    - 필요 데이터 정의 -> 데이터 정의서, 데이터 획득 계획서
    - 데이터 스토어 설계 -> 정형 데이터 스토어 설계서, 비정형 데이터 스토어 설계서, 데이터 매핑 정의서
    - 데이터 수집 및 정합성 점검 -> 수집된 분석용 데이터, 정합성 점검 보고서
  - 데이터 분석
    - 분석용 데이터 준비 -> 비즈니스 룰, 분석에 필요한 데이터 범위, 분석용 데이터셋
    - 텍스트 분석 -> 분석용 텍스트 데이터, 텍스트 분석 보고서
    - 탐색적 분석 -> 데이터 탐색 보고서, 데이터 시각화 보고서
    - 모델링 -> 훈련용/테스트용 데이터, 모델링 결과 보고서, 알고리즘 설명서(**의사코드** 수준의 상세한 작성 필요), 모니터링 방안
    - 모델 평가 및 검증 -> 모델 평가 보고서, 모델 검증 보고서
  - 시스템 구현:
    - 설계 및 구현 -> 시스템 분석 및 설계서, 구현 시스템
    - 시스템 테스트 및 운영(품질 관리) -> 시스템 테스트 결과보고서, 운영자 매뉴얼, 사용자 매뉴얼, 시스템 운영계획서
  - 평가 및 전개
    - 모델 발전 계획 수립 -> 모델 발전 계획서
    - 프로젝트 평가 및 보고 -> 프로젝트 성과 평가서, 프로젝트 최종 보고서

   

#### 분석과제 발굴 방법론

- 하향식 접근 방법: 현황 분석을 통해 **문제 탐색 -> 문제 정의 -> 해결방안 탐색 -> 타당성 평가 -> 분석과제 도출**. Why 관점
  - 비즈니스 모델 기반 문제 탐색(=비즈니스 모델 캔버스의 9가지 블록 단순화)
    - [업무, 제품, 고객], 규제와 감사, 지원 인프라
  - **분석 기회 발굴의 범위 확장 - 4가지 관점**
    - 거시적 관점: 사회, 기술, 경제, 환경, 정치
    - 경쟁자 확대: 대체재, 경쟁자, 신규 진입자
    - 시장니즈 탐색: 고객, 채널, 영향자들
      - 채널: 커뮤니케이션, 물류, 판매채널 등 기업과 고객의 인터페이스 전반
    - 역량의 재해석: 내부역량, 파트너 네트워크
  - 타당검 검토 대상: 경제성, 데이터, 기술
- 상향식 접근 방법: 기업에서 보유하고 있는 다양한 원천 데이터로부터 분석을 통하여 통찰력과 지식을 얻는 접근 방식. **What 관점**. **문제 정의 자체가 어려운 덩유 데이터를 기반으로 문제의 재정의 및 해결방안을 탐색하고 이를 지속적으로 개선하는 분석과제 발굴 방식**
  - 일번적으로 **비지도 학습** 방법의 의해 수행
  - 프로토타이핑 접근법: 일단 분석을 시도해 보고 결과를 확인해 가면서 반복적으로 개선해 나가는 방법
    - 신속한 해결책이나 모형 제시 -> 문제 인식 및 데이터를 구체화할 수 있기 하는 상향식 접근 방식
    - 가설 생성 -> 디자인에 대한 실험 -> 실제 환경에서 테스트 -> 인사이트 도출 및 가설 확인
    - 프로토타이핑의 필요성: 문제에 대한 낮은 인식 수준, 필요 데이터의 존재 여부 불확실성, 데이터 사용 목적이 가변성

- **디자인 사고**: 상향식 접근 방식과 하향식 접근 방식을 반복적으로 수행하는 상호 보완적인 동적 환경을 통해 분석의 가치를 높일 수 있는 최적의 의사결정 방식

   

#### 분석과제 관리를 위한 5가지 주요 영역

- 데이터 크기(Data Size): 분석하고자 하는 데이터의 양
- 데이터 복잡성(Data Complexity): 데이터에 잘 적용될 수 있는 분석 모델의 선정
- 속도(Speed): 분석 모델의 성능 및 속도를 고려한 개발
- 분석 복잡도(Analytic Complexity): 해석이 가능하면서도 정확도를 올릴 수 있는 최적 모델 탐색
- 정확도&일관성(Accuracy&Precision): 모델과 실제 값 사이의 정확도(활용성), 지속적으로 반복했을 때의 일관성(안전성)

#### 분석 프로젝트의 관리 방안

- 범위
- 시간
  - time boxing 기법 등으로 일정관리 필요
- 원가
- 품질
  - 품질 통제, 품질 보증
- 통합
- 조달
- 자원
- 리스크
  - 회피, 전이, 완화, 수용
- 의사소통
- 이해관계자

   

   

### 02. 분석 마스터 플랜

#### 분석 마스터 플랜 수립 프레임 워크

- **ISP(Information Strategy Planning)**: 정보기술 또는 정보시스템을 전략적으로 활용하기 위하여 조직 내외부 환경을 분석하여 기회나 문제점을 도출하고 사용자의 요구사항을 분석하여 시스템 구축 우선순위를 결정하는 등 중장기 마스터 플랜을 수립하는 절차
- 분석 마스터 플랜: 일반적인 ISP 방법론을 활용하되 데이터 분석 기획의 특성을 고려하여 수행하고 **분석과제를 빠짐없이 도출**한 후 과제의 우선순위 결정하고 단기 및 중장기로 나누어 계획 수립

- 마스터 플랜 수립 시 고려해야 할 요소

  - **우선순위 고려요소 및 평가기준**: 적용 우선 순위 설정
    
    - **전략적 중요도(전략적 필요성, 시급성)**
    - **실행 용이성(투자 용이성, 기술 용이성)**
    - **비즈니스 성과/ROI**
      - ROI 관점에서 빅데이터의 특징
        - 투자비용 요소(3V): Volume + Variety + Velocity  -> 난이도가 평가 기준
        - 비즈니스 효과(4V): Value -> 시급성이 평가 기준
    
  - 적용범위/방식 고려요소: 분석 구현 로드맵 수립
  
    - 업무 내재화 적용 수준, 분석 데이터 적용 수준, 기술 적용 수준
  
    - 단계적 구현 로드맵(3단계)
  
      - 데이터 분석체계 도입: 문제 정의 및 마스터 플랜 수립
      - 데이터 분석 유효성 검증: 유효성 및 타당성 검증, 실현가능성 검증, 분석 알고리즘 및 아키텍처 설계
      - 데이터 분석 확산 및 고도화: 업무 프로세스 내재화 준비, 활용시스템 구축
      - 데이터 분석체계는 고적적인 폭포수 방식도 있으나 반복적 수행을 통한 방법을 많이 사용함
  
         

#### 분석 거버넌스 체계 5구성요소

- **조직(Organization)**: 분석 기획 및 관리를 수행
- **프로세스(Process)**: 과제 기획 및 운영
- 분석 관련 **시스템(System)**
- **데이터(Data)**
- **분석 관련 교육 및 마인드 육성 체계(Human Resource)**

#### 데이터 분석 수준진단: 분석 거버넌스 체계를 수립하기 위한 선행 단계

- **분석 준비도**
- **분석 성숙도**

- 수준 진단 목표
  - 기업의 현재 수준 파악하여 미래의 목표수준 정의
  - 데이터 분석을 위한 기반이 경쟁사에 비해 어느 수준인지, 경쟁력 확보를 위해 어떤 영역에 선택과 집중을 해야하는지 등 개선방안 도출

#### 분석 준비도(readiness)

- 분석 업무를 파악하고 인력, 조직에 대해 평가하고 분석기법, 분석 데이터, 분석 문화, IT 인프라를 평가함으로써 기업의 분석 수준과 목표 수립에 대한 분석 거버넌스 체계를 수립하는데 활용되는 방법론

- **분석 업무, 분석 인력/조직, 분석 기법, 분석 데이터, 분석 문화, 분석 인프라**
  - 분석 업무 파악: 발생한 사실 분석, 예측 분석, 시뮬레이션 분석, 최적화 분석, 분석업무 정기적 개선
- 분석 데이터 진단 항목: 데이터 충분성, 신뢰성, 적시성, 비구조적 데이터 관리, 외부 데이터 활용 체계, 기준 데이터 관리(MDM)

#### 분석 성숙도(Maturity) 

- **능력 성숙도 통합 모델 CMMI(Capability Maturity Model Integration)**: 조직의 성숙도 평가 도구
- 성숙도 수준 분류: 도입단계, 활용단계, 확산단계, 최적화단계
- 분석 성숙도 진단 분류: **비즈니스 부문, 조직/역량 부분, IT 부문**

<table>
  <tr>
    <td>단계</td>
    <td>도입</td>
    <td>활용</td>
    <td>확산</td>
    <td>최적화</td>
  </tr>
  <tr>
    <td>설명</td>
    <td>분석을 시작하여 환경과 시스템 구축</td>
    <td>분석결과를 실제 업무에 적용</td>
    <td>전사 차원에서 분석 관리 및 공유</td>
    <td>분석 진화시켜 혁신 및 성과 향상에 기여</td>
  </tr>
  <tr>
    <td>비즈니스 부문</td>
    <td>- 실적 분석 및 통계<br>
      	- 정기보고 수행<br>
      	- 운영 데이터 기반
    </td>
    <td>- 미래 결과 예측<br>
      	- 시뮬레이션<br>
      	- 운영 데이터 기반
    </td>
    <td>- 전사 성과 실시간 분석<br>
      	- 프로세스 혁신 3.0<br>
      	- 분석규칙 관리<br>
      	- 이벤트 관리
    </td>
    <td>- 외부 환경분석 활용<br>
      	- 최적화 업무 적용<br>
        - 실시간 분석<br>
        - 비즈니스 모델 진화<br>
    </td>
  </tr>
  <tr>
    <td>조직역량 부문</td>
    <td>- 일부 부서에서 수행<br>
      	- 담당자 역량에 의존
    </td>
    <td>- 전문 담당부서에서 수행<br>
        - 분석기법 도입<br>
        - 관리자가 분석 수행
    </td>
    <td>- 전사 모든 부서 수행<br>
        - 분석 COE 조직 운영<br>
        - 데이터 사이언티스트 확보
    </td>
    <td>- 데이터 사이언스 그룹<br>
      	- 경영진 분석 활용<br>
      	- 전략 연계
    </td>
  </tr>
  <tr>
    <td>IT 부문</td>
    <td>- DW<br>
        - 데이터 마트<br>
        - ETL/EAI<br>
        - OLAP
    </td>
    <td>- 실시간 대시보드<br>
      - 통계분석 환경
    </td>
    <td>- 빅데이터 관리 환경<br />
      - 시뮬레이션/최적화<br />
      - 시각화 분석<br />
      - 분석 전용 서버
    </td>
    <td>- 분석 협업 환경<br />
      - 분석 샌드박스<br />
      - 프로세스 내재화<br />
      - 빅데이터 분석
    </td>
  </tr>
</table>


​    

#### 분석 수준 진단결과 사분면 분석: x축 - 준비도, y축 - 성숙도

<table style="text-align: center;">
  <tr>
    <td>정착형(준비도 낮음, 성숙도 높음)</td>
    <td>확산형(준비도 높음, 성숙도 높음)</td>
  </tr>
  <tr>
    <td>준비형(준비도 낮음, 성숙도 낮음)</td>
    <td>도입형(준비도 높음, 성숙도 낮음)</td>
  </tr>
</table>

- 정착형: 준비도는 낮으나 성숙도가 높아 1차적으로 정착이 필요한 기업
- 확산형: 현재 부분적으로 도입되어 지속적인 확산이 필요한 기업
- 준비형: 사전 준비가 필요한 기업
- 도입형: 준비도가 높아 바로 도입할 수 있는 기업

   

#### 분석지원 인프라 방안 수립

- 개별 분석 시스템은 관리 복잡도 및 비용 증대 부작용 -> 장기적,안정성, 확장성을 고려한 플랫폼 구조 도입

- 플랫폼

  - 분석 응용프로그램 + 서비스를 위한 기초 컴퓨터 시스템
  - 구성요소

  <table style="text-align: center; width: 500px;">
    <tr>
      <td colspan=2>분석 서비스 제공 엔진</td>
    </tr>
    <tr>
      <td colspan=2>분석 어플리케이션</td>
    </tr>
    <tr>
      <td colspan=2>분석 서비스 제공 API</td>
    </tr>
    <tr>
      <td colspan=2>데이터 처리 Framework</td>
      <td rowspan=2>협의의 분석 플랫폼</td>
    </tr>
    <tr>
      <td>분석 엔진</td>
      <td>분석 라이브러리</td>
    </tr>
    <tr>
      <td colspan=2>운영체제</td>
    </tr>
    <tr>
      <td colspan=2>하드웨어</td>
    </tr>
  </table>
  
  

#### 데이터 거버넌스

- **전사 차원의 모든 데이터에 대하여 정책 및 지침, 표준화, 운영조직 및 책임 등의 표준화된 관리체계를 수립하고 운영을 위한 프레임워크 및 저장소를 구축하는 것**
- 데이터 거버넌스의 중요 관리 대상: **마스터 데이터, 메타 데이터, 데이터 사전**
- 데이터 거버넌스 체계를 구축함으로써 데이터의 가용성, 유용성, 통합성, 보안성, 안전성 확보
- 데이터 거버넌스는 전사 차원의 IT 거버넌스나 EA의 구성요소로써 구축되는 경우도 있음
- 빅데이터 거버넌스: 데이터 거버넌스의 체계 + 빅데이터의 효율적인 관리, 다양한 데이터의 관리체계, 데이터 최적화, 정보보호, **데이터 생명주기 관리**, 데이터 카테고리별 관리 책임자 지정 등 포함



#### 데이터 거버넌스 구성요소

- **원칙(Principle)**
  - 데이터 유지, 관리를 위한 지침과 가이드
  - 보안, 품질 기준, 변경관리
- **조직(Organization)**
  - 데이터 관리할 조직의 역할과 책임
  - 데이터 관리자, 데이터베이스 관리자, 데이터 아키텍트
- **프로세스(Process)**
  - 데이터 관리를 위한 활동과 체계
  - 작업 절차, 모니터링 활동, 측정활동



#### 데이터 거버넌스 체계

- **데이터 표준화**
  - 데이터 표준 용어 설정(사전간 상호 검증), 명명 규칙 수립(언어별로 작성), **메타 데이터 구축**, 데이터 사전 구축
- 데이터 관리체계
  - 데이터 정합성 및 활용 효율성을 위해 메타 데이터와 데이터 사전의 관리 원칙 수립
  - 원칙에 근거하여 프로세스 및 담당자 역할과 책임 지정
  - **데이터 생명주기 관리방안**
- 데이터 저장소 관리
  - 메타데이터 및 표준 데이터를 관리하기 위한 전사 차원의 저장소
  - **워크플로우** 및 관리용 응용소프트웨어 지원
  - 관리 대상 시스템과의 인터페이스를 통한 통제
  - 데이터 구조 변경에 따른 **사전 영향 평가** 수행
- **표준화 활동**
  - 데이터 거버넌스 체계 구축 후 표준 준수 여부 주기적 **점검 및 모니터링**



#### 분석을 위한 3가지 데이터 조직 구조

- **집중구조**: 부서1 + 부서2 + DSCoE. 전사 분석 업무를 별도의 전담 조직에서 담당. 업무부서와 이원화
- **기능구조**: 부서1 + 부서2 + 부서3. 해당 업무 부서에서 분석 수행
- **분산구조**: (부서1+ DSCoE) + (부서2+ DSCoE). 분석 조직 인력을 현업 부서로 배치

#### 분석조직 인력구성 (DSCoE: Data Science Center of Exellence)

- 비즈니스 인력
- IT 기술  인력
- 분석전문 인력
- 변화관리 인력
- 교육담당 인력

#### 분석 과제 관리 프로세스

- **과제 발굴**
  1. 분석 아이디어 발굴
  
  2. 분석 과제 후보제안: 과제후보 pool
  
  3. 분석과제 확정: 전사분석 조직-> 분석과제->과제 제안자
  
- **과제 수행**
4. 팀구성: 과제 추진팀
  
5. 분석과제 실행: 과제 수행 지원, 전사분석 조직
  
6. 분석과제 진행관리: 전사분석 조직
  
7. 결과 공유 및 개선: 과제 결과 pool

#### 분석 내재화 단계

- 준비기: 분석 중심 문화 미도입된 상태, 막연한 불안감
- 도입기: 기존 행태로 되돌아가려는 경향, 성공시 강한 탄성에 의해 변화 가속화
- 안정 추진기: 분석 활용이 일상화된 균형 상태

#### 분석적 사고 교육

- 창의적 사고 및 문제해결을 위한 체계적 접근법 숙지
- 데이터 분석기회 발굴 및 과제정의 방법 이해
- 다양한 빅데이터 분석 기법의 활용
- 빅데이터 개념 및 관련 기술의 습득



### 03. 기타

#### 빅데이터 분석 Self Service Analytics

- 주요 포함 기능: BI 도구, Ad hoc Report, OLAP, Visual Discovery, Machine Learning
- 성공적인 적용을 위해서 Reference Method의 작성 및 공유, 표준 데이터의 활용, 데이터 거버넌스, 도구 사용에 대한 지속적 교육 필요
- 데이터 분석 언어와 많은 통계적 지식 필요



#### 4차 산업혁명

- Mass Production
- Mass Customization
- Servitization
  - service science의 하나로 제품과 서비스의 결합을 통한 기업의 새로운 비즈니스 모델
  - 제품의 서비스화와 서비스의 상품화를 모두 포함
  - 파이프라인 비즈니스를 넘어 플랫폼 비즈니스를 위한 모델



#### [기출] 분석방안 구체화

- 의사결정 요소 모형화
- 분석체계 도출
- 분석 필요 데이터 정의
- 분석 ROI 평가
- 분석 활용 시나리오 정의
- 분석 정의서 작성
- 전사 관점 분석 적용



#### [기출] 미래사회의 특성과 빅데이터의 역할

- 불확실 -> 통찰
- 리스트 -> 대응력
- 스마트 -> 경쟁력
- 융합 -> 창조력