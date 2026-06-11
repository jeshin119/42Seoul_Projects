## 42서울 프로젝트

### 0써클: 언어적 펀더멘탈, 메모리 관리, 시스템 환경 구축

1. **libft** | `C`, `Pointer Arithmetic`, `Dynamic Memory Allocation (malloc/free)`, `Linked List`
* 외부 라이브러리 없이 C 표준 함수들을 바닥부터 재구현한 커스텀 라이브러리. 포인터 연산을 통한 메모리 바이트 단위 제어, 스트링 가공, 단일 연결 리스트(Single Linked List) 자료구조의 삽입·삭제·순회 및 메모리 동적 할당/해제 메커니즘 포함.
* [https://github.com/jeshin119/Libft](https://github.com/jeshin119/Libft)


2. **ft_printf** | `C`, `va_list`, `va_start`, `va_arg`, `va_end`, `Type Casting`
* 호출 규약(Calling Convention)과 스택 프레임 구조를 이용해 가변 인자를 처리하는 포맷팅 출력 엔진. 문자열 파싱 루프를 통해 서식 지정자별 데이터 타입을 판별하고, 정확한 바이트 크기 계산 및 형변환을 거쳐 표준 출력을 수행함.
* [https://github.com/jeshin119/Ft_printf](https://github.com/jeshin119/Ft_printf)


3. **get_next_line** | `C`, `Static Variables`, `File Descriptors (FD)`, `Buffer Management`, `Memory Leak Debugging`
* 파일 디스크립터(FD)로부터 입력 스트림을 읽어 줄 바꿈(`\n`) 단위로 반환하는 데이터 버퍼링 함수. 유동적인 버퍼 크기 환경에 대응하기 위해 정적 변수(Static Variable) 기반의 파일별 캐시 시스템을 구축하고, 자원 유실이 없는 메모리 수명 주기를 제어함.
* [https://github.com/jeshin119/Get_next_line](https://github.com/jeshin119/Get_next_line)


4. **born2beroot** | `VirtualBox`, `Debian/Ubuntu OS`, `LVM`, `UFW`, `SSH/Sudoers`, `Password Policy (PAM)`, `Bash Scripting`
* 가상화 환경(Hypervisor) 기반의 보안 고도화 리눅스 시스템 구축. LVM을 활용한 유동적 디스크 파티셔닝 및 LUKS 암호화 적용, PAM 모듈 기반 비밀번호 정책 강화, UFW 방화벽 및 Sudoers 권한 최소화 설정을 반영함. 시스템 메트릭을 실시간 수집하여 주기적으로 브로드캐스팅하는 Bash 모니터링 스크립트 및 런타임 크론탭(Crontab) 스케줄러 포함.



---

### 1써클: IPC, 수학적 그래픽스 파이프라인, 알고리즘 최적화

1. **pipex** | `C`, `pipe()`, `fork()`, `dup2()`, `execve()`, `waitpid()`, `Environment Variables (envp)`
* Unix 오퍼레이팅 시스템의 쉘 파이프라인(`|`) 메커니즘을 재현한 IPC(프로세스 간 통신) 시스템. `fork()`를 통한 자식 프로세스 다중 생성, `pipe()` 및 `dup2()`를 이용한 표준 입출력(I/O) 스트림 리다이렉션, `envp` 환경변수 파싱 기반의 외부 바이너리 실행 및 `waitpid()` 동기화 처리.
* [https://github.com/jeshin119/Pipex](https://github.com/jeshin119/Pipex)


2. **FdF** | `C`, `MiniLibX (X11)`, `Isometric Projection`, `Bresenham's Line Algorithm`, `Coordinate Transformation`
* 2D 격자 맵 데이터를 3D 와이어프레임 모델로 변환하는 등각 투영(Isometric Projection) 그래픽스 엔진. 화면 프레임 버퍼 메모리에 픽셀 데이터를 직접 맵핑하는 렌더링 시스템 구조이며, 정수 연산 기반의 브레젠험(Bresenham) 알고리즘을 통한 고속 선형 보간 알고리즘 적용.
* [https://github.com/jeshin119/FDF](https://github.com/jeshin119/FDF)


3. **push_swap** | `C`, `Double Linked List (Circular)`, `Greedy Algorithm`, `Quick Sort Variation`, `Complexity (Big-O)`
* 제한된 명령어 세트와 스택 구조를 기반으로 데이터를 정렬하는 복잡도 최적화 알고리즘 프로그램. 고속 노드 순회를 위해 양방향 원형 연결 리스트로 스택 구조를 명세했으며, 데이터 세트 크기에 맞춰 모래시계, 그리디, 피벗 분할 정복 알고리즘을 동적으로 적용하여 최소 연산 횟수를 산출함.
* [https://github.com/jeshin119/Push_swap](https://github.com/jeshin119/Push_swap)



---

### 2써클: 고급 문자열 파싱, 인터프리터 설계, 동시성 프로그래밍

1. **minishell (팀 프로젝트)** | `C`, `Lexical Analysis`, `Syntax Analysis`, `Signal Handling`, `Termios`, `Redirection`
* POSIX 규격을 준수하는 CLI 기반 명령어 인터프리터(Shell) 시스템. 입력 문자열의 렉서(Lexer) 토큰화 및 파서(Parser) 구문 분석 엔진 탑재, 다중 파이프 루프 내 프로세스 동시 실행 제어, Here-doc 인터럽트 제어 및 `termios` 구조체를 이용한 터미널 입력 제어 로직 포함.
* [https://github.com/jeshin119/Minishell](https://github.com/jeshin119/Minishell)


2. **philosophers** | `C`, `POSIX Threads (pthread)`, `pthread_mutex`, `Semaphores`, `Data Race`, `Deadlock Prevention`
* 비동기 멀티스레드/멀티프로세스 아키텍처 환경의 동시성 제어 및 공유 자원 동기화 시스템. 뮤텍스(Mutex) 및 세마포어(Semaphore)의 원자적 연산을 통한 데이터 레이스(Data Race) 원천 차단, 자원 할당 순서 비대칭 설계를 통한 교착상태(Deadlock) 및 기아 상태 방지, `gettimeofday()` 모니터링 스레드 탑재.
* [https://github.com/jeshin119/Philosopher](https://github.com/jeshin119/Philosopher)



---

### 3써클: 객체지향 아키텍처, 네트워크 토폴로지, 비동기 이벤트 루프 그래픽스

1. **CPP Module** | `C++98`, `Encapsulation`, `RAII`, `Orthodox Canonical Form`, `Polymorphism`, `Templates`, `STL`
* C++98 표준 스펙을 준수하는 객체지향 프로그래밍(OOP) software 디자인 패턴. 생성자/소멸자 자원 제어 기반의 RAII 아키텍처를 도입하여 자원 유수를 차단하고, 가상 함수 기반의 가상 메소드 테이블(Vtable) 다형성 구현 및 STL 컨테이너 내부 구조 분석을 통한 제네릭 시스템 설계.
* [https://github.com/jeshin119/cpp_modules](https://github.com/jeshin119/cpp_modules)


2. **NetPractice** | `Computer Networking`, `IPv4 Addressing`, `Subnetting (VLSM)`, `CIDR`, `Routing Table`, `Gateway`
* 가변 길이 서브넷 마스크(VLSM) 및 CIDR 알고리즘을 적용한 IP 네트워크 토폴로지 아키텍처 모델링. 다중 인터페이스 환경의 이기종 서브넷 간 패킷 라우팅 처리를 위해 최장 일치(Longest Match) 규칙에 의거한 라우팅 테이블 구성 및 게이트웨이 파이프라인 설계.


3. **cub3d** | `C`, `Raycasting Engine`, `DDA Algorithm`, `Trigonometry (Vector/Matrix)`, `Texture Mapping`, `Event Loop`
* 2D 벡터 맵 구조 위에서 시야각(FOV)에 따른 실시간 광선을 투사하는 3D 레이캐스팅 그래픽스 엔진. DDA(Digital Differential Analysis) 알고리즘 기반 벽면 교차점 스캔, 거리 비례 왜곡 보정 및 텍스처 픽셀 매핑 연산 처리. X11 이벤트를 후킹하여 드랍 없는 프레임을 보장하는 비동기 렌더링 루프 구성.
* [https://github.com/jeshin119/Cub3d](https://github.com/jeshin119/Cub3d)



---

### 4써클: 컨테이너 가상화 오케스트레이션 및 고성능 이벤트 기반 비동기 웹서버

1. **Inception** | `Docker`, `Dockerfile`, `Docker-compose`, `Nginx`, `WordPress`, `MariaDB`, `TLS/SSL`, `Docker Network`
* 마이크로 서비스 아키텍처 구성을 위한 멀티 컨테이너 가상화 인프라 환경 구축. 경량 OS 기반 가상 레이어 캐싱 Dockerfile 빌드, Docker-compose 구동 인프라 자동화, OpenSSL 자가 서명 기반의 Nginx 리버스 프록시(HTTPS 443 포트) 구성, 격리된 내부 브릿지 네트워크 및 볼륨 바인딩을 통한 데이터 영속성 환경 설계.
* [https://github.com/jeshin119/Inception](https://github.com/jeshin119/Inception)


2. **webserv** | `C++`, `Network Socket API`, `I/O Multiplexing (kqueue/epoll)`, `Non-blocking I/O`, `State Machine`, `CGI`
* 대규모 트래픽 처리를 위해 커널 레벨 I/O 멀티플렉싱 인터페이스를 도입한 **Non-blocking 이벤트 드리븐 커스텀 HTTP 웹서버**. HTTP/1.1 프로토콜 스펙 파싱을 위한 결정적 유한 오토마톤(DFA) 기반 상태 머신 Request Parser 설계, 청크드 전송 부하 분산 처리, 자식 프로세스 포크 후 표준 스트림 파이프 연동을 통한 CGI(Common Gateway Interface) 동적 확장 레이어 수동 구현.
* [https://github.com/jaejehyun42/webserv](https://github.com/jaejehyun42/webserv)
