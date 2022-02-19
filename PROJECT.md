# 휙고
- 부서명 : 기술연구소
- 근무기간 : 2020.06.08 ~ 
- 주요업무 : DevOps

## 참여 프로젝트
- 강릉패스 (21.10 ~ )
  - 프로젝트 개요
    - 강릉시 통합 대중교통 MaaS 플랫폼 서비스
      (국토교통부 주관 스마트 시티 챌린지 사업)
  - 프로젝트 담당 업무
    - AWS Cloud + Kubernetes 기반의 Infra 구성 및 CI/CD Pipe Line 구축
    - Terraform 도입으로 Infra 코드화 진행
    - ArgoCD 도입으로 GitOps 기반의 CD 환경 구축
    - Graceful Shutdown 환경 구성으로 보다 견고한 무중단 배포 환경 구축
  - 프로젝트 링크
    - 홈페이지 : https://gangneungpass.com
    - App : https://play.google.com/store/apps/details?id=com.kstc.hwik.pine
- 휙고 (21.03 ~ 21.09)
  - 프로젝트 개요
    - 자사 통합 모빌리티 MaaS 플랫폼 서비스
  - 프로젝트 담당 업무
    - AWS Cloud + Kubernetes 기반의 Infra 구성 및 CI/CD Pipe Line 구축
    - CI 진행 시 Unit Test 및 SonarQube 정적 코드 분석 도입
    - Istio 를 이용하여 다양한 배포 방식 적용 (Rolling Update, A/B Testing, Blue/Green, Canary)
    - Jenkins Pipe Line 으로 AOS 자동 CI/CD 구축
    - Github Action 으로 iOS 자동 CI/CD 구축
  - 프로젝트 링크
    - 홈페이지 : https://www.hwikgo.com
    - App : https://play.google.com/store/apps/details?id=com.kstc.hwik.hwikgo
- 휙파인패스 (20.06 ~ 21.02)
  - 프로젝트 개요
    - 강릉시 통합 대중교통 MaaS 플랫폼 서비스
      (국토교통부 주관 스마트 시티 챌린지 시범 사업)
  - 프로젝트 담당 업무
    - AWS Cloud + Kubernetes 기반의 Infra 플랫폼 구성
    - Jenkins 를 통한 Kubernetes 배포 Pipe Line 구성
    - Github Webhook 연동으로 Jenkins CI/CD 자동화 진행
    - Istio Service Mesh 구성
    - S3+Cloud Front 정적 웹 페이지 기반의 홈페이지 배포 Jenkins Pipe Line 구축
  - 프로젝트 링크
    - 홈페이지 : https://hwik.pinepass.co.kr
    - App : https://play.google.com/store/apps/details?id=com.kstc.hwik.pine

## 기술 상세
### [ AWS Public Cloud 활용 ]
- AWS API Gateway, Lambda, S3, Cloud Front, RDS, ECR, EFS, Cloud Watch 등 AWS 자원을 활용하여 전체 Infra 구성을 경험
- 자사 AWS Cloud VPC 와 파트너사의 On-Premise IDC VPN 을 연결하는 Site-To-Site Network 구성

### [ Kubernetes 기반의 서비스 운영 ]
- EKS 를 활용한 Kubernetes 기반의 MSA 서비스 구축 및 운영
- CPU, Memory Resource 를 참조한 Pod HPA 를 적용하여 운영 안정성 향상
- PV + PVC 를 통해 EFS 를 Mount 하여 Pod Log 영구 보관
- RBAC 기반의 권한 제어로 개발팀 내에서도 Namespace 단위의 팀 별 권한 세분화
- Kubernetes Deployment 의 preStop Hook을 이용한 Graceful Shutdown 무중단 배포 환경 적용

### [CI/CD]
- Go, Java, Python, NodeJS, React, PHP 등 개발 언어에 구애 받지 않는 CI/CD Jenkins Pipe Line 구축
- Jenkins Build 를 통해 배포 버전 확인, Unit Test, SonarQube 정적 코드 분석, Docker Build, Container Image Push 까지 CI 자동화
- Istio 를 활용하여 개발자의 배포 설정에 따라 Rolling Update 외에도 A/B Testing, Blue/Green, Canary 배포를 지원하게끔 배포 환경 개선
- Gradle Build 로 apk 파일을 생성한 후 사내 메신저로 배포하는 Jenkins 기반 Android 배포 Pipe Line 구축
- Unit Test 및 Build, Fastlane 으로 TestFlight 까지 배포하는 Github Action 기반 iOS CI/CD 환경 구축

### [GitOps]
- 기존 Jenkins 수동 Build 방식에서 Github 의 Event Webhook 을 기반으로 CI/CD 자동화로 배포 환경 개선
- Jenkins Pipe Line 에서 필요한 배포 정보를 git 으로 관리하여 최신 배포 정보를 공통 적용될 수 있게끔 배포 환경 구축
- ArgoCD 도입으로 배포 Resource 에 대한 형상관리를 통해 배포 Roll Back 편의성 향상

### [ Infrastructure as Code (IaC) ]
- EKS Cluster 생성 과정을 Jenkins Pipe Line 스크립트로 작성하여 신규 EKS Cluster 생성 과정 자동화 (Cloud Formation, AWS CLI 활용)
- Terraform 도입으로 기존 AWS 자원을 마이그레이션하여 전체 Infra 코드화
- Terraform Cloud 를 이용한 Remote State 관리를 통해 IaC 협업 효율성 향상

### [ Monitoring ]
- Prometheus + Grafana 기반의 Kubernetes Resource 모니터링 환경 구성
- 자체 개발한 Go Batch Job 으로 실시간 Kubernetes Pod 상태 모니터링 시스템 구축
- EFK (Elastic Search + Fluentd + Kibana) 를 이용한 Application Log 수집 및 분석 시스템 구축

### [ 업무 자동화를 위한 Tool 개발 ]
- Go, Python, Bash Script 등을 이용한 업무 자동화로 개발/운영 편의성 향상
- 배포 효율성 증진을 위한 Kubernetes 배포 Resource Yaml 파일 자동 생성 CLI 개발
- EC2 에 별도 설치된 Mysql, MongoDB, InfluxDB 의 Data Dump, System Log 관리를 자동화하는 Bash Shell Script 작성
---
# 케이씨씨정보통신
- 부서명 : 정보기술연구소
- 근무기간 : 2018.02.01 ~ 2020.06.05
- 주요업무 : 솔루션 개발 및 운영, On-Premise 기반의 Private Cloud 관리

## 참여 프로젝트
- CRM4U (19.03 ~ 20.06)
  - 프로젝트 개요
    - Java Spring Framework 를 기반으로 하는 그룹사 고객관리 솔루션
  - 프로젝트 담당 업무
    - Java + JSP 를 이용한 기능 개발
    - 프로젝트 CI/CD 적용
- SMARTCAR4U (18.02 ~ 19.02)
  - 프로젝트 개요
    - 차량 OBD 데이터를 수집하는 파트너사 플랫폼에 API 연동을 하여 그룹사 시승차의 운행 정보, 운행 현황 등을 관리해주는 솔루션
- 프로젝트 담당 업무
  - nodeJS 언어를 이용한 기능 개발
  - Jenkins를 통한 배포 자동화 경험

## 기술 상세
### [ On-Premise 시스템 관리 ]
- KT Giga Office 서비스를 이용한 Private Cloud 시스템 운영 및 관리
- Private Cloud 방화벽 정책 관리
- Zabbix 를 이용한 Private Cloud 내의 서버 모니터링

### [ DevOps ]
- Zabbix Agent 설치 및 Config 에 대한 IaC 관리를 위한 Ansible 적용
- PCS, Pacemaker, Corosync 오픈 소스를 이용한 Zabbix 이중화 구성으로 서버 모니터링 강화
- 기존 서버에 SSH 접근하여 미리 작성된 스크립트를 수동으로 실행하는 배포 방식에서 Jenkins Build 방식으로 변경하여 배포 간편성 및 배포 로그 관리 효율성 향상
- SI 신입사원 OJT 진행 시 CI/CD part에 조교로 참여하여 SVN, Jenkins 를 활용한 CI/CD 교육 진행
