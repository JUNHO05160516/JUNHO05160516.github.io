---
layout: single
title:  "[자격증(ADP)] 3 과목. 데이터 분석 기획 1장. 분석 과제 발굴 (2)"
categories: ADP
tag: [ADP, 자격증, 3 과목, 하향식 접근 방식, 상향식 접근 방식, 분석 프로젝트 관리 방안]
toc: true
toc_sticky: true
toc_label: '페이지 주요 목자'
author_profile: false
sidebar:
    nav: "docs"
---



## 분석 과제 발굴

### [하향식 접근 방식: Top down Approach]

- 체계적 단계화 / Why 관점 / 문제 -> 해법 / 지도학습
- Problem Discovery (문제 탐색) -> Problem Definition (문제 정의) -> Solution Search (해결방안 탐색) -> Feasibility Study (타당성 검사)

**1. Problem Discovery 문제 탐색**

1) 비즈니스 모델 기반 문제 탐색

- 업무, 제품, 고객, 규제와감사, 지원 인프라
- 새로운 문제의 발굴 및 장기적인 접근을 위해서는 현재 수행하고 있는 비즈니스뿐만 아니라 환경과 경쟁 도구의 변화 및 역량의 재해석을 통한 "혁신"의 관점에서 분석 기회를 추가 도출해야 한다.
- 새로운 관점의 접근 필요
- 거시적 관점 ~ 메가 트랜드: 사회, 기술, 경제, 환경, 정치
- 경쟁자 확대 ~ 경쟁사의 동향: 대체제, 경쟁자, 신규 진입자
- 시장 니즈 탐색 ~ 고객 니즈의 변화: 고객, 채널, 영향자들
- 역량의 재해석 ~ 내부 역량, 파트너 네트워크

2) 외부 참조 모델 기반 문제 탐색**

- 기존에 수행한 분석 과제를 살펴보는 것
- 데이터 분석 활용 사례
- 벤치마킹

3) 분석 유즈 케이스 정의

- 풀어야 할 문제에 대한 상세한 설명 및 해당 문제를 해결했을 때 발생하는 효과를 명시함으로써 향후 데이터 분석 문제로의 전환 및 적합성 평가에 활용

**2. Problem Definition 문제 정의**

- 비즈니스 문제 -> 데이터 분석 문제로의 변환
- 분석 수행자 & 최종 사용자의 관점

**3. Solution Search 해결방안 탐색**

- 수행 옵션 도출

|분석기법 및 시스템 (How) / 분석 역량 (Who)|분석 역량 확보|분석 역량 미확보|
|:---|:---:|:---:|
|**기존 시스템**|기존 시스템 개선 활용|교육 및 채용을 통한 역량 확보|
|**신규 도입**|시스템 고도화|전문 업체 Sourcing|

**4. Feasibility Study 타당성 검토**

- 타당성 평가 -> 과제선정
- 경제적 타당성
- 데이터 및 기술적 타당성

![시급성 vs 난이도](https://user-images.githubusercontent.com/104074491/167981171-e8d18901-3e20-48e2-961e-d960c508f5d1.png)

### [상향식 접근 방식: Bottom Up Approach]

**1.**

- What 관점 / 디자인 사고 / 감정이입
- 데이터를 기반으로 문제 정의 및 해결방안 탐색
- 데이터 -> 분석 -> 문제/통찰력/지식
- 비지도 학습 방법: 데이터 자체의 결합, 연관성, 유사성을 중심으로 접근

**2. 프로토타이핑 접근법**

- 시행착오를 통한 문제 해결
- 사용자가 문제나 데이터를 정확하게 규정하기 어렵고 데이터 소스도 명확히 파악하기 어려운 상황에서 일단 분석을 시도해보고 그 결과를 확인해 가면서 반복적으로 개선해가는 방법
- 비록 완전하지는 못하다 해도 신속하게 해결책이나 모형을 제시함으로써 이를 바탕으로 문제를 좀 더 명확하게 인식하고 필요한 데이터를 식별하여 구체화
- 애자일 (Agile) 프로젝트 관리방식
- 가설의 생성 > 디자인에 대한 실험 > 실제 환경에서의 테스트 > 테스트 결과에서의 통찰 > 도출 및 가설 확인
- 잘 설계된 프로토타이핑을 지속하면 실험이 가지고 있는 불명확성이 감소하고 의도했던 결과를 도출할 수 있는 성공 가능성은 높아진다.
- 빅데이터에서 프로토타이핑의 필요성: 문제에 대한 인식 수준 / 필요 데이터의 존재 여부의 불확싱성 / 데이터의 사용 목적의 가변성

**3. 디자인 사고 프로세스**: 상향식 접근방식의 발산 (Diverage) 와 하향식 접근 방식의 수렴 (Coverage) 단계를 반복적으로 수행

## 분석 프로젝트 관리 방안

**1. 분석 과제의 중요 5 가지 특성/ 주요 관리 영역**

1) Data Size

2) Data Complexity: 원천 데이터 (비정형 데이터) 를 통합해서 분석 프로젝트를 진행할 때는 초기 데이터의 확보와 통합뿐만 아니라 해당 데이터에 잘 적용될 수 있는 분석 모델의 선정 등에 대한 사전 고려가 필요하다.

3) Speed: 시나리오 측면의 속도, 프로젝트 수행시 분석모델의 성능 및 속도를 고려한 개발 및 테스트가 수행되어야 한다.

4) Analytic Complexity: 해석이 가능하면서 정확도를 올릴 수 있는 최적모델을 차는 방안을 사적에 모색해야 한다.

5) Accuracy & Precision

- Precision: 모델을 지속적으로 반복했을 때의 편차의 수준으로써 일관적으로 동일한 결과를 제시한다.
- 분석의 활용 ~ Accuracy / 안정성 ~ Precision

**2. 분석 프로젝트의 관리방안 (프로젝트관리 지침)**

1) 통합: 통합적 운영

2) 이해관계자: 이해관계자를 식별하고 관리

- Data, Business, 분석 등 다양한 영역의 사람들이 프로젝트에 참여하며, Project Sponsor 및 향후 분석 결과를 활용 할 User 등 다양한 사람들의 니즈를 고려해야 한다.

3) 범위: 작업과 인도물을 식별하고 정의

4) 자원: 적절한 프로젝트 자원을 식별하고 확보

5) 시간: 프로젝트 활동의 일정을 수립하고 일정 통제의 진척상황을 관찰

6) 원가: 예산 개발과 원가통제의 진척상황을 관찰

7) 리스크: 위험과 기회를 식별하고 관리

8) 품질: 품질보증, 품질통제/품질목표를 사전에 수립하여 확정

9) 조달: 계획에 요구된 프로세스를 포함하여 제품 및 서비스 또는 인도물을 인수하고 공급자와 관계를 관리하는데 요구되는 프로세스

10) 의사소통: 분석 결과를 모든 프로젝트 이해관계자가 공유할 수 있도록
