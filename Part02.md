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

