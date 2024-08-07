Chapter3 - 1. 데이터 저장소
==============================

## (1) 데이터 모델
- 데이터 모델: 현실 세계의 정보를 인간과 컴퓨터가 이해할 수 있도록 추상화하여 표현한 모델이다.
- 표시 요소: 구조, 연산, 제약 조건
- 데이터 모델 절차: 요구조건 분석/ 개념적 설계/ 논리적 설계/ 물리적 설계 (요개논물)
- 개념적 설계: 사용자의 요구에 대한 트랜잭션을 모델링, ERD
- 논리적 설계: 트랜잭션이 인터페이스를 설계
- 물리적 설계: 논리 데이터 모델을 DBMS에 맞게 변환, 반정규
<br>

## (2) 논리 데이터 모델
- 논리 데이터 모델: 개념 모델로부터 업무 데이터 및 규칙을 구체적으로 표현한 모델
- 종류: 관계/
- 관계 데이터 모델
  - 데이터를 2차원 테이블 형태로 구성한 모델
  - 릴레이션, 튜플, 속성, 카디널리티, 차수, 스키마, 인스턴스
  - 관계대수: 관계형 데이터베이스에서 원하는 정보와 그 정보를 어떻게 유도하는가를 기술하는 절차적 정형 언어
  - 관계대수의 종류: 일반 집합 연산자, 순수 관계 연산자
  <p>
  <img
  src="https://velog.velcdn.com/images/khs0415p/post/2902fca1-ad71-4461-9022-a2b6c9b003ef/image.png"
  width=50%
  height=50%
  />
  <img
  src="https://velog.velcdn.com/images/khs0415p/post/9f762fdc-43ed-423d-be48-e22afe95a0c3/image.png"
  width=50%
  height=50%
  />
  </p>
  
  - 관계해석: 튜플 관계 해석과 도메인 관계 해석을 하는 비절차적 언어
- 논리 데이터 모델링 속성
  - 개체, 속성, 관계로 구성
  - 피터 챈 모델: 개체 ㅁ, 속성 ⬭, 관계 ◇
  - 까마귀발 모델: 개체 + 속성 => 표, 관계 => 직선 + 까마귀발
- E-R 모델: 요구사항으로부터 얻어낸 정보들을 개체, 속성, 관계로 기술한 모델
- 정규화
  - 이상 현상: 데이터의 중복성으로 인해 릴레이션 조작 시 발생하는 비합리적 현상(삽입, 삭제, 갱신 이상)
  - 함수 종속: 부분/완전/이행 함수 종속 (Partial/Full/Transitive Functional Dependency)
  - 데이터베이스 정규화 단계
    - 1정규형(1NF): 원자값으로 구성
    - 2정규형(2NF): 부분 함수 종속 제거(= 완전 함수적 종속 관계로 만들기)
    - 3정규형(3NF): 이행함수 종속 제거
    - 보이스-코드 정규형(BCNF): 결정자 후보 키가 아닌 함수 종속 제거
    - 4정규형(4NF): 다치(다중 값) 종속 제거
    - 5정규형(5NF): 조인 종속 제거
  - 반 정규화: 정규화된 엔터티, 속성, 관계에 대해 역으로 중복, 통합, 분리 등을 수행하는 데이터 모델링 기법
<br>

## (3) 물리 데이터 모델
- 데이터 무결성: 데이터베이스에 저장된 데이터 값과 그것이 표현하는 현실 세계의 실제 값이 일치하는 성질
- 데이터 무결성 종류
  - 개체 무결성: 한 엔터티에서 같은 기본키 x, 혹은 기본키 NULL 허용 안함 - 기본 키, 유니크 인덱스
  - 참조 무결성: 외래 키가 참조하는 값이 기본 키값이나 NULL이어야 함 - 외래 키
  - 속성 무결성: 속성의 값은 지정된 규칙을 준수해야 함 - CHECK, NULL / NOT NULL, DEFAULT
  - 사용자 정의 무결성: 사용자의 의미적 요구사항을 준수해야 함 - Trigger, 사용자 정의 데이터 타입
  - 키 무결성: 한 릴레이션에 같은 키값을 가진 튜플들을 허용할 수 없음 - 유니크
- 키
  - 조건을 만족하는 튜플을 찾거나 순서대로 정렬할 때 다른 튜플들과 구별할 수 있는 기준이 되는 속성
  - 특성: 유일성, 최소성
  - 종류: 기본 키, 대체 키, 후보 키, 슈퍼 키, 외래 키
- 파티셔닝
  - 테이블 또는 인덱스 데이터를 파티션(Partition) 단위로 나누어 저장하는 기법이다.
  - 유형
    - 레인지 파티셔닝: 연속적인 숫자나 날짜가 기준, 손쉬한 관리 기법 -> 관리시간 단축
    - 해시 파티셔닝: 파티션 키의 해시 함수 값이 기준, 균등한 데이터 분할
    - 리스트 파티셔닝: 명시적 제어 가능, 분포도가 비슷하고 데이터가 많은 SQL에서 컬럼 조건이 많이 들어오는 경우 유용
    - 컴포지트 파티셔닝: 앞의 3개 중 2개 이상의 파티셔닝 결합, 파티션이 클 때 유용
    - 라운드로빈: 라운드로빈으로 회전하면서 새로운 행을 파티션에 할당, 행의 고른 분포

<br>

Chapter3 - 2. 데이터베이스 기초 활용
==============================
