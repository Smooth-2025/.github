# 👋 Welcome to Team SMOOTH

**Team SMOOTH**는 **LG CNS Am Inspire Camp 2기 최종 프로젝트 팀**으로,  
안전한 주행 환경을 만들기 위해 함께 고민하고 개발하는 모빌리티 팀입니다.   

운전을 하다 보면 언제든 예기치 못한 상황이 찾아올 수 있습니다.  
갑작스러운 사고나 노면 문제는 혼자서는 대응하기 어렵죠.  
우리는 차량과 도로, 사람을 연결하는 **C-ITS(Cooperative-Intelligent Transport Systems)** 기반의 솔루션을 만들고 있습니다.  

또한 모빌리티와 데이터 기반 서비스를 **MSA(Microservices Architecture)** 로 구현하며,  
실시간 사고 알림, 운전자 성향 분석, 도로 위험 데이터 축적을 통해  
더 안전하고 신뢰할 수 있는 주행 경험을 만들어가고 있습니다. 🚗

---

## 🧑‍💻 Our Team

| 이름 | 담당 영역 | GitHub |
|------|-----------|--------|
| 최수인 | ProjectLead, Frontend (Web), Design | [@Choi suin](https://github.com/whl5105) |
| 이담 | Frontend (Web), Backend (Drivecast Service) | [@damiiya](https://github.com/damiiya) |
| 이병강 | Frontend (Web), Backend (API Gateway, User Service) | [@Byeongkang](https://github.com/131c2) |
| 김민주 | Cloud Infrastructure | [@Minju Kim](https://github.com/minju26) |
| 염태범 | Backend (Pothole Analysis Service), Infra | [@djaxoqja](https://github.com/djaxoqja) |
| 박지영 | Frontend (Web), Backend (Drivecast, Accident Service) | [@Jiyoung Park](https://github.com/pjy2163) |
| 정송미 | Backend (Driving Analysis Service) | [@Songmi54](https://github.com/Songmi54) |
| 박서희 | Backend (Driving Analysis, Accident Service), Infra | [@SeoHee Park](https://github.com/seohee-P) |

---

## 🚀 What We Do
- 🚨 **실시간 사고·돌발 알림**  
- 🧑‍🤝‍🧑 **주변 운전자 성향 공유**  
- 🛣️ **포트홀 등 이상 노면 자동 기록**  
- 📞 **119 자동 신고 및 긴급 연락망 알림**  
- 📊 **운전 습관 리포트 제공**  

---

## 🎥 Demo & Resources

- 📑 [최종 발표자료](https://drive.google.com/file/d/1znX1z5ypiPR0pASkGa1KZRLig8BlxpWk/view?usp=sharing)  
- 🎬 [발표 영상](https://drive.google.com/file/d/1OW3yNgwCbc-h_0VzSjmCNnnG0N_VNepQ/view?usp=sharing)  
- 🚗 [시연 영상](https://drive.google.com/file/d/1PLJrci_4GNHDNcY8IiDXCr41BNHFNXDD/view?usp=sharing)  

---

## 🏗️ System Overview

SMOOTH 시스템은 **MSA(Microservices Architecture)** 구조로 설계되어,  
Client, IoT, Gateway, Service, Data 계층이 유기적으로 연결되어 동작합니다.

- **Client Layer**: 운전자 주행 서비스 웹, 관리자 대시보드 (React, Three.js, STOMP)
- **IoT Layer**: AWS IoT Core / Greengrass를 통한 차량 데이터 수집
- **Gateway Layer**: Spring Cloud Gateway + Security로 인증/인가 및 요청 라우팅 처리
- **Service Layer (도메인별 마이크로서비스)**
  - **User Service**: 사용자 및 인증 관리
  - **Drivecast Service**: 주행 데이터 실시간 처리 및 전송
  - **Accident Service**: 사고 이벤트 기록 및 관리
  - **Pothole Analysis Service**: 포트홀 탐지 및 데이터 축적
  - **Driving Analysis Service**: 운전 습관/성향 분석 및 리포트 생성
- **Data Layer**
  - RDS(MySQL), DynamoDB, S3, Athena, Glue를 활용한 데이터 저장 및 분석
  - Redis/Valkey (세션/메시지/위치 캐시)

📌 이 구조는 도메인 단위 서비스 분리와 API Gateway를 통한 통합 진입점으로, 
확장성과 장애 격리성을 동시에 확보합니다.

<img width="1920" height="779" alt="Image" src="https://github.com/user-attachments/assets/7f38c73f-0a54-4ea6-b65f-a8b6c3f5bc01" />

---

## ☁️ Infrastructure Overview

SMOOTH는 AWS 기반 클라우드 네이티브 환경에서 운영됩니다.  
EKS를 중심으로, IoT Core → Kinesis → Lambda → Flink 파이프라인을 통해 데이터를 처리하고,  
ArgoCD·Prometheus·Grafana를 통해 CI/CD 및 모니터링을 수행합니다.

- **컨테이너 & 네트워크**: Amazon EKS + ALB, API Gateway
- **데이터 파이프라인**: IoT Core/Greengrass → Kinesis Data Streams → Flink 실시간 처리
- **스토리지 & 분석**: S3, RDS, DynamoDB, Athena, Glue
- **캐싱**: Amazon ElastiCache(Redis) 기반 세션·위치·메시지 캐싱
- **CI/CD & 운영**: GitHub → Jenkins → ECR → ArgoCD, 모니터링은 CloudWatch·Grafana·Prometheus

<img width="1519" height="1067" alt="Image" src="https://github.com/user-attachments/assets/81f9c229-e8e8-4495-99d9-29cadb15fd3a" />

---

## 🛠️ Tech Stack

SMOOTH 프로젝트는 최신 프론트엔드, 백엔드, 클라우드 네이티브 기술을 활용해 개발되었습니다.  

- **Frontend**: Vite · React · TypeScript · ReduxTK · Three.js · Stomp  
- **Backend**: Spring Boot · Spring Security · Spring Cloud · JWT · MySQL · Redis · YOLO  
- **CI/CD**: GitHub · Jenkins · Amazon ECR · ArgoCD · Kubernetes  
- **IoT & Analytics**: AWS IoT Core · Greengrass · Kinesis · Flink · Athena · Glue  
- **Compute**: Lambda · EC2 · EKS  
- **Storage & DB**: S3 · RDS · DynamoDB · ElastiCache  
- **AI**: Amazon Bedrock  
- **Monitoring & Logging**: CloudWatch · Grafana · Prometheus  
- **IaC**: AWS CloudFormation · Helm  

---

## 🔍 Key Repositories

| Repository | 설명 |
|------------|------|
| [mobile-frontend](https://github.com/Smooth-2025/mobile-frontend) | 운전자용 모바일 주행 서비스 웹 |
| [admin-frontend](https://github.com/Smooth-2025/admin-frontend) | 관리자 대시보드 |
| [gateway-service](https://github.com/Smooth-2025/gateway-service) | API Gateway, 인증/라우팅 |
| [user-service](https://github.com/Smooth-2025/user-service) | 사용자 관리 서비스 |
| [drivecast-service](https://github.com/Smooth-2025/drivecast-service) | 실시간 운전 데이터 처리 |
| [driving-analysis-service](https://github.com/Smooth-2025/driving-analysis-service) | 운전자 성향 분석 |
| [pothole-analysis-service](https://github.com/Smooth-2025/pothole-analysis-service) | 포트홀 탐지 및 분석 |
| [accident-service](https://github.com/Smooth-2025/accident-service) | 사고 이벤트 처리 |
| [tech-study](https://github.com/Smooth-2025/tech-study) | 팀 기술 학습 및 스터디 기록 |

---

※ 본 Organization은 팀 프로젝트 성격으로, 별도의 공식 Contact 채널은 운영하지 않습니다.
