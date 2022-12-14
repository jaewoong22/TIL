# OSI 7 계층 기초 정리

## OSI 7 계층 이란?

* 네트워크 : 사용자 혹은 데이터가 어떤 곳에서 다른 곳으로 이동 할 수 있게 만든 통로입니다. 현대의 네트워크는 TCP/IP를 이용하고 어떤한 곳이든 접근할 수 있게 해줍니다.

* OSI7 계층: 네트워크 분야에서 가장 중요하게 다루는 것으로 세계적으로 사용이 되고 네트워크 표준 모델입니다. 이 안에서 TCP/IP 네트워크 통신에 사용되는 전반적으로 프로토콜이 모두 포함되어 있습니다.

* 1계층 물리층 : 실제로 장치들을 연결하기 위한 물리적인 사항을 정의
* 2계층 데이터 전송층 : 두 지점 간의 신뢰성 있는 전송을 보장
* 3계층 네트워크층 : 여러 개의 지점을 거칠 때 경로를 찾아줌
* 4계층 전송층 : 양 끝단의 사용자들이 송수신에 있어서 신뢰성을 보장
* 5계층 양 끝단의 프로세스가 통신을 관리하기 위한 방법을 제공
* 6계층 표현층 : 인코딩 및 데이터의 형식 차이를 조절
* 7계층 응용층 : 응용 프로그램에서 서비스를 수행

## 1계층 물리 계층 
* 주로 전기적 및 기계적인 특성으로 통신 케이블로 데이터를 전송하는 기능
* 사용되는 단위로는 bit 이며 전기 적으로 on, off를 나타낸다.
* 케이블, 리피터, 허브

## 2계층 데이터 링크 계층
* 물리계층을 통하여 송,수신 되는 정보의 흐름과 오류를 관리한다.
* 맥주소를 가지고 통신이 가능한계층
* 사용되는 단위는 프레임
* 블릿지, L2스위치
* 2계층 까지만 있으면 실제 네트워크 통신이가능함
    * 두 컴퓨터를 물리적(케이블)으로 연결


## 3계층 네트워크 계층
* 가장 중요한 목적은 데이터를 목적지 까지 가장 안전하고 빠르게 전달하는 것, 라우팅
* 경로배정을 하고 경로에 따라 데이터를 전달하는 것이 하는 일
* 랜상 상호 네트워크 가능
* 사용되는 단위는 패킷
* 라우터, L3스위치
* **IP를 사용하기 위해 네트워크 계층이 필요**
    * 2계층에 있는 MAC Address 만으로 네트워크 통신을 할 수 있지만 그렇게될 경우 전세계의 모든 컴퓨터가 연결되 있어야함
    * 이런 이유 때문에 3계층

## 4계층 전송 계층
* 정보를 분할하고 다시 합치는 과정을 담당한다.
* 통신 과정에 있어 오류제어와 흐름제어를 한다.
* 사용되는 단위는 세그먼테이션
* TCP, UDP
* TCP에서 사용되는 주소를 Port라고함
    * 응용프로그램 사용하기 위한 번호
    * HTTP, 등등


구분  | UDP                     | TCP
----|-------------------------|--------------------------------
신뢰성 | 신뢰성이 없다                 | 신뢰성이 있다
연결성 | 비연결성                    | 연결성
재전송 | 재전송없음                   | 재전송
특징  | 신뢰할 수 없지만 고속의 데이터 전송 가능 | 흐름제어로 인하여 속도는 비교적느려도 신뢰성 있는 연결


## 5계층 세션 계층
* 통신 사이의 연결이 끊기지 않게 세션을 영어 관리하는 역할

## 6계층 표현 계층
* 다양한 데이터의 포멧을 일정한 포멧으로 변환하고 압축과 암호화, 복호화 작업을 수행하는 역할

## 7계층 응용 계층
* 응용 프로그램과 사용자 사이의 인터페이스를 제공하는 역할
* 크롬, 익스플로우 등



## 각 계층 별로 사옹되는 프로토콜

계층 | 계층명     | 프로토콜                 | 장비             | 기능
---|---------|----------------------|----------------|----------------------------------------------
7  | 응용 계층   | DHCP, DNS, FTP, HTTP | 서비스 제공         | 사용자가 네트워크에 접근할 수 있는 계층이다.
6  | 표현 계층   | JPEG, MPEG, SMB, AFP | 이해할 수 있는 포멧 변환 | 운영체제의 한 부분으로 입력 또는 출력되는 데이터를 하나의 표현 형태로 변환한다.
5  | 세션 계층   | SSH, TLS             | 응용간의 질서 제어     | 통신 세션을 구성하는 계층으로, port연결이라고도 한다.
4  | 전송 계층   | TCP, UDP, ARP        | 게이트 웨이         | 전체 메시지 발신지 대 목적지간 제어와 에러를 관리한다.
3  | 네트워크 계층 | IP, ICMP             | 라우터            | 다중 네트워크 링크 패킷을 발신지로부터 목적지로 전달할 책임을 갖는다.
2  | 데이터 계층  | MAC, PPP             | 브리지, 스위치       | 오류 없이 한 장치에서 다른 장치로 프레임을 전달역할
1  | 물리 계층   | Ethernet RS-232C     | 허브, 리피터        | 물리적 매체를 통해 비트흐름을 전송하기 위해 요구되는 기능들의 조정.
## 각 계층별 송/수신 과정
<p align="center">
    <img src="https://github.com/jaewoong22/TIL/blob/main/IMG/각 계층별 송수신 과정.png">
</p>

* 각 계층을 지나면서 캡슐화와 디캡슐화가 이루어지며 송/수신이 이루어진다.


## 네트워크 구조

<p align="center">
  <img src="https://github.com/jaewoong22/TIL/blob/main/IMG/네트워크 구조.png">
</p>

### 애플리케이션
* 브라우저, 메일러, 웹 서버, 메일 서버 등의 프로그램이 해당됩니다.
* 여기서 브터 아래로 향해서 데이터 송 수신 등의 일을 의뢰합니다.
* 애플리케이션 아랫부분에는 Socket 라이브러리가 있으며, 그 안에는 리졸버가 내장되어 있습니다.
    * DNS 서버에 조회하는 동작을 실행 합니다.


### 프로토콜 스택
* 프로토콜 스택의 윗부분에는 TCP라는 프로토콜을 사용하여 데이토 송 수신을 담당하는 부분과 UDP라는 프로토콜을 사용해서 데이터 송 수신을 담당합니다.
  * 브라우저나 메일 등의 일반적인 애플리케이션 데이터 송수신 할 때는 TCP
  * DNS 서버에 대한 조회 등에서 짧은 데이터 송수신을 하는 경우에는 UDP
* 그 아래에는 IP 프로토콜을 사용해서 패킷 송 수신을 동작을 제어하는 부분이 있습니다.
  * 인터넷에서 데이터를 운반 할 때는 데이터를 작게 나누어 `패킷` 형태로 운반됩니다.
  * ICMP 패킷은 운반할 때 발생하는 오유를 통지하거나 제어용 메시지를 통지할 때, ARP는 IP 주소에 대응하는 이터넷의 `MAC 주소`를 조사할 때 사용합니다.

### LAN 드라이버
* IP 아래에 있는 LAN 드라이버는 LAN 어댑터의 하드웨어를 제어합니다.

### LAN 어뎁터
* LAN 어댑터가 실제 송수신 동작, 즉 케이블에 대해 신호를 송 수신하는 동작을 실행합니다.

