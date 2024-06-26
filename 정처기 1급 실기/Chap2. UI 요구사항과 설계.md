Chapter2 - 1. UI 요구사항 확인
==============================

## (1) UI 요구사항 확인
- UI(사용자 인터페이스), UX(사용자 경험)
- UI 유형: CLI, GUI, NUI, OUI
- UI 설계원칙: 직관성, 유효성, 학습성, 유연성
- UI 품질 요구사항: 기능성, 신뢰성, 사용성, 효율성, 유지보수성, 이식성
<br>

## (2) UI 지침
- 소프트웨어 개발 단계별 UI 지침
  - 목표 정의: 3C 분석, SWOT 분석, 시나리오 플래닝, 워크숍
  - 프로젝트 계획: 프로파일, 리서치
  - 요구사항 정의: 페르소나, 브레인스토밍, 요구사항 매트릭스, 정황 시나리오
  - 설계 및 구현: UI 시나리오 문서
  - 테스트: 사용성 테스트
- UI 화면 설계: 와이어프레임, 스토리보드, 프로토타입
- cf. 프로토타입은 기능 시험, 목업은 디자인 시연 목적으로 사용
<br> <br>

Chapter2 - 2. UI 설계
==============================

## (1) UML
- UML: 객체지향 소프트웨어 개발 과정에서, 산출물을 명세화, 시각화, 문서화할 때 사용되는 모델링 기술과 방법론을 통합한 것으로, 표준화된 모델링 기법을 제공
- 특징: 가시화 언어, 구축 언어, 명세화 언어, 문서화 언어
- 구성 요소: 사물, 관계, 다이어그램
- UML 다이어그램
  - 구조적/정적 다이어그램
    - 시스템의 구조 및 구성요소들 간의 관계를 나타내는 다이어그램
    - 종류: 클래스, 객체, 컴포넌트, 배치, 복합체 구조, 패키지
  - 행위적/동적 다이어그램
    - 시스템의 동작 및 상호작용을 나타내는 다이어그램
    - 종류: 유스케이스, 시퀀스, 커뮤니케이션, 상태, 활동, 타이밍
- UML 스테레오 타입
  - 기본 요소 이외의 새로운 요소를 만들어내기 위한 확장 메커니즘
  - <<>>(길러멧 Guillemet) 기호 사용하여 표현
  - 유형
  ```
  <<include>> : 반드시 1 + 1 으로 실행
  <<extend>> : 1 + 1 할지 안할지 선택가능
  <<interface>> : 추상 메서드와 상수만 존재
  <<entity>> : 기억장치에 저장되어야 할 정보 표현
  <<boundary>> : 외부 액터와의 상호 작용 담당
  <<control>> : 기능의 로직 및 제어 담당
  ```
- UML의 유형
  - 클래스 다이어그램
    - 클래스의 속성 및 연산과 클래스 간 정적관계 표현
    - 구성요소: 클래스, 속성, 연산/메서드, 접근제어자(제한자)
    - 클래스 간의 관계: 연관, 의존, 일반화(상속), 실체화, 포함, 집합
    - (Association, Dependency, Generalization, Realization, Composition, Aggregation)
  - 유스케이스 다이어그램
    - 시스템이 제공하고 있는 기능 및 그와 관련된 외부 요소 표현
    - 구성요소: 유스케이스, 액터, 시스템, 시나리오, 이벤트의 흐름
    - 관계: 포함, 확장, 일반화
  - 시퀀스 다이어그램
    - 객체 간 상호작용을 메시지 흐름으로 표현
    - 동적 상호작용을 시간적 개념을 중심으로 모델링
    - 구성요소: 객체, 생명선, 실행, 메시지
    - (Object, Lifeline, Activation, Message)
  - 패키지 다이어그램
    - 서로 다른 패키지들 사이의 의존 관계 표현
    - 구성요소: 패키지, 의존관계(스트레오 타입 사용: import, access)
  - 활동 다이어그램
    - 오퍼레이션이나 처리과정에서 일어나는 일들의 흐름 표현
    - 구성요소: 시작점, 전이, 액션, 액티비티, 종료점, 조건(판단)노드, 병합노드, 포크노드, 조인노드, 구획면
  <br>
  
  <img
  src="https://blog.kakaocdn.net/dn/kzMlg/btqJHayfX48/AqZM3h86htjKcpW91iH7Uk/img.png"
  width=30%
  height=60%
  />
  
  <br>
  
  - 상태 다이어그램
    - 어떤 이벤트에 의해 객체 자신이 속한 클래스의 상태 변화나 객체 간 상호작용하는 과정에서의 상태변화를 표현
    - 객체의 상태: 객체가 갖는 속성값의 변화
    - 구성요소: 상태, 시작상태, 종료상태, 전이, 이벤트, 전이조건
  - 커뮤니케이션 다이어그램
    - 시퀀스 다이어그램과 유사하게 객체 간 상호작용을 메시지 흐름으로 표현
    - 거기에 객체 간의 연관까지 표현
    - 구성요소: 액터, 객체, 링크(객체 간의 관계), 메시지
  - 컴포넌트 다이어그램
    - 물리적인 컴포넌트와 그들 사이의 의존관계 표현
    - 구성요소: 컴포넌트, 인터페이스, 의존관계










