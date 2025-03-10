## 가상화(Virtualization) 개념과 중요성

- 이 챕터에서는 다음과 같은 내용을 다룰 것이다.
1. 가상화란 무엇인가?
2. 물리적 머신의 한계
3. 가상 머신(Virtual Machine)의 개념과 장점
4. 가상화의 다양한 형태

## 1. 가상화란 무엇인가?
- 우리는 일상에서 노트북, 스마트폰과 같은 물리적 장치(Physical Machines)를 사용한다. 서버(Server) 역시 물리적 컴퓨터의 한 종류로, 네트워크를 통해 클라이언트(Client)에게 서비스를 제공하는 역할을 한다.
- 하지만, 물리적 머신만으로 다양한 요구를 처리하기에는 몇 가지 한계가 있다. 이를 해결하기 위해 등장한 개념이 바로 **가상화(Virtualization)** 이다.
- 가상화는 **컴퓨터 시스템을 논리적으로 분리하여 여러 개의 가상환경을 만드는 기술** 이다. 가장 대표적인 형태가 **가상머신(Virtual Machine,VM)** 이다.

## 2. 물리적 머신의 한계
- 물리적 컴퓨터는 다음과 같은 한계가 존재한다.
  - `비용 문제` : 더 많은 작업을 처리하려면 추가적인 하드웨어를 구매해야 하며, 유지보수 비용도 증가하게 된다.
  - `관리의 복잡성` : 여러 대의 물리적 서버를 유지하려면 업데이트와 수리 과정에서 많은 시간이 소요될 수 있다.
  - `확장성 부족` : 성능을 업그레이드하려면 기존의 하드웨어를 교체해야 하며, 이는 비용과 시간이 많이 드는 작업이다.

이러한 문제들을 해결하기 위해 **가상화 기술** 이 도입되었다.

## 3. 가상머신(Virtual Machine, VM) 이란?
- 가상머신(VM)은 **하나의 물리적 컴퓨터** 안에서 **독립적으로 운영**되는 **가상의 컴퓨터 시스템**이다.
- 즉, **하나의 호스트(Host) 머신에서 여러 개의 가상 머신을 실행**할 수 있으며, 각 VM은 **자체 운영체제(OS)와 애플리케이션을 갖출 수 있다.**
- 가상 머신은 각각 독립적으로 실행되며 서로 간섭하지 않는다. 따라서, 물리적 하드웨어를 추가하지 않고도 여러 개의 시스템을 운영할 수가 있다.

### 가상 머신의 장점
- `자원 활용 극대화` : **여러 개의 가상 머신을 하나의 물리적 서버에서 운영**할 수 있어 **비용을 절감하고 자원을 효율적으로 사용**할 수 있다.
- `유연한 확장성` : 하드웨어를 직접 교체하지 않아고, **필요할 때 VM 의 리소스를 조정**할 수 있다.
- `보안성 향상` : **VM 간의 격리**가 이루어지므로, 한 VM에서 발생한 보안 문제가 다른 VM 으로 확산되지 않는다.
- `운영체제(OS) 다양성` : 하나의 물리적 머신에서 Window,Linux,macOS 등 서로 다른 OS를 동시에 실행할 수 있다.

## 4. 가상화(Virtualization)의 다양한 형태
- 가상화에는 다양한 수준(Level)이 있다.
- `전체 가상화(Full Virtualization)` : **하드웨어와 소프트웨어를 모두 가상화**하여 완전한 가상머신(VM) 을 생성하는 방식이다.
- `운영체제 가상화(OS Virtualization)` : **하나의 운영체제 내에서 독립적인 실행환경**을 제공하는 방식이다.(**컨테이너 기술과 관련**)
- `스토리지 가상화(Storage Virtualization)` : **여러 개의 물리적 스토리지를 하나의 논리적 스토리지로 통합**하는 방식이다.

이처럼 **가상화** 는 단지 **VM을 생성하는 것뿐만 아니라 다양한 IT 인프라에서 활용될 수 있는 중요한 기술** 이다.

<hr>
<hr>

## 컨테이너화(Containerization)의 개념과 중요성
- 이전 챕터에서는 가상화(Virtualization)에 대해 배웠다면, 이번에는 컨테이너화(Containerization)에 대해 알아보자.
- **컨테이너화는 운영체제 수준의 가상화**(Operating System-Level Virtualization)로, 현대 애플리케이션 배포 방식에서 중요한 역할을 한다.
- 이 챕터에서는 다음과 같은 내용을 다룰 것이다.
1. 컨테이너화란 무엇인가?
2. 컴퓨팅 환경(Environment)이란?
3. 운영체제(OS) 수준의 가상화
4. 컨테이너(Container) 개념과 특징
5. 컨테이너의 장점
6. 컨테이너 vs 가상머신 비교

## 1. 컨테이너화란 무엇인가?
- 가상화는 하드웨어, 소프트웨어 등 다양한 요소를 가상화할 수 있다. **컨테이너화(Containerization)는 가상화의 한 형태**로, **운영체제 수준(OS-Level)에서 이루어지는 가상화 기술**이다.
- 컨테이너화를 통해 **하나의 운영체제(OS) 내에서 독립적인 실행환경을 생성**할 수 있다.
- 즉, 개별 애플리케이션이 필요한 소스코드, 라이브러리, 종속성(Dependencies)등을 포함한 환경을 갖춘 컨테이너에서 실행된다.

## 2. 컴퓨팅 환경(Environment)이란?
- 컨테이너화를 이해하려면 먼저 **환경(Environment)**개념을 정리해야 한다.
- 컴퓨팅 환경이란, **애플리케이션이 실행되는 시스템**을 의미하며, 다음 요소로 구성된다.
  - 운영체제(OS, Operating System)
  - 하드웨어(Hardware)
  - 소프트웨어(Software)
  - 기타 필요한 리소스(Resources)
- 컨테이너는 이러한 환경을 **애플리케이션별로 독립적으로 구성**하는 방식이다.

## 3. 운영체제(OS) 수준의 가상화

![image](https://github.com/user-attachments/assets/b06fa407-4cd9-488d-8f51-a563ccf3fcee)

- 컨테이너화는 **운영체제 자체를 가상화하는 방식** 으로, 기존의 전체 가상화(Full Virtualization)와 차별화된다.
  - 기존 가상화(`VM`) : **하드웨어를 가상화**하여 **여러 개의 독립적인 운영체제**를 실행
  - 운영체제 수준의 가상화(`컨테이너`) : **하나의 운영체제(OS) 내에서 독립적인 실행 공간**을 생성
- 즉, 컨테이너화는 **운영체제 커널(Kernel) 을 공유** 하면서 애플리케이션 실행을 위한 가상 환경을 제공한다.

* Kernel(커널)이란? : 운영체제의 핵심 부분으로, 하드웨어와 소프트웨어 간의 **상호 작용** 을 담당하는 역할을 한다.

## 4. 컨테이너(Container)란?

![image](https://github.com/user-attachments/assets/dd9d98af-9ab8-4bb3-8ea7-ca7ea37c4dc7)

- **컨테이너(Container)는 운영체제 수준의 가상화된 환경**을 의미하며, **각 애플리케이션을 독립적으로 실행할 수 있도록 격리된 공간**을 제공한다.
- 컨테이너 내부에는 다음과 같은 요소가 포함된다.
  - 애플리케이션 코드
  - 필요한 라이브러리 및 종속성(Dependencies)
  - 환경 설정(Configuration)
- 컨테이너는 마치 하나의 작은 독립적인 컴퓨터처럼 동작하며, **같은 운영체제 내에서 서로 격리된 상태로 실행**된다.

```
- The definition of containerization is twofold
- First, containerization is virtualization at the OS-level.
- Second, containerization is the process of packaging an application and its dependencies into a container.
```

## 컨테이너의 특징과 장점

![image](https://github.com/user-attachments/assets/da6489d3-3249-45ea-87c5-b9429883f0d0)

- 컨테이너 기술은 기존의 물리적 머신이나 가상 머신보다 다양한 이점을 제공한다.

### 1. 애플리케이션 간 독립성(Isolation)
- 각 컨테이너는 자체적인 실행 환경을 가지고 있어, 다른 컨테이너의 실행에 영향을 주지 않는다.
- 예를 들어, 한 컨테이너에서 문제가 발생하더라도 다른 컨테이너에 영향을 주지 않는다.

### 2. 빠른 배포 및 확장성(Scalabilty)
- 컨테이너는 가볍고 빠르게 실행된다.
- VM처럼 운영체제 전체를 실행할 필요가 없으며, **필요한 부분만 로드하여 즉시 실행**이 가능하다.

### 3. 높은 이식성(Portability)
- 컨테이너는 **어느 환경에서나 동일하게 동작**한다.
- 예를 들어, 로컬 개발 환경에서 만든 컨테이너를 **클라우드, 서버, 다른 개발자의 컴퓨터** 에서도 동일하게 실행할 수 있다.

### 4. 자원 효율성(Resource Efficiency)
- 가상 머신(VM)은 각 OS 를 실행해야 하므로 리소스를 많이 사용한다.
- 반면, 컨테이너는 **운영체제 커널을 공유** 하므로 적은 리소스로 더 많은 애플리케이션 실행이 가능하다.

## 컨테이너 vs 가상머신(VM) 비교

![image](https://github.com/user-attachments/assets/994b89af-bce6-4983-92f2-7490d5fa381f)

- 컨테이너 기술의 대표적인 예로 `Docker` 와 `Kubernetes` 가 있다.
- `Docker` 는 개별 컨테이너를 생성하고 실행하는 도구
- `Kubernetes` 는 여러개의 컨테이너를 효율적으로 관리하는 오케스트레이션 도구

<hr>
<hr>

## 가상화(Virtualization)와 컨테이너화(Containerization) 비교
- 이번 챕터에서는 가상화와 컨테이너화의 차이점을 비교하고 각각의 사용사례와 장점을 살펴보자.

## 1. 가상화 vs 컨테이너화 : 개념 비교

### 가상화(Virtualizatino)란?
- `가상화`는 `컴퓨터 자원을 가상환경에서 실행할 수 있도록 하는 기술`이다.
- `가상화`를 통해 **하나의 물리적 머신에서 가상 머신(Virtual Machine,VM) 을 생성**하여 **독립적인 운영체제**와 **애플리케이션을 실행**할 수 있다.

### 컨테이너화(Containerization)란?
- `컨테이너화`는 `운영체제(OS) 수준에서 가상화`를 수행하는 기술이다.
- **애플리케이션과 필요한 라이브러리 및 종속성을 컨테이너(Container) 라는 독립된 환경에 패키징**하여 실행할 수 있도록 한다.

### 차이점 요약

![image](https://github.com/user-attachments/assets/60fd14cb-72ca-4f0b-afa2-87f0391301ce)

## 2. 컨테이너화의 주요 소프트웨어
- 컨테이너 기술을 활용하려면 적절한 도구를 사용해야 한다.
- `Docker` : `컨테이너를 생성, 실행 및 배포` 하는 가장 대표적인 플랫폼이다.
- `Kubernetes` : `여러 개의 컨테이너를 자동으로 관리`하고 `배포, 확장, 조정 하는 오케스트레이션 도구`이다.
- `Kubernetes` 는 `컨테이너 여러 개를 동시에 관리`하는 역할을 한다.
  
## 3. 가상화의 주요 소프트웨어
- 가상화를 지원하는 대표적인 소프트웨어로는 다음과 같은 것들이 있다.
- `Oracle VM VirtualBox` : 오픈소스 기반의 가상 머신 관리 소프트웨어
- `VMware` : 기업 환경에서 많이 사용되는 가상 머신 관리 소프트웨어
- 이러한 도구를 활용하면 여러 개의 가상 머신을 생성하고 관리할 수 있다.

## 4. `가상화` 의 활용사례

### 서버 자원 최적화
- 하나의 물리적 서버에서 `여러 개의 가상 머신을 실행`하여 **서버 자원을 효율적으로 활용** 할 수 있다.

### 레거시 시스템 유지
- 기업에서는 기존의 레거시(구형) 소프트웨어를 유지해야 하는 경우가 많다.
- 가상화를 사용하면 `오래된 운영체제와 소프트웨어를 최신 하드웨어에서도 실행` 할 수 있다.

## 5. `컨테이너화` 의 활용 사례

### 애플리케이션 격리 및 배포
- 컨테이너는 **애플리케이션과 그 필요한 환경을 독립적으로 패키징** 하여 배포가 쉽다.

### 마이크로서비스 아키텍처(Microservices)
- `컨테이너`는 **`마이크로서비스 아키텍처`** 를 구현하는 데 최적화된 기술이다.
- 애플리케이션을 `여러 개의 작은 서비스로 나누고`, 각 서비스를 **`독립적인 컨테이너에서 실행`** 할 수 있다.
- 이를 통해 **유연한 배포 및 확장이 가능** 하며, 각 서비스에 **다른 기술 스택을 적용** 할 수도 있다.

## 6. 컨테이너 오케스트레이션(Orchestration)
- `컨테이너 오케스트레이션`이란 `여러 개의 컨테이너를 자동으로 배포, 확장, 조정`하는 기술이다.
- 이를 쉽게 이해하기 위해 오케스트라를 떠올려 보면 된다.
  - `컨테이너 오케스트레이션` = `오케스트라 지휘자`
  - 컨테이너 각각이 `개별 연주자` 라면, `Kubernetes` 는 이들을 조율하는 `지휘자 역할`을 한다.
- 즉, `Kubernetes` 는`컨테이너들을 체계적으로 관리`하여 애플리케이션이 원활하게 실행될 수 있도록 한다.

## 7. 컨테이너 vs 가상 머신 : 장점 비교

![image](https://github.com/user-attachments/assets/1edd9fd8-a510-4ebf-8078-d6496b12e6ec)

<보안>
- `VM` 은 `전체 하드웨어를 에뮬레이션`하기 때문에 호스트 OS 커널을 다른 컨테이너와 공유하는 컨테이너화보다 `더 강력하고 안전한 격리를 제공`한다.
- 공격이 발생하는 경우 `호스트 OS 커널`에 엑세스하면 해당 호스트의 모든 컨테이너에 액세스하게 된다.(컨테이너는 동일한 운영 체제를 공유하므로)

<공간, 이식성, 확장성>
- `VM`보다 `컨테이너`가 공간을 덜 차지하기 때문에 사용하면 오버헤드 비용을 낮출수 있따.
- `컨테이너` 는 가볍기 때문에 `가상 머신` 보다 이식성과 확장성이 더 뛰어나다.

- 반면, `VM`은 여러 운영체제를 실행할 수 있는 유연성을 제공한다.
- `VM`은 동일한 호스트 시스템에 시스템을 설치하고 최신 하드웨어에서 레거시 애플리케이션도 지원한다.

결론적으로 **가상 머신과 컨테이너는 각각 장점과 단점이 다르므로, 사용 목적에 맞춰 선택**해야 한다.
- 보안이 중요한 경우 or 레거시 시스템을 그대로 쓰고 싶은 경우 -> `가상머신(VM)`
- 빠른 배포와 확장이 필요한 경우 -> `컨테이너(Container)`

<hr>
<hr>

## 컨테이너화(Containerization)와 도커(Docker)의 개념
- 이전 챕터에서는 컨테이너화(Containerization)의 개념을 더욱 깊이 이해하고, 이를 가능하게 해주는 가장 대표적인 도구인 Docker 에 대해 살펴보자.

## 1. 컨테이너(Container)란?
- 컨테이너는 애플레케이션 실행하기 위한 독립적인 환경을 제공한다.
- 컨테이너에는 애플리케이션이 정상적으로 실행도기 위해 필요한 `소스코드`,`라이브러리`,`종속성(Depenecies)`, `설정(Configuration)` 등이 포함된다.

## 2. Docker란?
- `Docker`는 컨테이너화(Containerization)를 쉽게 구현할 수 있도록 도와주는 `오픈 소스 플랫폼`이다.
- `오픈 소스(Open-source)`란 `누구나 자유롭게 사용, 수정, 배포할 수 있는 소프트웨어`를 의미한다.
- `Docker`가 인기 있는 이유
  - `컨테이너 기술을 표준화`하여 `누구나 쉽게 사용할 수 있도록` 한다.
  - `설치와 실행이 간편`하며, `개발 환경`과 `배포환경을 일치`시키는 데 유용하다.
  - `Stack Overflow` 개발자 설문조사에서 가장 많이 사용되는 기술 중 하나로 선정된다.

## 3. `Docker`의 핵심 역할

![image](https://github.com/user-attachments/assets/1c2b7274-90eb-45a9-abf2-aa288ca430ba)

- Docker는 `컨테이너 생성(Build)`, `배포(Distribute)`, `실행(Run) 및 관리(Manage)` 를 돕는 도구이다.
- 즉, `컨테이너 라이프사이클을 관리하는 소프트웨어 플랫폼`이라고 할 수 있다.

## 4. Docker의 주요 구성 요소
- Docker의 아키텍처를 구성하는 중요한 요소들을 살펴보자.

- Docker Desktop
- Docker Engine
  - Docker Client
  - Docker Daemon
- Docker Objects
  - Docker Images
  - Docker Containers
- Docker Registries

| 구성요소        |       설명    |
|---------------|-------------|
|Docker Desktop|Mac, Linux, Windows 에서 Docker 를 실행할 수 있는 **GUI(그래픽 사용자 인터페이스)** 제공|
|Docker Engine|Docker의 핵심 엔진으로, **컨테이너를 실행하는 서버**|
|Docker CLI| **터미널(Command Line Interface)을 통해 Docker 명령어를 실행**할 수 있는 도구|
|Docker Daemon| 컨테이너 실행, 이미지 빌드 등 **핵심 작업을 처리하는 백그라운드 프로세스**|
|Docker 이미지(Image)| **컨테이너를 실행하기 위한 설정** 및 **파일이 포함된 불변(immutable) 템플릿**|
|Docker 컨테이너(Container) | Docker 이미지 기반으로 실행되는 **독립적인 환경**|
|Docker 레지스트리(Registry) | Docker **이미지를 저장하고 공유하는 공간**(ex.Docker Hub)|

## 5. Docker 설치 및 실행
- Docker를 사용하려면 먼저 **Docker Desktop 을 설치**해야 한다.
- `Docker Desktop`은 Mac, Linux, Windows 에서 사용할 수 있으며, **GUI 환경**을 통해 컨테이너와 이미지를 쉽게 관리할 수 있다.
- 또한, `Docker Desktop` 에는 `Docker Engine` 이 포함되어 있어 `명령줄 인터페이스(CLI)` 또는 `GUI` 를 이용해 `컨테이너를 실행`할 수 있다.

## 6. `Docker` 의 클라이언트-서버 아키텍처

![image](https://github.com/user-attachments/assets/edd8a474-0000-4245-b44f-d485e28aadaa)

- `Docker`는 `클라이언트-서버(Client-Server) 아키텍처`를 따른다.
  - `Docker Client`(사용자 측) : **사용자가 Docker 명령어를 입력하는 인터페이스**(CLI 또는 Docker Desktop) 
  - `Docker Daemon`(서버 측) : 클라이언트 요청이 수신된다. Docker의 핵심 서비스로, **컨테이너를 실행하고 관리하는 역할을 담당**한다. Docker를 사용할 때마다 실행되어야 한다.
- 즉, **사용자는 `CLI` 또는 `GUI` 를 통해 명령을 입력**하면, **`Docker Daemon` 이 이를 받아 실행하는 방식**으로 동작한다.

## 7. `Docker` 오브젝트 개요
- Docker에서 다루는 주요 오브젝트는 다음과 같다.

![image](https://github.com/user-attachments/assets/335cc654-1b44-4693-8fca-b7a230a2e2fd)

### Docker 이미지 (Image)
- 컨테이너 실행을 위한 불변(Immutable) 템플릿
- 애플리케이션 코드, 라이브러리, 실행 환경 등이 포함된다.
- 하나의 이미지를 기반으로 여러 개의 컨테이너 생성 가능하다.

### Docker 컨테이너 (Container)
- Docker 이미지로부터 생성되는 실행 가능한 환경
- 격리된 상태에서 애플리케이션 실행 가능
- 필요할 때 빠르게 생성, 실행, 삭제 가능

### Dockerfile : 이미지 생성의 기본
- `Docker Image`는 `Dockerfile 이라는 설정 파일을 기반`으로 생성된다.
- `Dockerfile` 은 `컨테이너를 빌드하는 설정 스크립트(Recipe) 역할`을 한다.
- 즉, `Dockerfile` 을 사용하여 컨테이너에 대한 청사진을 구축하는데, 이 청사진을 `DockerImage` 라고 하는 것이다.

(ex)
```dockerfile
FROM python:3.8  # Python 3.8 환경을 사용
COPY . /app      # 현재 폴더의 파일을 컨테이너 내부로 복사
WORKDIR /app     # 작업 디렉토리 설정
RUN pip install -r requirements.txt  # 필요한 패키지 설치
CMD ["python", "app.py"]  # 컨테이너 실행 시 실행할 명령어
```

### 아날로지(비유)로 이해하는 Docker 이미지 & 컨테이너
- `Dockerfile` : 집을 짓기 위한 설계도(Recipe)
- `Docker 이미지` : 설계도를 기반으로 만들어진 집 모델(House Model)
- `Docker 컨테이너` : 실제로 지어진 완성진 집(Instance of House)
즉, 같은 `Docker 이미지` 를 기반으로 `여러 개의 컨테이너`를 실행할 수 있다.

## 8. Docker 이미지 공유 : Docker 레지스트리

![image](https://github.com/user-attachments/assets/8cedae30-d2a4-4bba-92be-91218bf51b30)

- `Docker에서는 생성한 이미지`를 `Docker 레지스트리(Docker Registry)에 저장하고 공유`할 수 있다.
  - `Docker Hub` : 가장 널리 사용되는 퍼블릭(public) Docker 레지스트리
  - `Private Registry` : 기업 내부에서 사용되는 프라이빗(private) 레지스트리
- 개발자는 `Docker Hub` 또는 `자체 레지스트리`를 활용하여 `이미지를 쉽게 공유하고 배포`할 수 있다.

## 9. 컨테이너 vs 가상 머신 : Docker의 장점

![image](https://github.com/user-attachments/assets/37562f70-7411-400b-bc92-e8b0b0223b0a)

- `Docker 컨테이너`는 `가볍고 빠르며`, `동일한 환경을 유지`할 수 있어 `배포 및 개발 효율성을 극대화`할 수 있다.

<hr>
<hr>

## 컨테이너 오케스트레이션(Container Orchestration) 개념과 활용
- 이전 챕터에서는 `Docker`를 활용한 컨테이너화(Containerization)의 개념과 실무 활용법을 다루었다.
- 이번에는 여러 개의 컨테이너를 효과적으로 관리하는 방법인 **컨테이너 오케스트레이션(Container Orchestration)** 에 대해 정리해보자.

## 1. 컨테이너 오케스트레이션이란?
- `컨테이너 오케스트레이션(Container Orchestration)` 은 **여러 개의 컨테이너를 자동으로 관리 및 조율하는 기술** 이다.

### 오케스트라에 비유
- 컨테이너 오케스트레이션은 `오케스트라의 지휘자(Conductor)` 와 같다.
- 오케스트라(Containers) : 각각의 개별 컨테이너
- 지휘자(Container Orchestrator) : 컨테이너들이 조화롭게 동작하도록 관리
- 즉, **각 컨테이너가 개별적으로 실행되는 것이 아니라, 전체 시스템이 유기적으로 동작하도록 조율하는 것이 핵심 역할** 이다.

## 2. 컨테이너 오케스트레이션의 목적
- `컨테이너 오케스트레이션`은 **대규모 컨테이너 환경을 쉽고 효율적으로 관리** 하기 위해 사용된다.
  - `여러 개의 컨테이너가 협업하여 원활하게 동작`하도록 조정
  - `자원을 최소한`으로 사용하면서도 `최적의 성능` 유지
  - `자동화된 관리로 효율적인 운영` 가능
- 이를 통해 **개발자와 운영팀이 컨테이너를 수동으로 관리하는 부담을 줄이고, 더 중요한 업무에 집중할 수 있도록 돕는다.**

## 3. 선언전 프로그래밍(Declartive Programming) 과 오케스트레이션
- 컨테이너 오케스트레이션은 **선언적 프로그래밍(Declartive Programming) 방식을 사용** 한다.

### 선언전 프로그래밍이란?
- **목표 상태(Desired State)를 정의**하고, **그 상태를 유지하도록 자동 조정**
- 작업 순서를 직접 지정하는 것이 아니라, **최종 결과를 지정**한다.
- 예를 들어, "웹 서버 5개가 항상 실행되도록 설정" 하면, 오케스트레이션 도구가 알아서 5개를 유지한다.

### 구성 파일(Configuration File) 활용

![image](https://github.com/user-attachments/assets/64e97d6c-249f-4884-b00b-c452d7de2570)

- `YAML` 또는 `JSON` 같은 **설정 파일에 `컨테이너 이미지 위치`, `네트워크 설정`, `저장소 할당` 등의 정보를 입력**
- `컨테이너 오케스트레이션 도구`가 이를 `자동으로 설정 및 배포`한다.

(ex)

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: my-app
spec:
  replicas: 3  # 웹 서버 컨테이너 3개 실행 유지
  selector:
    matchLabels:
      app: my-app
  template:
    metadata:
      labels:
        app: my-app
    spec:
      containers:
      - name: my-app-container
        image: my-app:latest
        ports:
        - containerPort: 80
```

## 4.컨테이너 오케스트레이션의 장점
- 컨테이너를 수동으로 관리하는 방법도 있지만, 컨테이너 오케스트레이션을 활용하면 더 많은 이점을 얻을 수 있다.

### 1) 확장성(Scalability)
- 수요 증가 시 컨테이너 자동 확장(Scailing)
  - `수평 확장(Horizontal Scailing)` : 컨테이너 `개수를 늘리거나 줄이기`
  - `수직 확장(Vertical Scailing)` : 컨테이너 `리소스(CPU, 메모리) 동적 조정`
- (ex) 웹사이트 방문자가 증가하면 자동으로 웹 서버 컨테이너 개수를 추가

### 2) 자동화(Automation)
- 컨테이너 `배포`, `업데이트`, `장애 복구` 등의 **반복작업을 자동화**
- 개발자는 비즈니스 로직 개발에 집중 가능

### 3) 비용 절감 및 자원 최적화
- `필요할 때만 컨테이너를 실행`하여 **불필요한 리소스 사용 최적화**
- 기업은 서버 운영 비용을 절감 가능

### 4) 가용성(Availability) 및 복구
- 장애 발생 시, 컨테이너를 자동으로 다시 시작하거나 교체
- 서비스 중단 없이 안정적인 운영을 할 수 있다.

### 5) 업데이트 및 롤백 지원
- 새로운 버전 배포 시, `기존 컨테이너를 점진적으로 교체`하여 `무중단 배포가 가능`하다(Rolling Update)
- 문제가 발생하면, **이전 버전으로 즉시 롤백 가능**하다.

## 5. 컨테이너 오케스트레이션의 활용 사례

### 1) 마이크로서비스 아키텍처(Microservices Architecture)
- 대규모 애플리케이션을 `여러 개의 작은 서비스(컨테이너) 단위로 나누어 관리`한다.
- (ex) 각 컨테이너가 독립적으로 실행되면서 **서로 통신하며 협업**한다.

### 2) 트래픽 변동이 심한 서비스
- 사용량이 급증하는 서비스(ex. 온라인 쇼핑몰, 스트리밍 서비스)에서 활용한다.
- 트래픽 변화에 따라 `컨테이너 개수를 유동적으로 조절`하여 `서비스 중단을 방지`한다.

### 3) 데이터 엔지니어링 및 머신러닝 파이프라인
- `데이터 처리 및 머신러닝 모델 학습 과정`에서 `여러 개의 컨테이너가 자동으로 배포 및 실행`
- (ex) Spark 클러스터, ETL 파이프라인, AI 모델 학습 환경 구축

## 6. 컨테이너 오케스트레이션 도구
- 컨테이너 오케스트레이션을 지원하는 다양한 도구가 존재한다.

![image](https://github.com/user-attachments/assets/177874f5-5993-45f9-8055-ac3eb8b578d8)

| 오케스트레이션 도구       |       특징    |
|---------------|----------------------|
|`Kubernetes(가장 인기)`| 구글에서 개발, 강력한 확장성 및 자동화 기능 제공|
|Docker Swarm|Docker에서 제공하는 간단한 오케스트레이션 도구|
|Red Hat OpenShift| Kubernetes 기반으로, 엔터프라이즈 환경에 최적화|
|HashiCorp Nomad| Kubernetes보다 가벼운 구조, 다양한 워크로드 관리 가능|

### 가장 널리 사용되는 오케스트레이션 도구 : Kubernetes
- 가장 강력한 기능을 제공하며, **대규모 컨테이너 환경에서 필수적인 도구** 이다.
- 이후 챕터에서는 Kubernetes 대해 자세히 다룰 예정이다.

![image](https://github.com/user-attachments/assets/d482a98f-274d-4672-9594-c8e7f509e58f)


<hr>
<hr>

## Kubernetes 를 활용한 컨테이너 오케스트레이션
- 이전 챕터에서 `컨테이너 오케스트레이션`(Container Orchestration)의 개념과 필요성에 대해 배웠다.
- 이번에는 Kubernetes 를 중심으로 실제 컨테이너 오케스트레이션이 어떻게 이루어지는지 살펴보도록 하자.
- Kubernetes(쿠버네티스)는 현재 가장 널리 사용되는 **컨테이너 오케스트레이션 도구** 이며, 많은 기업이 컨테이너 환경을 관리하기 위해 `Kubernetes`를 활용하고 있다.

## 1. Kubernetes란?
- `Kubernetes`(K8s)는 `컨테이너화된 애플리케이션`의 `배포`, `확장(Scailing)`, `관리(Management)`를 **자동화하는 오픈 소스 플랫폼**이다.
- `K8s` 라는 약어는 `K` 와 `s` 사이에 `8개의 글자`가 있기 떄문에 붙여진 별칭이다.
- 원래 `Google 이 개발` 했으며, 2014년에 오픈 소스 프로젝트로 공개되었고, 현재는 `Cloud Native Computing Foundation(CNCF)`에 의해 관리된다.
- 많은 기업들이 Kubernetes를 사용하거나 도입을 검토하고 있을 만큼 업계 표준으로 자리잡고 있다.

## 2. Kubernetes 의 특징

![image](https://github.com/user-attachments/assets/eee44527-66c2-4dcb-8fff-9012ed8073f4)
![image](https://github.com/user-attachments/assets/2aeeacde-4c35-47d5-b7e7-b6fbc8b83eb0)

- 컨테이너를 `논리적 단위(Logical Unit)로 그룹화`
- `분산 시스템(Distributed System)` 기반
- `클라우드` 및 `온프레미스(On-Premise)환경`에서 `모두 운영 가능`
- `자동화된 배포`, `확장성 제공`
- 장애 발생 시 `자동 복구(Self-healing)` 지원

- 즉, `Kubernetes`를 사용하면 컨테이너가 어떤 머신에서 실행되는지를 **직접 관리할 필요 없이, 자동으로 할당 및 배치할 수 있다.**

## 3. Kubernetes 아키텍처 구성 요소
- Kubernetes는 여러 개의 중요한 구성 요소로 이루어져 있으며, 이를 하나씩 살펴보자.

### 1) `Pod` (가장 작은 배포 단위) - 최소 실행 단위

![image](https://github.com/user-attachments/assets/2e38168e-0e74-439f-9c26-b93ebc9ec511)

- `Pod`는 `Kubernetes`에서 **가장 작은 배포 단위**이며, `하나 이상의 컨테이너`로 구성된다.
- `같은 Pod 내의 컨테이너`들은 `자원을 공유`하며, `같은 네트워크 주소를 사용`한다.
- 즉, **여러 개의 컨테이너가 같은 작업을 수행하거나 협력해야 할 경우 Pod 내에서 함께 실행**된다.

### 2) `Node` (하드웨어 단위) - 호스트 머신

![image](https://github.com/user-attachments/assets/ff5fdf9c-b187-4738-9348-1ef521487eb8)

- `Node`는 `Pod가 실행되는 호스트 머신`을 의미한다. - Kubernetes 에서 가장 작은 컴퓨팅 하드웨어 단위로 `Pool`을 나타낸다.
- `물리적 서버(Physical Server)` 또는 `가상 머신(Virtual Machine)`일 수 있다.
- `Node`는 실제 사용자 지정 머신이 아닌 `머신을 추상화`하므로 `모든 노드는 다른 노드로 쉽게 교체될 수 있으며` 모든 것이 동일하게 작동한다. - **특정 Pod 가 항상 동일한 Node 에서 실행되는 것은 아니다.**
- Kubernetes는 Node들을 `클러스터(Cluster)`로 `묶어 관리`한다.

### 3) `Control Plane` (노드 및 Pod 관리) - 클러스터 제어

![image](https://github.com/user-attachments/assets/6adc2d1a-6cd7-4ee1-bfae-ff377be17361)

- Control Plane(제어 평면)은 `클러스터를 관리`하고, `적절한 노드에 적절한 Pod를 배치하는 역할`을 한다. - **사용 가능한 Node 에 Pod를 스마트하게 할당하여 리소스를 할당**하는 역할을 한다.
- `클러스터의 두뇌(Brain of the Cluster)`라고 불릴 만큼 중요한 요소이다.
- 주요 역할
  - `Pod`를 특정 `Node`에 자동 할당
  - 리소스 사용량 최적화
  - 장애 발생 시 컨테이너 자동 재시작

### 4) `Cluster` (노드들의 모음) - 전체 시스템

![image](https://github.com/user-attachments/assets/e4183c75-d252-4afd-9553-a92dee6d5dd3)

- `Kubernetes 클러스터`에는 앞서 언급한 `모든 구성 요소가 포함`되어 있으며 최대 수천 개의 노드로 구성된 그룹이다. - **`여러 개의 Node가 모여` Kubernetes `클러스터를 형성`한다.**
- `클러스터 내부의 Node`들은 `하나의 슈퍼 컴퓨터(Super-Machine)` 처럼 동작한다. - **`클러스터`에서는 `개별 노드의 리소스가 함께 풀링`(Pooing)되고 강력한 슈퍼 머신을 형성하는데, 이 슈퍼머신이 클러스터라고 할 수 있다.**
- 사용자는 특정 Node가 아닌 `클러스터 자체에 애플리케이션을 배포`하면, `Kubernetes가 자동으로 적절한 Node에 배치`한다.

### 정리
![image](https://github.com/user-attachments/assets/8805c7fc-045c-443f-86a8-58d55ee8d8a9)

## 4. Kubernetes 와 Docker 의 관계
- Docker 와 Kubernetes 는 함께 사용될 수 있지만, 각각 다른 역할을 수행한다.

![image](https://github.com/user-attachments/assets/41f0fb61-380b-4d37-ae32-b2cfd008d9e1)
![image](https://github.com/user-attachments/assets/0a69a1a8-4370-409e-a40e-c0de8e0bf4f0)

- `Docker` 는 개발자가 `컨테이너를 쉽게 생성하고 실행할 수 있도록 도와주는 도구` 이다.
- `Kubernetes` 는 `수백~수천 개의 컨테이너를 효율적으로 배포, 확장 및 관리하는 데 최적화된 도구` 이다.
- Kubernetes는 Docker 외에도 `Containerd` 같은 더 가벼운 컨테이너 런타임을 사용할 수도 있다.
- 즉, `Docker`는 `개발자 경험(Developer Experience)에 초점`이 맞춰져 있고, `Kubernetes`는 `확장성과 자동화(Scalability & Automation)에 최적화`되어 있다.

## 5. Kubernetes 의 주요 기능
- `자동화된 컨테이너 배포 및 업데이트`
- `자동 스케일링(Scailing)` : 트래픽 증가 시 Pod 개수 자동 증가
- `자동 복구(Self-healing)` : 장애 발생 시 컨테이너 재시작
- `로드 밸런싱(Load Balancing)` : `트래픽을 여러 Pod로 자동 분산`
- `클러스터 내 모든 Node 리소스를 하나의 슈퍼 컴퓨터처럼 사용 가능`

## 6. Kubernetes를 사용하는 이유
- Kubernetes를 사용하면 `대규모 애플리케이션을 안정적으로 운영하고 관리`할 수 있다.

### 1) 확장성이 뛰어남
- **트래픽이 증가하면 `자동으로 Pod 를 확장하여 서비스 성능을 유지`한다.**
- **사용량이 적을 때는 `자동으로 Pod 개수를 줄여 비용을 절감`한다.**

### 2) 장애 복구 및 가용성 보장
- `컨테이너가 다운되면 자동으로 새로운 컨테이너를 생성`한다.
- **`서비스 중단 없이 운영`할 수 있다.**

### 3) 효율적인 자원 관리
- `여러 개의 Node`를 `하나의 클러스터로` 묶어 하드웨어 리소스를 최적화한다.
- `필요한 곳에 적절한 컨테이너를 자동으로 배치`한다.

### 4) 다양한 환경에서 운영 가능
- `클라우드(AWS, GCP, Azure)` 및 `온프레미스(On-premise)` 환경 **모두 지원**한다.
- **멀티 클라우드 및 하이브리드 클라우드 환경에서도 활용 가능**하다.

<hr>
<hr>

## Dockerfile 읽기 및 컨테이너 실행하기
- 이제까지 `Docker` 와 `Kubernetes`의 개념과 활용법을 배웠다면, 이번 챕터에서는 직접 `Docker 컨테이너를 실행하는 방법`을 배워본다.
- 이를 위해 `Dockerfile을 작성하는 방법과 실행 명령어`에 대해 자세히 알아볼 것이다.

## 1. Docker 개념 복습
- Docker의 핵심 개념을 다시 한번 정리해보자.

![image](https://github.com/user-attachments/assets/479dab17-98ee-438e-9fa9-dfd1e6369438)

![image](https://github.com/user-attachments/assets/20a84748-c3d3-4156-a0fc-47b324506c20)

- Dockerfile -> Docker Image -> Docker Container
- 즉, `Dockerfile 을 기반`으로 `Docker 이미지를 빌드`하고, 이 이미지를 실행하면 `Docker 컨테이너가 생성`된다.

## 2. Dockerfile 명령어 vs Docker CLI 명령어
- Docker를 다룰 때, CLI(Command Line Interface) 명령어와 `Dockerfile 명령어`(Instruction) 를 구분해야 한다.

![image](https://github.com/user-attachments/assets/96d2770c-db49-4036-822a-01520c2c9cec)


- Dockerfile 명령어(Instruction) : `Docker 이미지`를 생성할 때 사용하는 **명령어** - **Dockerfile의 구성 요소**
- DockerCLI 명령어(Commands) : `Docker container`를 실행 및 관리할 때 사용하는 **명령어** - **Docker 개체를 관리하기 위해 Docker Daemon으로 전송되는 명령어**

![image](https://github.com/user-attachments/assets/17fe4823-2244-4742-9363-370f7122e86b)

- 즉, `Dockerfile`은 `컨테이너를 만들기 위한 구성 파일`이고, `CLI 명령어`는 `컨테이너 실행 및 관리에 사용`된다.

## 3. Dockerfile 작성 형식
- Dockerfile의 기본 형식은 다음과 같다.

### Dockerfile Instructions 형식 규칙
1. 주석(Comment) : `#`기호로 시작
2. 명령어(Command) : `대문자(Uppercase)` 로 작성
3. 인수(Arguments) : `소문자(Lowercase)` 로 작성
4. 작성 순서 : **위에서 아래로 순차적으로 실행**된다.

- `Dockerfile`은 `메타데이터`, `주석`, `인수`로 시작할 수 있고, `FROM`command 로도 시작할 수 있다.

## 4. 주요 Dockerfile 명령어

### 1) `FROM`(베이스 이미지 설정)
- Docker 이미지는 항상 `기존 이미지 기반으로 생성` 된다.
- `FROM` 명령어는 `기본이미지(Base Image)` 를 설정한다.

- 문법
```dockerfile
FROM <name_of_image>
```

- 예시
```dockerfile
# Define the image on which to build
FROM python:3.8 # Python 3.8 이미지를 기반으로 생성
```

### 2) `COPY`(파일 복사)
- `로컬 파일을 컨테이너 내부로 복사`할 때 사용한다.
- `.`(점)은 `현재 디렉토리(current directory)`를 의미한다.

- 문법
```dockerfile
COPY <source> <destination>
```

- 예시
```dockerfile
# COPY files/folders to the main folder of the container
COPY . /app  # 현재 폴더의 모든 파일을 컨테이너 내부 `/app` 폴더로 복사  
```

### 3) `RUN`(명령어 실행)
- `이미지 생성 중 실행할 명령어`를 정의한다.
- 주로 `필요한 패키지 설치` 또는 `환경설정`에 사용된다.
- 컴퓨터의 CLI 에서 명령어를 실행하는 방법과 유사하다.

- 문법
```dockerfile
RUN <command>
```

- 예시
```dockerfile
RUN pip install -r requirements.txt # 필요한 Python 패키지 설치
```

### 4) `ENTRYPOINT`(컨테이너 실행 시 기본 실행 파일)
- 컨테이너가 실행될 때 **`기본으로 실행할 명령어`를 정의**한다.

- 문법
```dockerfile
ENTRYPOINT ["command", "argument"]
```

- 예시
```dockerfile
# Run the script when the container starts
ENTRYPOINT ["python", "app.py"] # 컨테이너 실행 시 Python 애플리케이션 app.py 실행
```

## 5. Dockerfile 예제
- 위의 명령어들을 조합하여 간단한 `Dockerfile`을 만들 수 있다.
```dockerfile
# 1. Python 3.8 을 기반으로 컨테이너 생성
FROM python:3.8

# 2. 현재 디렉토리의 파일을 /app 폴더로 복사
COPY . /app

# 3. 작업 디렉토리를 /app으로 설정
WORKDIR /app

# 4. 필요한 패키지 설치
RUN pip install -r requirements.txt

# 5. 애플리케이션 실행
ENTRYPOINT ["python","app.py"]
```

## 6. Docker 이미지 및 컨테이너 실행
- 이제 Dockerfile 을 사용하여 이미지를 빌드하고 컨테이너를 실행하는 방법을 알아보자.

### 1) `docker build`(이미지 빌드)
- `docker build` 명령어를 사용하여 `Dockerfile`을 기반으로 `Docker 이미지를 생성` 할 수 있다.
- `dockerfile`은 CLI에서 명령을 실행할 때 **빌드되는 곳에 위치되어야 한다.** - <context> 바깥의 파일은 Dockerfile에서 `COPY` 하려고 하면, 오류가 발생한다.

- 문법
```sh
## <context>는 빌드 컨텍스트를 의미한다. dockerfile은 반드시 빌드 컨텍스트 내부에 있어야 한다.
docker build (-t) <이미지 이름>:<태그> <context>
```
- 예시
```sh
docker build -t my-image .
```
- `-t my-image` : 생성할 이미지에 'my-image'라는 이름을 설정 - **<태그>가 생략되면 자동으로 `latest'라는 태그가 붙는다.**
- `.` : **현재 디렉토리의 Dockerfile을 사용하여 빌드**
- 빌드가 완료되면 `Docker 이미지가 생성` 된다.

### -t (태그) 옵션
- `-t` 옵션을 지정하지 않으면, Docker는 이름이 없는 이미지(untagged image)를 자동 생성한다.
- 이렇게 생성된 이미지는 `docker images` 명령어로 확인하면 이름 대신 **`ID로 표시`** 된다. - 나중에 컨테이너를 실행할 때, 이미지 ID를 직접 입력해야 하는 불편함이 있다.

(ex)
```nginx
REPOSITORY   TAG       IMAGE ID       CREATED        SIZE
<none>       <none>    5d3b2c123abc   3 minutes ago  125MB
```
- 보통 `-t` 옵션을 사용할 때 이미지 이름 규칙은 `<이름>:<태그>` 형식으로 작성한다.
- **<태그>가 생략되면 자동으로 `latest'라는 태그가 붙는다.**
```sh
docker build -t my-image:latest .
docker build -t myapp:v1 .
docker build -t backend:v2 .
docker build -t myrepo/myapp:1.0 .

# 이미지 이름을 Docker Hub 또는 개인 레지스트리에 업로드 할 경우
docker build -t myusername/my-image:1.0 . # myusername/my-iamge : Docker Hub의 `myusername` 계정 아래 저장된다.
```

![image](https://github.com/user-attachments/assets/64232e92-bfcc-4183-8908-e1e6d3d77231)


### 2) `docker run`(컨테이너 실행)
- `docker run` 명령어를 사용하여 'Docker 이미지`에서 `Docker 컨테이너를 생성하고 실행`할 수 있다.

- 문법
```sh
docker run <name_of_image>
```

```sh
docker run my-image
```
- `my-image` : 실행할 Docker 이미지 이름
- 이제 `my-image` 기반의 컨테이너가 실행되며, `ENTRYPOINT`에 설정된 `app.py`가 자동으로 실행된다.

### 추가질문 & 답변
![image](https://github.com/user-attachments/assets/cfa7e396-93c7-4de3-aad6-62c9fc4c159b)

<hr>
<hr>
