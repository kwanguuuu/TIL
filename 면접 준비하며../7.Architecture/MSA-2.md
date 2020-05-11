## MSA 이해하기

![가트너MSAComponent](https://media.vlpt.us/post-images/tedigom/b6bae160-fb10-11e9-9ef4-395edd3ef4d0/%EA%B0%80%ED%8A%B8%EB%84%88MSAComponent.png)

- inner Artchitecture
- Outer Architecture

### Inner Architecture

내부 서비스와 관련된 아키텍쳐. **내부 서비스를 어떻게 잘 쪼개는지에 대한 설계**

고려해야할 부분

- (마이크로)서비스를 어떻게 정의할 것인가.
- DB access구조를 어떻게 설계할 것인가
- 마이크로 서비스 내 API를 어떻게 설계할 것인가
- 논리적 컴포넌트들의 layer를 어떤 방식으로 설계할 것인가

Inner Architecture는 비즈니스마다 서비스마다 시스템마다 특성이 있어 정해져 있는 표준은 없다. 그래서 어려운 부분



###Outer architecture

- External Gateway
- Service Mesh
- Container Management
- Backing Services
- Telemetry
- CI/CD Automation



**External Gateway**

전체 서비스 외부로부터 들어오는 접근을, 내부구조를 드러내지 않고 처리하기 위한 요소.

사용자 인증과 권한정책등을 수행하고, API게이트웨이가 가장 핵심역할을 담당함

API Gateway : 서버 최 앞단에서 모든 API호출을 받음. 받은 호출을 인중 후 적절한 서비스들 메세징을 전달함 (라우팅 역할)



**Service Mesh**

마이크로서비스 구성요소간의 네트워크를 제어하는 역할을 함.

서비스간의 통신을 위해선 service discovery, service routing, 트래픽 및 보안담당등의 요소가 있어야 하고. 서비스메쉬에서 해당 기능을 수행함



**Container Management**

컨테이너 기반 어플리케이션 운영이 유연성 & 자율성을 가짐. 쿠버네티스가 대표적 컨테이너 매니지먼트.



**Backing Service**

어플리케이션이 실행되는 가운데 네트워크를 통해 사용할 수 있는 모든 서비스를 말하고, db, 캐쉬 시스템, smtp서비스 등 어플리케이션과 통신하는 리소스들을 생각할 수 있음 

message queue 가 특징적인 서비스 중 하나.

msa에서 메세지는 송신자와 수신자가 직접 송신하지 않고, message queue를 활용해 비동기 적으로 통신하는것을 지향함.

ex) 

1. 프로젝트 내에 장애 발생이 일아남 -> 서비스 오케스트레이션이 진행되 새로운 서비스 컨테이너를 신규 생성하거나 재생성 하는 작업을 진행함 
2. 메세지 큐를 사용하지 않는다면(강한결합), 1의 상황에서 트랜잭션이 끊어져 요청서비스를 보존할 수 없음. -> 에러발생 & 실패 처리 어려움
3. 2의 이유로 인해, 메세지큐를 활용한 비동기 처리 효율적



**Telemetry**

먼거리(tele) + 측정(metry). 마이크로서비스가 분산환경에서 운영되기 때문에 상태를 일일이 모니터링& 이슈대응 하는것이 어렵다. 

서비스 모니터링, 서비스별로 이슈대응 하도록 환경 구성하는 역할



**CI/CD Automation**

지석적 통합, 지속적 전달, 지속적 배포로 msa의 배포 자동화를 해. 잦은 배포를 커버하기

[https://velog.io/@tedigom/MSA-%EC%A0%9C%EB%8C%80%EB%A1%9C-%EC%9D%B4%ED%95%B4%ED%95%98%EA%B8%B0-1-MSA%EC%9D%98-%EA%B8%B0%EB%B3%B8-%EA%B0%9C%EB%85%90-3sk28yrv0e](https://velog.io/@tedigom/MSA-제대로-이해하기-1-MSA의-기본-개념-3sk28yrv0e)