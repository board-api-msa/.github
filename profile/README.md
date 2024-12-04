# **Board API MSA 프로젝트**

## **개요**

간단한 게시판 API를 마이크로서비스 아키텍쳐로 구현해보았습니다.   
이 프로젝트는 **Spring Cloud**와 **마이크로서비스 아키텍처**를 학습하고 실습하기 위해 시작되었습니다.   
최신 기술 스택을 활용하여 확장 가능하고 유연한 마이크로서비스 환경을 구축하는 것을 목표로 합니다.   

## **구성 요소**

프로젝트에 포함되는 마이크로서비스 및 구성 요소는 다음과 같습니다:

- [**Config Server**](https://github.com/board-api-msa/config-server): 중앙화된 설정 관리 서버
- [**Eureka Service Registry**](https://github.com/board-api-msa/eureka-server): 서비스 디스커버리를 위한 레지스트리
- [**API Gateway**](https://github.com/board-api-msa/gateway-server): 외부 요청을 각 마이크로서비스로 라우팅
- [**User Service**](https://github.com/board-api-msa/user-service): 사용자 관리 서비스
- [**Post Service**](https://github.com/board-api-msa/post-service): 게시글 관리 서비스
- [**Comment Service**](https://github.com/board-api-msa/comment-service): 댓글 관리 서비스
- **Kafka Broker**: 비동기 메시징을 위한 카프카
- **Resilience4j 적용**: 회복성 있는 서비스 통신 구현

## **실행 환경**
- **Docker**
- **Kubernetes**

### **실행 명령어**
```cmd
helm install board-api oci://ghcr.io/board-api-msa/chart-release/board-api-msa --version 0.1.0
```

- 명령어 실행후 서비스가 완전히 준비되기까지 15~20초 정도 소요됩니다.   
- Gateway Server가 노출하는 포트는 **31000**번입니다.

## **기술 스택**

프로젝트에서 사용된 주요 기술은 다음과 같습니다:

- **Java 21**
- **Spring Boot**
- **Spring Security**
- **Spring Cloud**
  - Config Server
  - Eureka
  - Gateway
  - OpenFeign
  - Resilience4j
- **Apache Kafka**

## **프로젝트 목표**

- **Spring Cloud**를 활용한 마이크로서비스 아키텍처 이해 및 구현
- **서비스 간 통신**과 **서비스 디스커버리** 메커니즘 학습
- **분산 설정 관리** 및 **API 게이트웨이** 구축
- **회복성 패턴** 적용을 통한 시스템 안정성 향상
- **카프카**를 통한 이벤트 주도 아키텍처 구축 및 **데이터 무결성** 유지