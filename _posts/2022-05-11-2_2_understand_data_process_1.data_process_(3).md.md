---
layout: single
title:  "[자격증(ADP)] 2 과목 2 장. 데이터 처리 기술 이해 :: 데이터 처리 프로세스 (2)"
categories: ADP
tag: [ADP, 자격증, 2 과목, 데이터 처리 기술 이해, 데이터 처리 프로세스, 데이버베이스 클러스터, 분산 컴퓨팅 기술, 클라우드 인프라 기술]
toc: true
toc_sticky: true
toc_label: '페이지 주요 목자'
author_profile: false
sidebar:
    nav: "docs"
---


## 데이터베이스 클러스터
- DB를 여러 개의 서버가 나눠서 처리하도록

**1. 장점**

- 고가용성: 장애가 발생하더라도 서비스가 중단되지 않음.
- 병렬처리: 빠른 데이터 검색 및 처리 성능
- 성능 향상

**2. 공유디스크 vs. 무공유**

1) 공유디스크

- 높은 고장 감내성
- 클러스터가 커지면 디스크 영역에서 병목현상 발생
- 모든 노드가 데이터를 수정할 수 없기에 노드 간의 동가화 작업을 위한 별도의 커뮤니케이션 채널이 필요하다.
- Oracle RAC

2) 무공유

- 노드 확장에 제한이 없다.
- 노드에 장애가 발생할 경우를 대비해 고장감내성을 구성해야 한다.
- IBC DB2 ICE

**3. Oracle RAC 데이터베이스 서버**

- 어플리케이션 파티션과 데이터 파티션을 동시에 구현.
- 클러스터의 모든 노드에서 실행되며 데이터는 공유 스토리지에 저장된다.
- 클러스터 내의 모든 노드는 데이터베이스의 모든 테이블에 동등하게 엑세스하며 특정 노드가 데이터를 소유하는 개넘은 없다. 따라서 데이터를 파티셔닝할 필요는 없지만 성능 향상을 위해 빈번하게 파티셔닝 된다.
- 가용성, 확장성, 비용절감

**4. 마이크로소프트 SQL 서버**
- 연합 데이터베이스 형태
- 네트워크를 이용해 연결
- 무공유/ 수평적 분할
- PDV뷰: 테이블을 논리적으로 분리해 물리적으로 분산된 각 노드에 생성하고 각 노드의 데이터베이스 인스턴스 사이에 링크를 구성한 후 모든 파티션에 대한 UNION ALL 을 이용해 논리적인 뷰를 구성하는 방식으로 분산된 환경의 데이터에 대한 싱글 뷰를 제공.
- 파티셔닝 정책에 맞게 테이블과 뷰를 생성해야 하고, 전역 스키마 정보가 없기 때문에 질의 수행을 위해 모든 노드를 액세스해야 한다.
- 페일오버: 평상시 하나의 서버로 운영되고 유사한 서버는 예비로 준비하는 Active_Standby 방식.

**5. MySQL**
- 무공유 구조에서 메모리 기반 데이터베이스의 클러스터링 지원
- 병렬 서버구조로 확장 가능
- 관리 노드: 클러스터 관리/ 클러스터 시작과 재구성 시에만 관여
- 데이터 노드: 클러스터 데이터 저장
- MySQL 노드: 클러스터 데이터 접근

**6. NoSQL**
- Key : Value 형태로 자료 저장
- 빠르게 조회/ 복잡한 Join 연산 기능 X/ 대용량 데이터 & 대규모 확장성
- 구글 빅테이블/ 아마존 Simple DB/ 마이크로소프트 SSDS

## 분산 컴퓨팅 기술

### [맵리듀스]
- 데이터를 가져오지 않고 데이터가 저장한 곳에서 처리
- 맵: 입력 파일을 한 줄씩 읽어 데이터를 변형
- 리듀스: 맵의 결과 데이터를 집계 (shuffle)
- 셔플링: 리듀스의 입력을 key 를 기준으로 정렬/ 맵의 출력이 리듀스의 입력으로 전송하는 과정.
- Input > Splitting > mapping > Shuffling > Reducing > Result
- Split Input > Fork Process > Map > Map Worker:Partition > Reduce Sort (Shuffle) > Reduce Function > Done
- 하둡 맵리듀스 시스템: 클라이언트, 잡트래커, 태스크트래커

### [병렬 쿼리 시스템]
**1. 구글 Sawzall**

- 맵리듀스를 추상화한 스크립트 형태의 병렬 프로그래밍 언어.
- 사용자가 이해하기 쉬운 이터페이스를 제공하여 맵리듀스 개발 생산성을 높인다.

**2. 아파치 Pig (야후)** : 맵리듀스에서 처리할 수 없는 조인 연산 지원

**3. 아피치 하이브**
- SQL 쿼리를 작성하면 자동으로 맵리듀스 작업으로 변경해준다.
- SQL 기반의 퀴리 언어와 JDBC 지원
- HDFS 나 HBASE 와 같은 빅데이터 원본을 HiveQL 질의 언어를 이용하여 분석한다.
- 하둡 스트리밍을 쿼리 내부에 삽입해 사용할 수 있다.

1) 아파치 하이브 아키텍처
- 메타스토어: 내장 메타스토어, 로컬 메타스토어, 원격 메타스토어
- 내장형 더비: 로컬 디스크에 저장, 내장형 메타스토어
- HiveQL: 사용자로부터 입력받은 쿼리를 분석해 쿼리 수행 계획을 작성하고 이에 따르는 맵리듀스 코드 생성.

2) 하이브 언어 모델
- DDL: Create Table, Drop Table, Rename Table, Alter Table, Add Column, Show Table, Describe Table
- DML: 로컬에서 DFS로 데이터 업로드, 쿼리 결과를 테이블이나 로컬 파일 시스템/ DFS 에 저장
- Query: Select, Group by, Joins, Union, Sub Queries, Sampling, Transform

**4. SQL on Hadoop**
- HDFS 에 저장된 데이터를 SQL 혹은 SQL 과 유사한 형태로 처리하고 실시간으로 분산처리
- 아파치 Drill, Hive on Tez, 타조, 샤크 (Spark SQL), 임팔라, Presto

1) 임팔라
- Hive-SQL 채택
- 분산과 트랜잭션 처리를 모두 지원
- 하둡과 HBase 에 저장된 데이터를 대상으로 SQL 질의
- 맵리듀스를 사용하지 않고 실행중에 최적화된 코드를 생성해 데이터를 처리한다.

## 클라우드 인프라 기술

### [서버 가상화 기술]
- 하나의 서버에서 여러 어플리케이션, 미들웨어, 운영체제들이 서로 영향을 미치지 않으면서 동시에 사용
- 가상머신 사이의 데이터 보호
- 예측하지 못한 장애로부터 보호
- 공유 자원에 대한 강제 사용의 거부
- 서버 통합: 더 많은 서버 운영
- 자원 할당에 증가된 유연성: 자원 활동도 극대화
- 테스팅
- 정확하고 안전한 서버 사이징
- 시스템 관리: 하드웨어 장애, 로드 밸런싱, 업그레이드

**1. CPU 가상화**: 하이퍼바이저 = 가상머신 == VMM
1) 하이퍼바이저의 기능
- 하드웨어 환경 에뮬레이션
- 실생환경 격리
- 시스템 자원 할당
- 소프트웨어 스택 보존

2) 완전가상화: 모든 자원을 하이퍼바이저가 직접 제어 & 관리

3) 하드웨어 지원 완전가상화

4) 반가상화
- CPU와 메모리 자원의 동적 변경이 서비스의 중단 없이 이루어질 수 있다.
- 완전가상화에 비해 성능이 뛰어남

5) 호스트 기반 가상화: 호스트 운영체제 위에 하이퍼바이저 탐재

6) 컨테이너 기반 가상화: 운영체제만을 가상화

**2. 메모리 가상화**
- Memory ballooning
- Transparant page sharing
- Memory Overcommitment

**3. I/O 가상화**
- 가상 이더넷
- 공유 이더넷 어댑터
- 가상 디스크 어댑터


