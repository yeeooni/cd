[데이터 모델링]

**데이터 모델링의 중요성 및 유의점**

- 중복 : 같은 시간 같은 데이터를 제공
- 비유연성 : 사소한 업무변화에 데이터 모델이 수시로 변경되면 안된다.
- 비일관성 : 신용 상태에 대한 갱신 없이 고객의 납부 이력 정보를 갱신하면 안된다.

_개념, 논리, 물리적 데이터 모델링_

> 외부 스키마 : 사용자가 보는 개인적 DB  스키마를 뜻한다.
>
> 개념 스키마 : 모든 사용자 관점을 통합한 전체 DB를 뜻한다.
>
> 내부 스키마 : 물리적 장치에서 데이터가 실제로 저장되는 곳을 뜻한다.

**데이터 독립성**

- 논리적 독립성 : 개념 스키마가 변경되어도 외부 스키마에는 영향이 없다.
- 물리적 독립성 : 내부 스키마가 변경되어도 외부/개념 스키마는 영향이 없다.

**사상(Mapping)**

- 상호 독립적인 개념을 연결시켜주는 다리 

**데이터 모델링의 3요소**

- Things
- Attributes
- Relationships

데이터 모델링은 프로젝트에 참여한 모두가 알아야 한다.

엔터티 : 집합

인스턴스 : 단수

**데이터 모델 표기법**

1976) 피터첸 ERM

**모델링의 특징**

- 추상화, 단순화, 정확화

**ERD 설계 순서**

- 엔터티를 그린다.(1)
- 엔터티를 배치한다.(2)
- 엔터터의 관계를 설정한다.(3)
- 관계명을 기술한다.(4)
- 관계의 참여도를 기술한다.(5)
- 관계 필수 여부를 표시한다.(6)

**좋은 데이터 모델의 요소**

- 완전성 : 업무에 필요한 모든 데이터가 모델에 정의
- 중복 배제 : 하나의 DB내에 동일한 사실은 중복 되지 않는다.
- 업무 규칙 : 많은 규칙을 사용자가 공유하도록 제공한다.
- 데이터 재사용 : 데이터가 독립적으로 설계되어야 한다.
- 의사소통 : 업무규칙은 엔터티, 서브타입, 속성, 관계 등의 형태로 최대한 자세히 표현한다.
- 통합성 : 동일한 데이터는 한 번만 정의한다. 참조를 활용한다.

**엔터티**

- 업무에 필요하고 유용한 정보를 저장하고 관리하기 위한 집합. 보이지 않는 개념을 포함한다.

**엔터티의 특징**

- 반드시 해당 업무에서 필요하고 관리하고자 한다.
- 유일한 식별자에 의해 식별이 가능하다.
- 두 개 이상의 인스턴스의 집합이다.
- 업무 프로세스에 의해 이용되어야 한다.
- 반드시 속성이 있어야 한다.
- 다른 엔터티와 최소 1개 이상의 관계가 있어야 한다.

**엔터티의 분류**

- 유무형에 따른 분류
  - 유형 엔터티 : 물리적 형태 (사원, 물품, 강사)
  - 개념 엔터티 : 개념적 정보 (조직, 보험상품)
  - 사건 엔터티 : 업무 수행 시 발생 (주문, 청구, 미납)

- 발생시점에 따른 분류
  - 기본 엔터티 : 독립적으로 생성되는 엔터티 (고객, 부서)
  - 중심 엔터티 :  기본 엔터티로부터 발생되는 엔터티 다른 엔터티와의 관계로 많은 행위 엔터티 생성 (계약, 사고, 주문)
  - 행위 엔터티 : 2개 이상의 부모 엔터티로부터 발생, 자주 바뀌거나 양이 증가한다. (주문목록, 사원변경이력)

**엔터티의 명명**

- 현업 업무에서 사용하는 용어 사용, 약어 사용 금지, 단수 명사 사용, 고유한 이름 사용, 생성 의미대로 부여 

**속성**

- 업무에서 필요로 하는 인스턴스로, 관리하고자 하는 의미상 분리되지 않는 최소의 데이터 단위
- 한 개의 엔터티는 2개 이상의 인스턴스 집합
- 한 개의 엔터티는 2개 이상의 속성을 가진다.
- 한 개의 속성은 1개의 속성값을 가진다.

**속성의 분류**

- 기본 : 업무로부터 추출한 모든 일반적인 속성
- 설계 : 업무를 규칙화하기 위해 새로 만들거나 변형, 정의하는 속성 (일련번호)
- 파생 : 다른 속성에 영향을 받아 발생하는 속성, 빠른 성능을 낼 수 있도록 원래 속성의 값을 계산 (합)

**도메인**

- 각 속성이 가질 수 있는 값의 범위

**속성의 명명 규칙**

- 해당 업무에서 사용하는 이름 부여
- 서술식 속성명은 사용 금지
- 약어 사용 금지
- 전체 데이터 모델에서 유일성 확보 

**관계**

- 엔터티의 인스턴스 사이의 논리적인 연광성으로서 존재의 형태로서나 행위로서 서로에게 연관성이 부여된 상태
  - 존재관계, 행위관계

**패어링**

- 엔터티 안에 인스턴스가 개별적으로 관계를 가지는 것 
- _통합모델링언어_ 에는 연관관계와 의존관계가 있는데, 연관(존재적)관계는 항상 이용하는 관계이고, 의존관계는 상대방의 행위에 의해 발생하는 관계이다. ERD에서는 존재적관계와 행위에 의한 관계를 구분하지 않고 표기했지만 통합모델링언어에서는 이를 구분하여 연관관계는 실선, 의존관계는 점선으로 표현한다.

**관계의 표기법**

- 관계명 : 관계의 이름
- 관계차수 : 1:1, 1:M, M:N
- 관계 선택 : 필수관계, 선택관계

**관계 체크사항**

- 두 개의 엔터티 사이에 관심있는 연관 규칙
- 두 개의 엔터티 사이에 정보의 조합 발생
- 업무 기술서, 장표에 관계연결에 대한 규칙 서술
- 업무 기술서, 장표에 관계 연결을 가능케 하는 동사 서술

**식별자**

- 엔터티 내에 인스턴스를 구분하는 구분자, 식별자는 논리 데이터 모델링 관계에서 사용한다. 키는 물리 데이터 모델링 단계에서 사용한다.

**식별자의 특징**

- 주 식별자에 의해 모든 인스턴스들이 유일하게 구분짓는다. (유일성)
- 주 식별자를 구성하는 속성의 수는 유일성을 만족하는 최소의 수가 되어야한다. (최소성)
- 지정된 주 식별자의 값은 자주 변하지 않아야한다. (불변성)
- 주 식별자가 지정이 되면 반드시 값이 들어와야한다.(존재성)

**식별자의 분류**

- 대표성 여부 : 주 식별자, 보조 식별자
  - 주 식별자 : 엔터티 내에서 각 어커런스를 구분할 수 있는 구분자, 타 엔터티와 참조관계를 연결할 수 있다.
  - 보조 식별자 : 어커런스를 구분할 수 있는 구분자이나 대표성을 가지지 못해 참조관계 연결 불가.
- 스스로 생성 여부 : 내부 식별자, 외부 식별자
  - 내부 식별자 : 스스로 생성되는 식별자 
  - 외부 식별자 : 타 엔터티로부터 받아오는 식별자
- 속성의 수 : 단일 식별자, 복합 식별자
  - 단일 식별자 : 하나의 속성으로 구성
  - 복합 식별자 : 두 개 이상의 속성으로 구성
- 대체 여부 : 본질 식별자, 인조 식별자
  - 본질 식별자 : 업무에 의해 만들어지는 식별자
  - 인조 식별자 : 인위적으로 만든 식별자 

