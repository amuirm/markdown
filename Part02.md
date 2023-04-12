# LAN 

- "Local Area Network"

# WAN 

- "Wide Area Network"

# Ethernet

- 요즘 가장 많이 사용하는 네트워크 방식
- CSMA/CD 방식으로 통신한다.
    ## CSMA/CD
    ---
    - "Carrier Sense Multiple Access/Collision Detection" 
      - '대충 알아서 눈치로 통신하자' - 후니가쓴 CISCO 네트워킹
      - '네트워크상에 나타나는 신호(Carrier Sense)를 2개 이상의 PC나 서버가 동시에 접근(Multiple Access)할떄 데이터가 부딪쳐 충돌(Collision)이 나는지 감지(Detection)하는 것이다
      - 충돌이 발생하면 기다렸다가(1시간 기다린 후) 다시 보낸다. 다시 충돌나도 다시 보낸다. 15번 반복하고 안되면 포기한다.
      - 프로토콜

# TokenRing
- Token을 가진 PC만이 데이터를 전송할 수 있음
- Token을 받은 PC가 보낼 데이터가 없으면 다른 PC로 넘어감
1. 장점
   1. Collision이 발생하지 않음
   2. 네트워크에 대한 성능을 미리 예측하기 쉬움
2. 단점
   1. 바로 보내야 할 데이터를 바로 못 보냄
   2. 자기 차례를 기다려야 함

# Cable

- 네트워크 구성중 필요한 단계
- 다양한 종류의 케이블이 있음
    
    ## UTP
    ---
    - "Unshielded Twisted Pair" - '감싸지 않은 꼬인 한쌍'
    - STP 보다 싸다
    - 대중적으로 사용하는 케이블
  
    ## STP
    ---
    - "Shielded Twisted Pair" - '감싼 꼬인 한쌍'
    - 보다 비쌈
    - TokenRing에서 많이 쓰이는 케이블
    - EMI를 줄여 성능이 좋아졌다.
        ## EMI
        ---
        - "ElectroMagnetic Interference" - '전기기장 간섭'
        - 전자 기기들간에 통신을 하면서 서로에게 영향을 미쳐 발생하는 문제
    ##  TP
    ---
    - Category 1: 주로 전화망에 사용하는 용도로 만들어진 케이블, 전송용으로는 맞지 않음
    - Category 2: 데이터를 최대 4Mbps의 속도로 전송 할 수 있다.
    - Category 3: 10 Base T 네트워크에서 사용되는 케이블, 최대 10Mbps 속도까지 데이터 전송 가능 잘 구성하면 100Mbps까지 적용가능 ( 드물다 )
        ### 10 Base T
        ---
        - 10 = 10Mbps의 속도를 의미
        - Base = 케이블 종류
            1. 베이스밴드(BaseBand) : 디지털 방식
            2. 브로드밴드(BroadBand) : 아날라고 방식
        - T = TP(Twisted Pair) 보통 UTP를 의미, 보통 이 자리에 최대 거리 의미
    - Category 4: TokenRing 네트워크에서 사용하는 케이블, 최대 16Mbps 속도까지 데이터 전송 가능
    - Category 5: 100Mbps지원 가능한 Fast Ethernet, 요즘은 기가비트 표준이 됨 ( 이 경우 8가닥 모두 사용해야 함 )
    - Category 6: 기가비트 이상의 속도에 적합한 케이블, 가장 많이 쓰이는 케이블, 최대 10Gbps
    - Category 7: 주로 10Gbps속도 지원 가능한 케이블, 아직 많이 쓰이진 않음

## MAC Address
- "Media Access Control"
- 통신을 하는데 사용되는 주소
- ip로 통신을 하여도 다시 MAC 주소로 바뀌어 통신되는 ARP
    ### ARP
    ---
    - "Address Resolution Protocol"
    - 주소 확인 프로토콜
    - IP 주소를 MAC 주소로 바꾸는 과정
- MAC 주소는 Physical 주소, IP 및 IPX 주소는 Logical 주소라 한다.
- 48bit (6octet)

<!-- 42p.g.-->