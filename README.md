# Asset-No-1 팀프로젝트

## 목차

1. [팀 소개](#팀-소개)
2. [프로젝트 개요](#프로젝트-개요)
   - [주제](#주제)
   - [선정 배경](#선정-배경)
3. [사용한 기술 스택](#사용한-기술-스택)
4. [기능 소개](#기능-소개)
5. [요구사항 정의서](#요구사항-정의서)
   - [프로필](#프로필)
   - [업무 대화 기능](#업무-대화-기능)
   - [감사 기능](#감사-기능)
   - [영화 챗봇 기능](#영화-챗봇-기능)
   - [시스템 알람 기능](#시스템-알람-기능)
   - [일정 챗봇 기능](#일정-챗봇-기능)
6. [설치 및 사용법](#설치-및-사용법)
   - [설치](#설치)
   - [사용법](#사용법)
7. [기여](#기여)
8. [참고](#참고)

## 팀 소개

**팀 이름**: Asset-No-1  
**의미**: 미래 자산 1조를 담은 의미의 팀 이름입니다.

<img src="https://github.com/user-attachments/assets/54c8f2f6-5f6e-4c1c-a738-3f6077eaaeb5" alt="자산 1조 이미지" width="250" />

### 예비 1조 클럽 명단

| 이름     | 역할            |
|:--------:|:---------------:|
| 함선우   | PM(Project Manager) |
| 김동욱   | TL(Tech Leader)     |
| 임영인   | GM(Geometry Manager) |
| 김도현   | AC(Agile Coach)      |

## 프로젝트 개요

### 주제

사내 채팅 및 영화 정보 검색 챗봇 기능이 가능한 업무용 메신저 개발

### 선정 배경

1. **사내 기술 유출 우려**: 사내 정보 보호를 위한 커뮤니케이션 툴의 필요성
2. **부적절 및 부정한 메시지 감찰**: 감사팀이 사내 메신저의 대화 내용을 모니터링할 수 있도록 하기 위함

## 사용한 기술 스택

- ![Apache Kafka](https://img.shields.io/badge/Apache%20Kafka-000000?style=flat&logo=apache-kafka&logoColor=white): 실시간 데이터 스트리밍 및 메시징 시스템
- ![Apache Spark](https://img.shields.io/badge/Apache%20Spark-E25A1C?style=flat&logo=apache-spark&logoColor=white): 대규모 데이터 처리 및 분석
- ![Apache Airflow](https://img.shields.io/badge/Apache%20Airflow-017E9A?style=flat&logo=apache-airflow&logoColor=white): 워크플로우 오케스트레이션 및 스케줄링 
- ![Apache Zeppelin](https://img.shields.io/badge/Apache%20Zeppelin-006400?style=flat&logo=apache-zeppelin&logoColor=white): 데이터 시각화 및 분석

## 기능 소개

1. **업무 대화 기능**:
   - 사용자는 실시간으로 업무 관련 대화를 주고받을 수 있습니다.

2. **시스템 챗봇 기능**:
   - Airflow의 성공적인 작업 완료 여부를 확인할 수 있는 챗봇 기능을 제공합니다.

3. **영화 챗봇 기능**:
   - 채팅방에 `@영화제목`을 입력하면 해당 영화에 대한 정보를 제공하는 기능을 갖추고 있습니다.

4. **업무 대화 감사 기능**:
   - 채팅방에서 오고간 대화 내용을 저장하고, 통계를 생성하여 Zeppelin을 통해 시각화합니다.

## 요구사항 정의서

### 프로필

| **요구사항 ID** | **구분**        | **요구사항 설명**            | **중요도** | **난이도** | **구현 상태** |
|:---------------:|:---------------:|:----------------------------:|:----------:|:----------:|:-------------:|
| RQ-001          | Username 설정   | 사용자의 이름을 설정합니다.   | 필수       | 하         | O             |

### 업무 대화 기능

| **요구사항 ID** | **구분**         | **요구사항 설명**                   | **중요도** | **난이도** | **구현 상태** |
|:---------------:|:----------------:|:------------------------------------:|:----------:|:----------:|:-------------:|
| RQ-002          | 메세지 보내기    | 사용자가 채팅방에 메세지를 보냅니다.   | 필수       | 중         | O             |
| RQ-003          | 메세지 받기      | 상대방이 보낸 메세지를 받습니다.       | 필수       | 하         | O             |
| RQ-004          | 메세지 시간 표시 | 메세지를 보낸 시간을 표시합니다.       | 필수       | 중         | O             |

### 감사 기능


| **요구사항 ID** | **구분**                | **요구사항 설명**                                                | **중요도** | **난이도** | **구현 상태** |
|:---------------:|:-----------------------:|:----------------------------------------------------------------:|:----------:|:----------:|:-------------:|
| RQ-005          | 채팅 내역 저장           | 채팅 내역을 json 파일로 저장합니다.                               | 필수       | 상         | O             |
| RQ-006          | 특정 단어 사용 횟수      | 사용자 별로 특정 단어(비방, 욕설) 사용 횟수를 통계합니다.        | 필수       | 중         | △             |
| RQ-007          | 시간대 별 채팅 통계      | 시간대 별로 채팅량을 통계합니다.                                  | 필수       | 중         | △             |
| RQ-008          | 시간 단어 통계           | 활발했던 시간에 가장 많이 쓰인 단어를 통계합니다.                 | 선택       | 중         | X             |

### 영화 챗봇 기능

| **요구사항 ID** | **구분**          | **요구사항 설명**                                               | **중요도** | **난이도** | **구현 상태** |
|:---------------:|:-----------------:|:---------------------------------------------------------------:|:----------:|:----------:|:-------------:|
| RQ-009          | 영화 정보 검색    | "@영화제목"을 입력하면 해당 영화 정보를 출력합니다.              | 필수       | 중         | O             |

### 시스템 알람 기능

| **요구사항 ID** | **구분**      | **요구사항 설명**                                                | **중요도** | **난이도** | **구현 상태** |
|:---------------:|:-------------:|:----------------------------------------------------------------:|:----------:|:----------:|:-------------:|
| RQ-010          | 성공 알람     | Airflow task가 성공 시 Line에 success 알람이 전송됩니다.           | 필수       | 중         | O             |
| RQ-011          | 실패 알람     | Airflow task가 실패 시 Line에 fail 알람이 전송됩니다.              | 필수       | 중         | O             |

### 일정 챗봇 기능

| **요구사항 ID** | **구분**         | **요구사항 설명**                                            | **중요도** | **난이도** | **구현 상태** |
|:---------------:|:----------------:|:------------------------------------------------------------:|:----------:|:----------:|:-------------:|
| RQ-012          | 시간 알람        | 지정한 시간이 되면 알람이 전송됩니다.                        | 선택       | 하         | X             |

## 설치 및 사용법

### 설치

- [설치 방법 적기]

### 사용법

- 메신저를 실행하고, 사용자 계정을 등록합니다.
- 업무 대화, 시스템 챗봇, 영화 챗봇 기능을 사용하여 다양한 기능을 테스트합니다.
- 데이터 감사 및 통계 시각화는 Zeppelin 대시보드에서 확인할 수 있습니다.

## 기여

이 프로젝트는 팀원들이 협력하여 기술적 문제를 해결하고, 사내 커뮤니케이션의 효율성을 높이는 동시에 기술 유출 방지와 부적절 메시지 감찰을 위한 강력한 도구를 만드는 데 기여했습니다.

## 참고

프로젝트 관련 코드
- Team Reposit: [바로가기](https://github.com/asset-No-1/teamchat)
