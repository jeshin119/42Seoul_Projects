## 42서울 프로젝트

### 0써클: 언어적 펀더멘탈, 메모리 관리, 시스템 환경 구축

1. **libft (기초 데이터 구조 및 표준 라이브러리 재구현)**
* **구현 기술 및 스택**: `C`, `Pointer Arithmetic`, `Dynamic Memory Allocation (malloc/free)`, `Linked List`
* **상세 역량**: 외부 라이브러리 도움 없이 메모리 바이트 단위 제어와 포인터 연산만으로 스트링 가공, 메모리 복사/비교 함수들을 직접 구현함. 단일 연결 리스트(Single Linked List) 자료구조를 바닥부터 설계하여 데이터 추가, 삭제, 순회, 메모리 해제 메커니즘을 완벽하게 내재화함.


2. **ft_printf (컴파일러 레벨 가변 인자 처리 및 포맷팅 엔진)**
* **구현 기술 및 스택**: `C`, `va_list`, `va_start`, `va_arg`, `va_end`, `Type Casting`
* **상세 역량**: 호출 규약(Calling Convention)에 따른 스택 프레임의 데이터 접근 원리를 이해하고 가변 인자 매크로를 활용해 포맷 문자열 파싱 엔진을 구축함. 데이터 타입별(`char`, `string`, `pointer`, `integer`, `hexadecimal`) 크기를 계산하고 적절히 형변환(Type Casting)하여 버퍼 출력의 무결성을 확보함.


3. **get_next_line (정적 메모리 관리 및 스트림 버퍼링 I/O)**
* **구현 기술 및 스택**: `C`, `Static Variables`, `File Descriptors (FD)`, `Buffer Management`, `Memory Leak Debugging`
* **상세 역량**: `BUFFER_SIZE`가 유동적인 환경에서 파일 디스크립터(FD)로부터 데이터를 효율적으로 읽어오기 위해 정적 변수(Static Variable)를 버퍼 캐시로 활용함. 이 과정에서 다중 FD 처리를 위한 최적화와 메모리 누수(Memory Leak) 및 댕글링 포인터가 절대 발생하지 않도록 정밀한 자원 해제 플로우를 설계함.


4. **born2beroot (가상화, 리눅스 커널 보안 및 인프라 아키텍처)**
* **구현 기술 및 스택**: `VirtualBox`, `Debian/Ubuntu OS`, `LVM (Logical Volume Manager)`, `UFW (Uncomplicated Firewall)`, `SSH/Sudoers`, `Password Policy (PAM)`, `Bash Scripting`, `Crontab`
* **상세 역량**: 하이퍼바이저 위에서 리눅스 OS를 수동 아키텍팅함. 디스크 확장성에 용이한 LVM 파티션을 구성하고 LUKS 기반 암호화를 적용함. PAM 모듈을 통한 패스워드 복잡도 강제, Sudoers 설정을 통한 권한 최소화 원칙(PoLP) 적용, UFW 방화벽 포트 포워딩 제어로 엔터프라이즈급 인프라 보안 기본 설정을 마스터함. 시스템 메트릭(CPU, RAM, Disk, Network)을 모니터링하여 Wall 데몬으로 브로드캐스팅하는 Bash 스크립트를 작성하고 10분 주기 크론탭(Crontab)으로 자동화함.



---

### 1써클: IPC, 수학적 그래픽스 파이프라인, 알고리즘 최적화

1. **pipex (운영체제 프로세스 생명주기 및 IPC 파이프라인)**
* **구현 기술 및 스택**: `C`, `pipe()`, `fork()`, `dup2()`, `execve()`, `waitpid()`, `Environment Variables (envp)`
* **상세 역량**: Unix 쉘의 핵심 기능인 파이프라인(`|`) 자원 전송 메커니즘을 프로세스 관점에서 구현함. `fork()`를 통해 자식 프로세스를 생성하고 `pipe()` 파일 디스크립터를 `dup2()`로 복사해 입출력(stdin/stdout) 스트림을 리다이렉션함. `envp` 문자열 배열에서 `PATH` 경로를 파싱, `execve()`로 외부 바이너리 명령어를 안전하게 로드하고 `waitpid()`를 통해 자식 프로세스의 종료 상태 코드를 추적 및 자원 좀비화를 방지함.


2. **FdF (3D 컴퓨터 그래픽스, 투영 수학 및 렌더링 파이프라인)**
* **구현 기술 및 스택**: `C`, `MiniLibX (X11 Graphic Library)`, `Isometric Projection`, `Bresenham's Line Algorithm`, `Coordinate Transformation`
* **상세 역량**: 2D 격자 지도 데이터를 읽어와 등각 투영(Isometric Projection) 수학 공식을 적용, 3D 와이어프레임 모델로 좌표 변환하는 그래픽스 엔진을 구축함. 프레임 버퍼 메모리에 직접 접근하여 픽셀 값을 밀어 넣는 방식으로 화면 잔상을 제어함. 두 점 사이의 픽셀을 정수 연산만으로 부드럽게 잇는 브레젠험 라인 알고리즘(Bresenham's Algorithm)을 구현하여 렌더링 성능을 극대화함.


3. **push_swap (자료구조 정렬 최적화 및 복잡도 제어)**
* **구현 기술 및 스택**: `C`, `Double Linked List (Circular)`, `Greedy Algorithm`, `Quick Sort Variation`, `Complexity (Big-O)`
* **상세 역량**: 두 개의 한정된 스택 공간에서 정해진 명령어로만 데이터를 정렬하는 고난도 최적화 과제를 수행함. 효율적인 노드 이동을 위해 양방향 원형 연결 리스트(Circular Doubly Linked List)로 스택을 구현함. 데이터 개수에 따라 모래시계 알고리즘, 그리디(Greedy) 기법, 피벗 기반의 분할 정복(Quick Sort 변형)을 선택적으로 적용하여 연산 횟수(명령어 수)를 극단적으로 줄이며 Big-O 시간/공간 복잡도를 최적화함.



---

### 2써클: 고급 문자열 파싱, 인터프리터 설계, 동시성 프로그래밍

1. **minishell (POSIX 준수 커널 인터프리터 및 쉘 서브시스템 설계 - 팀 프로젝트)**
* **구현 기술 및 스택**: `C`, `Lexical Analysis (Tokenization)`, `Syntax Analysis`, `Signal Handling (SIGINT/SIGQUIT)`, `Termios`, `Redirection (<, >, >>, <<)`, `Built-in Commands`
* **상세 역량**: **[팀 프로젝트 - Git 협업 및 아키텍처 분배]** 쉘 프로세스를 밑바닥부터 설계함. 입력된 문자열의 따옴표, 환경변수 치환을 처리하는 렉서(Lexer)와 파서(Parser)를 전개함. 다중 파이프 루프 내에서 추상 구문 트리에 따라 명령어를 동시 실행하고, Here-doc(`<<`) 처리를 위해 임시 파일 및 시그널 인터럽트를 정밀 제어함. `termios` 구조체를 제어하여 터미널 키보드 입력(에코 비활성화 등)을 커스텀하고 `cd`, `exit`, `export` 등 빌트인 명령어를 쉘 내부 메모리 컨텍스트와 동기화하여 수동 구현함.


2. **philosophers (동시성 제어, 공유자원 경합 및 교착상태 방지)**
* **구현 기술 및 스택**: `C`, `POSIX Threads (pthread)`, `pthread_mutex`, `Semaphores`, `Data Race`, `Deadlock/Starvation Prevention`, `Precision Time Management`
* **상세 역량**: 멀티스레드와 멀티프로세스 환경에서 발생하는 동시성 제어 문제를 해결함. 공유 자원에 대한 동시 접근을 제어하기 위해 뮤텍스(Mutex) 및 세마포어(Semaphore) 원자적 연산을 적용하여 데이터 레이스(Data Race)를 원천 차단함. 자원 할당 순서의 비대칭성을 부여해 교착상태(Deadlock) 4대 조건을 무력화하고 기아 상태(Starvation)를 방지하는 알고리즘을 설계함. `gettimeofday()` 기반의 마이크로초 단위 정밀 타이머 스레드를 별도로 운용하여 모니터링 루틴을 구축함.



---

### 3써클: 객체지향 아키텍처, 네트워크 토폴로지, 비동기 이벤트 루프 그래픽스

1. **CPP Module (객체지향 설계, 메모리 안정성 및 제네릭 프로그래밍)**
* **구현 기술 및 스택**: `C++98`, `Encapsulation`, `RAII (Resource Acquisition Is Initialization)`, `Orthodox Canonical Form`, `Polymorphism (Virtual Function)`, `Templates`, `STL Containers/Algorithms`
* **상세 역량**: 절차지향 프로그래밍을 벗어나 객체지향 패러다임(OOP)을 정립함. 복사 생성자, 대입 연산자 오버로딩을 포함한 정형화된 정적 클래스 구조를 설계하고 소멸자를 통한 자동 자원 해제(RAII)로 메모리 누수를 원천 차단함. 순수 가상 함수를 활용한 추상 클래스 설계로 런타임 다형성(Dynamic Binding)을 극대화함. 데이터 독립적인 코딩을 위해 함수/클래스 템플릿(Generic)을 커스텀 정의하고 Vector, List, Map 등 다양한 STL 컨테이너의 내부 동작 특성을 파악하여 알고리즘 최적화에 매칭함.


2. **NetPractice (네트워크 토폴로지 설계 및 패킷 라우팅 알고리즘)**
* **구현 기술 및 스택**: `Computer Networking`, `IPv4 Addressing`, `Subnetting (VLSM)`, `CIDR`, `Routing Table Configuration`, `Default Gateway`
* **상세 역량**: 네트워크 인프라 설계의 핵심인 IP 라우팅 구조를 마스터함. 제한된 IP 자원 내에서 가변 길이 서브넷 마스크(VLSM)와 CIDR 표기법을 활용해 계층별 서브넷을 쪼개고 할당함. 다중 인터페이스를 가진 라우터 환경에서 패킷이 유실되거나 루프에 빠지지 않도록 목적지 주소별 최적의 마스크 일치(Longest Match) 규칙에 맞춰 라우팅 테이블 및 기본 게이트웨이를 설계함.


3. **cub3d (레이캐스팅 레이 레이어 및 실시간 비동기 이벤트 루프)**
* **구현 기술 및 스택**: `C`, `Raycasting Engine`, `DDA (Digital Differential Analysis)`, `Trigonometry (Vector/Matrix)`, `Texture Mapping`, `Asynchronous Event Loop`
* **상세 역량**: 2D 맵 데이터 위에 플레이어 시야각(FOV)에 맞춰 가상의 광선을 투사하여 3D 원근감을 표현하는 레이캐스팅 엔진을 바닥부터 코딩함. 광선이 벽과 부딪히는 교차점을 부동소수점 연산 오차 없이 빠르게 찾는 DDA 알고리즘을 구현함. 벽과의 거리 비례에 따른 수직선 스케일링 및 텍스처 픽셀 오프셋 매핑을 계산하여 입체감을 구현함. 키보드와 마우스 입력 이벤트를 후킹(Hooking)하여 프레임 드랍 없이 실시간으로 화면을 지우고 다시 그리는 비동기 이벤트 기반 렌더링 루프를 구축함.



---

### 4써클: 컨테이너 가상화 오케스트레이션 및 고성능 이벤트 기반 비동기 웹서버

1. **Inception (DevOps, 마이크로 인프라 컨테이너화 및 보안 네트워크)**
* **구현 기술 및 스택**: `Docker`, `Dockerfile`, `Docker-compose`, `Nginx`, `WordPress`, `MariaDB`, `TLS/SSL (OpenSSL)`, `Docker Network (Bridge)`, `Docker Volume`
* **상세 역량**: 인프라 가상화 및 IaC(코드 기반 인프라)의 기초를 다짐. 경량화 OS 이미지를 기반으로 레이어 캐싱을 고려한 자체 Dockerfile을 설계함. Docker-compose 파일 하나로 다중 컨테이너 환경을 유기적으로 연동함. 외부 진입점인 Nginx를 Reverse Proxy로 구성하고 OpenSSL을 이용해 자가 서명 TLS 인증서를 부착, 모든 트래픽을 HTTPS(443 포트)로 강제함. WordPress(FastCGI 연동)와 MariaDB 서버를 독립된 내부 브릿지 네트워크로 격리시키고 볼륨(Volume) 마운트를 통해 컨테이너가 내려가도 데이터가 손실되지 않는 영속성 환경을 구축함.


2. **webserv (고성능 대규모 트래픽 대응 비동기 웹서버 엔진 구축)**
* **구현 기술 및 스택**: `C++`, `Network Socket API (socket, bind, listen, accept)`, `I/O Multiplexing (select/poll/epoll/kqueue)`, `Non-blocking I/O`, `HTTP/1.1 Spec Parsing`, `State Machine`, `CGI (Common Gateway Interface)`
* **상세 역량**: 프로토콜 스펙 및 고성능 인프라 아키텍처 역량의 결정체임. 리눅스/유닉스 커널 소켓 API를 이용해 서버 소켓을 개방함. 멀티스레드 방식의 C10K 컨텍스트 스위칭 비용 문제를 극복하기 위해, 커널 레벨의 **I/O 멀티플렉싱 기법을 도입하여 단일 스레드로 수천 개의 파일 디스크립터를 감시하는 Non-blocking 이벤트 드리븐 아키텍처**를 구축함. HTTP/1.1 규격을 준수하여 대용량 요청 패킷이 들어올 때 데이터가 쪼개져 와도 누수 없이 조립하는 상태 머신(State Machine) 기반 HTTP Request Parser를 설계함. 정적 파일 캐시 전송, 청크드 응답(Chunked Transfer Encoding) 구현은 물론, 자식 프로세스를 생성하여 환경변수 세팅 후 스트림을 연결해 파이썬이나 쉘 스크립트 등을 구동하는 CGI 인터페이스 표준까지 완벽하게 직접 코드로 구현함.
