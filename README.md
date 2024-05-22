# Today I Learned(TIL)
## 05/21

## [AWS]
### 클라우드 컴퓨팅
인터넷을 사용해서 공유자원(서버, 네트워크, 스토리지)을 사용할 수 있는 서비스이다.

데이터센터안에 네트워크장비가 있어서 우리가 장비들을 쓸 수가 있는 건데,
인터넷을 연결하면 라우터를 포함한 모든 네트워크장비를 쓸 수 있다.

또한 원래 우분투, 리눅스, 아마존을 쓰려면 가상머신을 깔아야 한다. 그러려면 용량이 큰 컴퓨터를 사야 하는데 클라우드 컴퓨팅은 이러한 모든 작업을 서비스 형태로 제공한다. 오직 인터넷에서 제공하는 서비스를 호출하여 즉시 필요한 자원을 사용할수 있다.

#### 클라우드의 특징
- 한 화면에 운영체제를 여러 개 띄워서 사용 할 수 있다.

#### 클라우드의 종류
- Amazon AWS
- Microsoft Azure
- Google Cloud Platform

### On demand 서비스와 SLA
> On demand

클라우드 서비스 사용자가 요청한 만큼 서비스를 제공하고 비용을 청구하는 모델이다.

대용량 서버중에서 요청한 만큼의 서버만을 사용자에게 제공하기 때문에 해당 서버의 자원을 분할, 할당할 수 있는 방법이 있어야한다.

즉, 가상화 기술이 필요하다.


> SLA(Service Level Agreement)

On demand 서비스 사용할 때 클라우드 컴퓨팅 서비스 사용자와 서비스 제공자(AWS) 간에 서비스 수준에 대한 협약서.  
즉, SLA를 통해서 사용한 서비스만큼 비용을 지불하게 된다.

### 가상화
하드웨어를 분할하거나 할당할 수 있어서  
한 대의 서버를 여러 서비스 사용자가 물리적으로 같이 사용할 수 있다.   
(한대의 고성능 컴퓨터를 분할하여 여러명이 쓸 수 있다.)       

또한 여러개의 물리적 자원을 통합하여 하나의 컴퓨터처럼 사용할 수 있다.  
(마치 한대의 고성능 컴퓨터를 사용하는 것처럼 여러개의 물리적 서버를 통합한다.)

> Host Os와 Guest OS

#### Host Os

하드웨어 위에 설치된 운영체제를 의미.

#### Guest OS

호스트 가상화 혹은 하이퍼바이저 위에 설치된 운영 체제. (리눅스, 윈도우 등)

> 가상화 종류

|구분 |특징|
|:----|:----:|
| 호스트 가상화  |  Host Os 위에 Guest OS가 실행되는 방식.(VMServer, Virtual Box, VM Workstation 등)  |
| 하이퍼바이저  |  Host Os가 없음. 하이퍼바이저 위에 Guest OS. (Xen, Microsoft Hyper-V, Citrix, KVM 등)  |
| 컨테이너 가상화 |  Host OS 위에 컨테이너 관리 소프트웨어를 설치하여 논리적인 컨테이너를 나누어서 사용한다. (Docker) |  



> 하이퍼 바이저(Hyper Visor)

하드웨어 위에 별도의 Host OS를 설치하지 않고 하이퍼바이저라는 가상화 소프트웨어를 설치한다. 그리고 하이퍼바이저 위에 Guest OS를 설치하는 구조.

> 하이퍼바이저 가상화의 종류

|수준 |Type-1(Native, Bare metal) |Type-2(Hosted)|
|:----|:----|:----:|
|네번째|   |  GuestOS  |
|세번째|GuestOS   |  하이퍼바이저  | 
|두번째|하이퍼바이저|HostOS| 
|첫번째|하드웨어   |  하드웨어  | 

> 하이퍼바이저 가상화의 장단점

- 장점 :  Host OS가 없기 때문에 오버헤드가 적다. 

  ( 오버헤드 : 처리를 하기위해 들어가는 간접적 처리시간/메모리 )
- 단점 : 자체적으로 머신에 대한 관리 기능이 없기 때문에 관리를 위한 컴퓨터 혹은 콘솔이 필요.


### On-Premise
서버, 데이터베이스, 네트워크 등의 장비를 모두 구매후, 구축하고 운영하는 서비스.
일반적으로 IDC에 서버를 설치하고 전용 네트워크를 통해서 운영하는 시스템 형태.

> IDC(Internet Data Center)

- 서버랙 : 랙은 서버를 설치하는 장치를 의미.
- 케이블 타워 : 각종 서버에 케이블 연결하여 통신, 케이블은 케이블 타워에 설치.
- 항온항습기 : 온도 습도 조절


### 클라우드 컴퓨팅 종류
서비스를 제공하는 방식에 따라 분류함.
- Private Cloud : 기업 내부에서 기업 조직원들을 위한 서비스 제공. 
- Public Cloud : 인터넷을 사용해서 제공하는 클라우드 컴퓨팅. (AWS, AZURE 등)
- Hybrid Cloud : private Cloud, Public Cloud 모두 제공.

### 클라우드 컴퓨팅 모델

#### 1. IaaS(Infrastrucure as a Service)
- 인프라를 서비스 형태로 제공. *서버, 스토리지, 네트워크 관련* 각종 *물리적 장비*를 서비스 형태로 제공.
- AWS에서 EC2, S3, VPC 등의 서비스가 해당된다.
#### 2. PaaS(Platform as a Service)
- 인프라에 설치되는 *운영체제, 미들웨어, 데이터베이스 관리 시스템* 등의 *소프트웨어*를 제공.
- AWS에서 리눅스 및 윈도 운영체제, Oracle, MySQL 등의 DBMS를 제공하는 것.
#### 3. SaaS(Software as a Service)
- *응용 프로그램*(구글 Office 365, 드롭박스 등)을 서비스 형태로 제공.


## [spring boot]

### AdminUserController에서 User 객체를 이용해 멤버를 하나하나 복사해 와서 adminUser를 통해 전체 조회하는 예제를 실행해봄.

여기서 MappingJacksonValue 클래스가 어떤건지에 대해서 궁금해져서 알아보았다.

> MappingJacksonValue란?

MappingJacksonValue는 JSON Serialization(직렬화)을 처리하는 데 사용되며, 주로 Spring MVC(혹은 Spring  WebFlux) 기반의 웹 애플리케이션에서 Java 객체를 JSON으로 변환하거나, 반대로 JSON 데이터를 Java 객체로 변환하는 데 매우 효율적이고 강력한 라이브러리. 
 
일반적으로 컨트롤러 메서드에서 반환되는 데이터를 래핑하는데 사용되며, 이를 통해 특정 필터링 기능이나 시리얼라이제이션(Serialization) 설정을 적용하여 응답 데이터를 제어할 수 있습니다.


즉, 특정 사용자나 상황에 따라 다른 응답을 제공할 때 유용한 것이다. 
예제에서 보면 AdminUser 클래스의 "id", "name", "joinDate", "ssn"가 응답되도록 필터링을 했다.

이와 같이 하기 위해서는 AdminUser 클래스에 @JsonFilter("myDataFilter")와 같이 등록되어야 한다.

### Version 관리
- 실제 api를 쓰는것 처럼 버전을 만들어서 버전에 따른 출력값을 확인해 보았다.
- 첫번째는 URI를 통한 버전관리이다.
```python
@GetMapping("/v1/users/{id}")
```
- 두번째는 Request prarmeter 버전관리이다. 
```python
@GetMapping(value = "/users/{id}", params = "version=1")
```
params에 버전이름을 적어두면 된다.

호출은 다음과 같이 한다.
```
http://localhost:8088/admin/users/2?version=2
```
- 세번째는 headers 버전관리이다.
```python
@GetMapping(value = "/users/{id}", headers = "X-API-VERSION=1")
```
여기서부터는 URI를 통한 접근이 불가능하고, POSTMAN에 있는 header 기능을 이용하여 호출한다.
- 네번째는 mime-type 버전관리이다.
```python
@GetMapping(value = "/users/{id}", produces = "application/vnd.company.appv1+json")
```
> mime-type이란 : 특정한 파일이나 데이터가 어떤 유형인지 알려주는 형식

### 정리
(일반 브라우저에서 실행가능)

		1. URI를 통한 버전관리		(예시 사이트 : x)
		2. Request 파라미터 버전관리	(예시 사이트 : Amazon)

		(일반 브라우저에서 실행불가) - 직접프로그래밍 개발 or postman이용
		3. headers 버전관리		(예시 사이트 : Microsoft)
		4. mime-type 버전관리		(예시 사이트 : GitHub)

### 버전관리를 하면서 주의할점
        	1. uri를 통해 정보를 너무 과도하게 표기하지 말자.
		2. 잘못된 헤더값 사용 주의
		3. 인터넷 웹브라우저 캐시문제가 생길 수 있으니 캐시를 삭제해보고 다시 해보자


### Level3 단계의 REST API 구현을 위한 HATEOAS 적용

> HATEOAS란 : 현재 리소스와 연관된(호출 가능한) 자원 상태 정보를 제공해준다.

API를 설계 할 때는 RMM에서 말하는 레벨단계를 따라 API를 업데이트 할 수 있다.
```
	LEVEL 0
	LEVEL 1 : 리소스화 할 수 있는 단계, 리소스가 제공되고 있는 단계
	LEVEL 2 : HTTP에 필요한 상태코드, 메소드를 이용해서 리소스를 제공하는 단계   ( 사용자 관리, RESTFUL 지금까지 작업한 단계랑 같다고 보면 된다. )
	LEVEL 3 : HATEOAS 기능이 추가 / 연결되어 있는 단계 Hypermedia를 통해서 우리가 제공하고자 하는 리소스를 제어 하는 단계
```

HATEOAS를 사용하기 위해서는 pom.xml에 

```
    	<dependency>
		<groupId>org.springframework.boot</groupId>
		<artifactId>spring-boot-starter-hateoas</artifactId>
	</dependency>
```
를 추가 해 주면 된다.





## 05/22
### AWS(Amazon Web Service)
컴퓨팅, 네트워킹, 스토리지, 분석 플랫폼 등 다양한 서비스를 제공.

> 컴퓨팅 서비스

- Amazon EC2 : 다양한 타입의 가상화 서버(Windows, Linux, Aurora)를 지원.
- Amazon Auto Scaling : 사용량에 따른 자동 서버 추가 삭제
- Amazon Lightsail : VPS(Virtual Private Server)는 웹사이트 및 웹 어플리케이션을 배포하거나 관리.
- Amazon Workspace : 데스크톱 가상화 서비스. (사내PC는 가상화), (개인 PC는 문서를 서버에 보관. 저장x)

> 네트워킹 서비스

|서비스 |설명|
|:----|:----:|
| Amazon Route 53  |  클라우드 기반의 DNS(Domain Name System)  |
| Amazon VPN  |  가상 사설 네트워크를 구성(DHCP, VPN 사용)  |
| AWS Direct Connect | AWS를 연결하기 위해서 전용선을 구성하는 것. (AWS-ON-Premise를 연결)  |  
| Amazon ELB(Elastic Load Balancer) | 네트워크 부하를 분산하기 위해서 L4 스위치 역할  | 

- L4스위치 : 서버가 점점 늘어나다보면 네트워크에 부하가 가게 된다. 이때 필요한 것이 로드밸런싱(서버 부하 분산)이다. 외부에서 들어오는 모든 요청을 서버가 아닌 L4 스위치가 받아 서버들에게 적절히 나누어 준다.


> 스토리지 서비스

|서비스 |설명|
|:----|:----:|
| Amazon S3  |  클라우드 기반의 DNS(Domain Name System)  |
| Amazon DynamoDB  |  NoSQL 서비스로 대용량의 데이터를 저장,분석  |
| Amazon ElasticCache | In-memory 기반의 Cache 서비스.  | 

> 분석 플랫폼

|서비스 |설명|
|:----|:----:|
| Amazon S3  |  클라우드 기반의 DNS(Domain Name System)  |
| Amazon DynamoDB  |  NoSQL 서비스로 대용량의 데이터를 저장,분석  |
| Amazon ElasticCache | In-memory 기반의 Cache 서비스.  | 

> AWS CloudWatch 서비스

자원과 성능을 모니터링하고 통지하는 서비스

### AWS 장점
1. 사업 초기 투자비용이 발생하지 않는다.
	- 사업을 하기 위해서 정보시스템이 필요.
	- 정보시스템 구축을 위해서 시설이 필요
	- 하지만 AWS는 이 모든 시설을 구축해서 제공하고 있음
	- 따라서 *인건비, 운영비용 감소효과*
2. 탄력적 확장이 가능하다. -> 속도, 민첩성
	- 저렴한 서버를 구매함.
	- 사용자가 폭증.
	- 다시 서버를 구매해야함.
	- 하지만 AWS는 서비스 형태로 제공되므로 바로 확장 가능.
	- -> 사용자는 본인 사업에 집중할 수 있다.
3. 전 세계로 확장이 가능.


## [GCP]

### 클라우드란

- On-Premises : ( 집을 지을때 자재부터 직접 사서 지음 )하드웨어부터 애플리케이션, 확장까지 모든것을 직접 설치해 구동시키는것. 

- IaaS : ( 깡통 집은 지어줌 )운영체제, 런타임, 확장 등에 대해서는 사용자가 직접 관리해야함.
- CaaS : ( 집을 임대한다. + 기본적인 설비 but 가구는 없다 ) 컨테이너 화된 어플리케이션은 설치가능 but 확장과 런타임에 대해서는 관리가 필요.
- PaaS : ( 가구까지 제공하는 집 임대 ) 자체 코드를 가져와 배포하지만 확장은 공급자에게 맡길 수 있다.

- FaaS : ( 사무실 임대 ) 함수 또는 코드 일부를 배포, 해당 함수 실행될 때마다 클라우드 공급자는 필요에 따라 규모를 확장

- SaaS : ( 청소나 잔디 유지비용 지불 ) 비용을 지불하면 업체가 데이터를 관리 해 준다.

### Compute Engine
맞춤형 컴퓨팅 서비스, 일반 사용자가 구글 인프라 상에서 가상 머신(VM)을 구동 할 수 있다.

1. 사전 정의된 머신 유형(predefined machine type)
	- vCPU와 메모리를 가진 VM구성
	- 사전에 생성돼 빠르게 사용할 수 있다.
2. 사용자 정의형 머신 유형(custom machine type)
	- 작업 부하에 따라 최적의 CPU와 메모리를 가진 vm 생성가능
	- 작업 부하에 맞게 인프라 조정
	- 요구사항 변경 -> 더 작거나 큰 머신 유형 인스턴스 또는 사전에 정의된 구성으로 작업 이전 가능.

### 머신유형
작업 부하에 따라 제품군으로 분류됨.

1. 일반목적
	- 비용이 저렴 -> 일상적 컴퓨팅
	- 균형잡힌 가격과 성능

2. 컴퓨팅 최적화
	- *최고성능*을 요구하는 작업에 권장
	- 게임, 비디오, 전자 설계 등
3. 메모리 최적화
	- 큰 메모리 작업, 내장 메모리 분석에 권장
4. 가속기 최적화
	- 고성능 요구 작업
	- 대규모 계산, 머신러닝

### 작동방식






## [spring boot]
### Swagger Documentation 구현
|Swagger 3 annotations |Description|
|:----|:----:|
| @Tag  |  클래스에 설명, Swagger 리소스  |
| @Parameter  |  API 에서의 단일 매개 변수  |
| @Parameters | API 에서의 복수 매개 변수  | 
| @Schema | Swagger모델에 대한 추가 정보  | 
| @Operation(summary="",description="") | 특정 경로에 대한 작업   | 
| @ApiResponse(responseCoded="404",description="") | API에서의 작업 처리에 대한 응답코드 설명  | 