# AWSMidExam
## week 2
### 클라우드 개념 개요 (1)
1. IT 서비스란?
- 컴퓨터 기술을 이용해 기업이나 개인에게 제공하는 서비스
<br>

2. 네트워크란?
- 컴퓨터 장치들 사이를 연결하는 기술
<br>

3. 인터넷이란?
- 작은 네트워크들이 모여 하나의 큰 네트워크를 구성 한 것
<br>

4. IT 서비스 구성
- Internet
- Server(SW + HW)
  - Web Application(SW)
  - Server(HW)
- client(SW + HW)
  - Web Browser(SW)
  - Computing Device(HW)

5. IT 서비스 운영
   1. 상용 IT 서비스에 요구되는 점
   - 24시간 / 7일 내내 안정적인 서비스 제공 
     1. 소프트웨어가 시스템 중단으로 이어지지 않아야 함.
     - 소프트웨어공학적 접근을 통해 버그를 줄이고, 버그가 실패로 이어지지 않는 아키텍처를 구상
     2. 비정상 종료되지 않는 인프라
        1. 장비 자체의 높은 안정성 필요
        2. 안정적인 전원 공급
        3. 온도 및 습도 관리
     - 위 3가지 조건을 충족하기 위해선 테이터 센터가 필요
     3. 데이터 센터
     - 인프라를 안정적으로 관리하기 위한 시설
     - 자체 전력 설비를 통해 정전시에도 전원 공급 가능
     - 하드웨어 인프라에 대한 발열 및 습도 관리
       - 타워형 서버
       - 랙 마운트 형 서버
         - 타워형 서버와 달리 서버 랙에서 관리 가능
     - 네트워크를 통한 연결

### 클라우드 개념 개요 (2)
1. 전통적인 IT 서비스 구축 과정
   1. 새로운 서비스 기획
   2. 서버 등의 장비 구매
   3. 데이터 센터 공간 임대
   4. 데이터 센터 내 서버에 인터넷으로 접속 후 개발 진행
   5. 서비스 시작

2. 전통적인 IT 서비스 구축 과정의 어려움
   1. 서버 등의 장비 구매 과정이 수개월 이상 걸리는 경우가 많음
   2. 데이터 센터 직접 구축하는 경우 큰 비용 발생
   3. 서버 등 구매 시 사용자 규모 예측에 실패하면 서비스 장애 발생하며 즉각적인 대처가 어려움

3. 클라우드 환경에서 IT 서비스 구축 과정
   1. 새로운 서비스 기획
   2. 서버 등의 장비 대여 요청
   3. 클라우드 컴퓨팅 서비스
   4. 개발 진행
   5. 서비스 시작

4. 클라우드 환경에서 IT 서비스 구축 과정
   1. 낮은 초기 비용과 구매 기간 단축
      - 서버 가상화를 통해 사용자가 원할 떄 원하는 만큼의 서버를 대여 할 수 있음.
        - On-Demand
        - 서버 가상화란, 물리 서버에서 가상머신을 실행하는 방식
      - 사용한 만큼 비용을 지불
        - 종량제 결제 모델(Pay-as-you-go)
   2. 사용자 규모 예측 불필요
      - 사용자 규모가 증가하면 필요한 만큼 자원을 추가로 대여
        - 확장성
      - 사용자 규모가 줄어들면 반납 가능
        - 탄력성
        - 비용 최적화 가능

## week 3
### AWS 핵심 컴퓨팅 서비스
#### (EC2 (Elastic Cloud Compute) 생성/삭제 및 접속 방법)
1. AWS 컴퓨팅 서비스란?
- 프로그램을 실행시킬 수 있는 환경을 제공하는 서비스
  - 기존 자체 설비(On-Premise) 환경에서는 그것이 물리 서버를 의미
- AWS에서는 가상 머신을 이용해 가상 서버 환경을 제공, 물리 서버와 사용상 차이 없음
- 가장 대표적인 것은 AWS EC2(Elastic Cloud Compute) 서비스

2. EC2(Elastic Cloud Compute)
- 기존 서버에서 실행하는 것과 동일한 유형의 애플리케이션을 호스팅할 수 있는 가상 머신
- 사용자가 할당 받은 가상 머신 한 대를 인스턴스(Instance)라고 함
- 인스턴스 별로 사용자가 원하는 애플리케이션을 실행

3. 원격 서버 사용 방법
- 원격 서버 접속(Remote Server Access)
  - SSH(Secure SHell)
  - 사용자 Local PC는 Private Key, 원격 서버는 Public Key를 가지고 있고 접속 시 두 키가 맞는지 확인
  - 이 두 키를 키 페어(key Pair)라고 한다.
  - 두 키가 맞으면 암호화(Encrypt)와 복호화(Decrypt)를 하며 통신

4. 원격 서버 관리
- 원격 서버 관리(Remote Server Administration)
  - 전문 툴을 이용한 서버 상태 모니터링(Status & Health Monitoring)
  - 원격 접속을 통한 관리
  - 서버 설정 최적화(Configuration Optimization)

5. Linux 환경의 이해
- Linux 터미널 환경
  - 명령줄 인터페이스(Command Line Interface, CLI)를 이용해 OS 사용 환경
  - CLI에 명령어를 입력하여 OS의 프로그램 실행, 파일과 디렉토리 다룰 수 있는 방법 제공
  - 예시<br>
  `ssh -i <키페어 파일 경로> <사용자 명>@<서버IP>`
  ```console
  $ ssh -i ~/.ssh/labsuser.pem ec2-user@52.32.29.1
  ```
  - ID와 Password를 통해 사용자 인증
    - 여러 명의 사용자가 사용 가능
    - ID와 Password 대신 키 페어(Key Pair) 사용 가능
    - 특정 사용자의 Password에 대신 키페어 사용하도록 지정 가능
  - EC2에 Amazon Linux가 설치된 경우
    - ec2-user를 기본 사용자로 생성됨
    - EC2 생성 과정에 지정한 키페어가 ec2-user 로그인에 대신 사용됨

6. 컴퓨터 아키텍쳐와 파일
   1. 컴퓨터 아키텍쳐
      1. CPU
      2. Memory
      3. Disks
         1. 논리적 볼륨(Logical Volume)으로 나누어진 디스크 위에 파일 시스템(File System)이 저장된다.
         2. 파일 시스템은 디렉토리와 파일의 구조를 관리한다.

7. 디스크와 디렉토리 관련 Windows와 Linux의 차이점
   1. Windows는 각 디스크 드라이브(C:, D:)가 최상위 디렉토리이다.
   2. Linux는 특정 디렉토리에 디스크 연결 가능, 최상위(Root directory)는 하나 밖에 없음<br>
   ![윈도우 디스크](Img/윈도우%20디스크.png)
   ![리눅스 디스크](Img/리눅스%20디스크.png)

8. CLI에서 파일과 디렉토리 관리
   1. 현재 디렉토리 확인<br>
   `pwd`
   2. 현재 디렉토리 내의 파일 및 디렉토리 목록 확인<br>
   `ls`
   3. 현재 디렉토리에 디렉토리 생성<br>
   `mkdir <디렉토리 명>`
   4. 디렉토리 이동<br>
   `cd <이동할 디렉토리 명>`
      - 상대 경로
        - 현재 디렉토리를 기준으로 이동하는 방법
        - .. : 현재 디렉토리를 기준으로 상위 디렉토리
      - 절대 경로
        - 현재 디렉토리와 상관없이 전체 경로를 모두 명시하여 이동하는 방법
        - ~ : 사용자 디렉토리를 가리키는 기호
      - 디렉토리 및 파일명 맨 앞의 "." 기호의 의미
        - 숨김 파일 및 숨김 디렉토리를 의미
        - `ls -al`로 숨긴 파일 및 디렉토리 확인 가능
   5. 파일 삭제<br>
   `rm <삭제할 파일 이름>`
   6. 디렉토리 삭제<br>
   `rm -r <삭제할 디렉토리 이름>`
   7. 파일 내용 출력<br>
   `cat <출력할 파일 이름>`
   8. 파일의 생성 시간을 변경하거나, 새로운 파일을 생성하는 명령어<br>
   `touch <파일 명>`
   9. 디스크와 같은 블록 디바이스의 목록을 출력<br>
   `lsblk`

9. EC2 인스턴스 수명 주기(Lifecycle)<br>
![ec2의 생명주기](Img/ec2의%20생명주기.png)

### AWS 핵심 컴퓨팅 서비스
#### EC2 인스턴스 타입(Instance Type)과 EBS(Elastic Block Store)
1. EC2
- 성능의 기준은 vCPU / Memory / Storage / Network로 구분
- 사용 목적에 따라 미리 정해진 규격(Specification)을 인스턴스 타입(Instance Type)으로 제공
- 스토리지는 EBS(Elastic Block Store)와 인스턴스 스토어(Instance Store)로 나뉨
  - 모든 인스턴스에는 EBS 유형의 스토리지를 설정할 수 있음
  - 인스턴스 스토어는 특정 인스턴스 타입의 EC2 인스턴스에서만 사용할 수 있음

2. EC2 인스턴스 타입(Instance Type) 분류
- EC2는 목적에 따라 인스턴스 패밀리로 분류
- 패밀리 내에서 세부적으로 타입을 선택하게 됨
  - 범용(General Purpose) 인스턴스 패밀리
  - 컴퓨팅 최적화(Compute optimized)
  - 메모리 최적화(Memory optimized)
  - 스토리지 최적화(Storage optimized)
  - 액셀러레이티드 컴퓨팅(Accelerated Computing)

3. 규격(Specification)에 따른 성능 차이
- vCPU
  - 가상 CPU 코어 개수는 물리 CPU 코어의 쓰레드(Thread) 개수를 의미함
- Memory
  - RAM 용량을 나타내며, 클수록 연산 처리에 유리
- Storage
  - EC2 인스턴스에서 사용할 수 있는 디스크 볼륨의 용량과 처리량(Throughput), IOPS(Input/Output Per Seconds)을 나타냄
  - 처리량: 초당 데이터 전송량
  - IOPS: 초당 I/O 연산 수행 횟수
  - 처리량 = IOPS X 연산당 데이터 전송 크기
  - 1,000 X 4 Kbytes = 4 Mbytes / Seconds
- Network
  - 네트워크 대역폭(Bandwidth)을 결정
  - Gbps(Giga bit per seconds) 단위로 나타냄

4. EC2 스토리지 선택사항
- EBS(Elastic Block Store)와 인스턴스 스토어(Instance Store)
  1. 인스턴스 스토어는 EC2 인스턴스와 같은 물리 서버 내에 생성되는 형태
     - 데이터 영구 보관 불가
       - 중지(Stop) 후 시작 시 데이터 삭제
       - 종료(Terminate) 시 모든 데이터 삭제
       - 물리 디스크 문제 발생 시 복구 불가
     - EBS에 비해 빠른 성능

  2. EBS는 EBS용 물리서버에 생성되어 초고성능 네트워크를 통해 EC2 인스턴스와 연결되는 형태
       - 데이터 영구 보관
       - EBS 볼륨에 문제 발생 시 복구 가능
       - 스냅샷(Snapshot) 기능과 특정 시점 복구 기능(Point-in-time Recovery)
       - EBS 볼륨 내 데이터 암호화 가능
       - 탄력적 볼륨 지원
         - 크기 조정 / 성능 조정 가능

## week 4
1. Three-Tier Architecture
   - Presentation Tier
   - Application Tier
   - Data Tier

2. EC2(Elastic Cloud Compute)를 이용한 컴퓨팅 자원 배포
   - S/W와 OS → AMI(Amazon Machine Image)
   - CPU/Memory/Network → 인스턴스 타입(Instance Type)
   - Storage → EBS(Elastic Block Store) & 인스턴스 스토어(Instance Store)

3. IaaS(Infrastructure as a Service)
![사용과 관리 책임과 AWS 관리 책임](Img/week5-1.png)

1. AMI(Amazon Machine Images)
   - 가상머신에 현재 설치된 OS와 애플리케이션들을 이미지로 만들 수 있음
   - 이렇게 생성된 이미지를 이용해 완전히 동일한 가상머신을 추가 생성 가능
   - 클라우드의 확장성은 이를 통해 달성 가능

## week 5
1. EC2 사용자 데이터
   - 인스턴스 시작 시 자동으로 실행되는 스크립트(== 사용자 데이터) 지정(선택 사항)
   - 단, 인스턴스가 최초로 시작될 때 스크립트가 실행됨

2. 리눅스 리다이렉션(Redirection)
   1. `>>`
      - 특정 명령의 실행 결과를 파일로 저장할 때 사용
      - 파일이 존재하지 않을 경우 새로 생성하고, 파일에 결과를 저장
      - 파일이 존재할 경우 내용을 다음 줄(Line)에 추가
      - Ex.
      ```console
      $ echo "How are you?" >> test.txt
      ```
   2. `>`
      - ">>＂과 동일하게 특정 명령의 실행 결과를 파일로 저장할 때 사용
      - 단, 파일이 존재하더라도 덮어쓰게 됨(Overwrite)

3. AWS와 리소스(Resource)
   - 사용자가 생성하거나 AWS 서비스를 통해 자동으로 생성되는 모든 가상 자원

4. ARN(Amazon Resource Name)
   - 리소스를 구분하기 위한 유일한 식별자(Unique Identifier)
   - ARN 형식
     1. 서비스명
     2. 리전(Region)
     3. AWS 계정 ID
     4. 리소스 유형(Type)
     5. 리소스 ID
     6. 선택적인 추가 구성 요소
   - ARN 예시<br>
   arn:aws:ec2:us-east-1:123456789012:instance/i-01234567890abcdef

5. 리전(Region)
   - AWS의 특정 서비스를 통해 리소스를 생성할 때 실제 데이터 센터의 물리적 위치
   - 특정 지역에 위치한 데이터 센터들의 집합

6. 태그(Tag)
   - 태그는 AWS 리소스에 할당할 수 있는 레이블(Label)
   - 태깅의 장점
     - 필터링
     - 자동화
     - 비용 할당
     - 액세스 제어

7. AWS 계정과 사용자 관리
   - AWS의 IAM(Identity and Access Management) 서비스를 통해 사용자 관리 가능
   - IAM 사용자에 따라 서비스 사용에 대한 권한을 다르게 설정할 수 있음

8. IAM 역할(Role)
   - IAM 사용자는 실제 사용자를 구분하고, 사용자 별로 할 수 있는 일을 구분하기 위해 사용되는 개체

## week 6
1. 인터넷(Internet)이란?
   - 작은 네트워크들을 서로 간에 연결하여 거대한 네트워크를 구성하는 것

2. 인트라넷(Intranet)이란?
   - 특정 집단에서 사용하는 독립적인 내부 네트워크

3. IP 주소(Internet Protocol Address)
   - 서로를 구분하기 위한 유일한 구분자(Unique Identifier)

4. 네트워크 장비
   - 라우터(Router), 스위치(Switch) 

5. DHCP(Dynamic Host Configuration Protocol)
   - 라우터에서 각 PC에 IP를 부여하는 방식

6. 서브넷(Subnet)
   - 네트워크를 분할한 것 

7. 공인 IP(Public IP)와 사설 IP(Private IP)
   - 같은 IP를 가진 네트워크 대역은 인터넷에서 존재할 수 없음

8. 라우팅 테이블(Route Table)
   - 라우터에서 경로를 찾기 위해 제공하는 규칙 정보를 테이블 형태로 제공

9. NAT(Network Address Translation)
   - 인터넷과 연결할 때만 대표 공인 IP 주소를 사용하는 방법

10. IP CIDR(Classless Inter-Domain Routing) Block
   - IP 주소를 범위로 나타내는 방식

11. IP Network Prefix
   - Network Address와 Host Address를 나누는 방식

12. AWS VPC(Virtual Private Cloud)
    - 자체 설비(On-premise) 데이터 센터에서 내부의 서버들끼리 통신할 수 있는 독립된 네트워크를 구성하는 것과 마찬가지로, VPC 역시 해당 AWS 계정에 독립된 네트워크를 구성
    - 독립된 네트워크를 외부나 AWS 서비스, 혹은 다른 VPC 네트워크와 연동하기 위해서는 별도의 설정이 필요
    - VPC에서 IP CIDR Block 구성 시 IP network prefix는 /16 ~ /28 사이만 가능

## week 7
1. NIC(Network Interface Card)
   - IP가 할당되어 컴퓨터가 인터넷 통신을 할 수 있도록 하는 장치

2. 탄력적 네트워크 인터페이스(Elastic Network Interface)
   - AWS에서는 ENI를 통해 EC2 인스턴스에 네트워크 카드를 가상으로 연결

3. 인터넷을 통한 네트워크 간 연결 방법
   1. 필요한 서버에 사설IP와 공인 IP를 모두 할당
   2. NAT(Network Address Translation)을 이용한 인터넷 연결
      - 인터넷과 연결할 때만 대표 공인 IP 주소를 사용하는 방법

4. 탄력적 IP(Elastic IP)
   - EC2 인스턴스에 고정 공인 IP 할당하기 위해 생성하는 IP

 5. 데이터 센터와 리전
    - 사용자가 생성하려는 리소스가 어떤 데이터 센터에 만들어지는지 인지할 수 있도록 영역을 구분
    - 이러한 영역을 가용 영역(Availability Zone)이라 부르고, 작은 데이터 센터 여러 개를 묶어서 하나의 가용영역으로 지정하거나, 큰 데이터 센터 하나를 하나의 가용 영역으로 지정하기도 함
    - 왜 이런 구조를 갖게 되는가? → 고가용성(High Availability)

6. 고가용성
   - 서버 및 장비를 원하는 때에 원하는 만큼 사용하는 것이 가능 → On-Demand
   - 필요한 경우 추가 대여하는 것이 가능 → 확장성(Scalability) → 다중화(Redundancy)

7. AWS 글로벌 인프라(Global Infrastructure)
   - 동일 데이터 센터에 리소스 생성 시 고가용성 확보 불가
   - 가용 영역 단위로 리소스를 각각 생성해야 고가용성 확보 가능
   - 확장성(Scalability) + 복원성(Resilience) 역시 고가용성을 함께 고려해야 함
   - VPC에서 각 Subnet은 반드시 하나의 가용 영역에 속하게 됨 → 하나의 Subnet에 문제가 생기더라도, 다른 Subnet은 정상 동작 → 고가용성
