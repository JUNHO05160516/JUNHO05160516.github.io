---
layout: single
title:  "[자격증(ADP)] 5 과목. 데이터 시각화 3 장. 시각화 구현"
categories: ADP
tag: [ADP, 자격증, 5 과목, 데이터 시각화, 시각화 구현]
toc: true
toc_sticky: true
toc_label: '페이지 주요 목자'
author_profile: false
sidebar:
    nav: "docs"
---




## 3 장. 시각화 구현

|분류|도구|적용방법|
|:---:|:---:|:---:|
|시각화 플랫폼|Cagnos Insight, Information Builders, PowerPivot, PowerView, Visual, SAS, Enterprise Business Intelligence, Tableau, R, EXCEL, CartoDB, Gephi|플랫폼 설치/구축 필요, 플랫폼에서 제공하는 기능/명령어 실행|
|시각화 라이브러리|D3.js, InfoVis, Toolkit, jQuery Visualize, Google Charts, Tangle, NodeBox|라이브러리 설치 필요, 라이브러리가 제공하는 API로 코드 작성|
|인포그래픽스|iCharts, Visualize, Visual.ly|웹서비스 형태로 제공되며 회원 가입이 필요하다. 제공되는 템플릿으로 인포그래픽스 구현|

**1. ggplot**
- fill(): 내부 색상을 바꿔준다
- ggplot() + geom_point() + theme_wsj() 3 가지 함수로 구성된다.
- geometric object: 기하 객체
- colour: 명목형 변수, 테두리 색상, 라인의 색상
- fill: 내부 색
- alpah: 투명도
- facet_grid(변수명~.): 시각화 가로 & 범주 우측
- facet_grid(.~변수명): 시각화 세로 & 좌측
- guides(colour="): 색의 범위


**2. 공간분석**

1) 구글비즈

2) 샤이니

- 웹 프로그래밍 지식이 없더라도 인터렉트브한 웹 그래픽을 만들 수 있다.
- 인터랙티브한 데이터 정리와 질의를 쉽게 할 수 있다.
- HTML, CSS 로 만든 사용자 콘텐츠를 쉽게 통합할 수 있다.
- headerPanel: 제목 / 주제
- sidebarPanel 은 mainPanel 에서 다룰 수 있는 컴포넌트들이 들어간다.
- mainPanel: 실질적으로 보여주는 부분
- ui.R : User Interface, 컴포넌트 클래스 설정
- server.R: R에서 구동시킨 코드가 들어가고 각각 id 값을 설정해 ui.R 에 input 과 output 값으로 작동한다.
- ui.R 과 sever.R 이 같은 디렉토리에 있어야 한다.

3) 모자이크 플롯

- 복수의 범주형 변수 분포 파악에 도움이 되는 시각화 방법
- 두 변수의 구조적 특성을 파악하는 데 도움이 된다.
- 범주형 변수를모자이크 플롯을 활용하면 유의미한 집단을 파악할 수 있다.

**3. D3.js**

- 자바스크립트 기반의 데이터 시각화 라이브러리
- HTML5, SVG, CSS 로 데이터 시각화
- 크롬, 사파리, 오페라 브라우저에서 동작
- SVG 요소를 이용한 벡터 기반 그래프이다.
- 데이터 획득 > 데이터 파싱 > 데이터 필터링 > 데이터 표현 상호작용 추가

|SVG|Canvas|
|:---:|:---:|
|화면에 출력할 모든 정보를 개체 자체에 저장한다. 다시 그리기 유리하지만 속도에 문제가 발생한다.|화면에 출력한 모든 정보를 저장하지 않는다. 다시 그리기는 효율이 떨어지지만 속도에 있어 유리하다. 최초에 컨택스트 (객체) 를 얻을 필요가 있다.|

- 스케일: 데이터를 직접 입력하는 대신 scale 이라는 객체로 데이터와 시각적 요소 간의 관계를 정의한다.
- range(): 입력 데이터를 막대차트로 출력하기 위해서는 스케일이 필요하다. 실제 출력 (=입력) 크기 범위를 지정하는 함수
- ticks(): 각 축의 눈금 단위를 지정
- orient(): 스캐터 플롯에서 눈금의 위치를 나타낸다.
- transform(): rotate, translate 등이 함께 사용되는 함수로 시각화 요소의 위치를 변경하는 속성
- transition(): 생성된 개체가 시간에 따라 속성값이 부드럽게 변화하며 다이나믹한 그래프를 그릴 수 있게 해준다.
- Data-Binding: 각 데이터의 값과 SVG 객체의 속성을 묶어서 연결한다.
- Appending node: enter()를 이요하여 각 데이터를 하나씩 업데이트하고 나오면 DOM 트리에 노드 붙이기를 한다.
