# Part 6

## STP

```
개념
1. 브리지 ID
    브리지나 스위치들이 통신할 때 서로를 확인하기 위해 하나씩 가지고 있는 번호
    브리지 우선순위(2bytes) + 맥 어드레스(6bytes) 로 총 8bytes로 구성되어 있음

2. Path Cost
    다른 스위치로 가는 데 드는 비용


기본 동작
1. 네트워크당 하나의 루트 브리지를 갖는다.
2. 루트 브리지가 아닌 나머지 모든 브리지는 무조건 하나씩의 루트 포트를 갖는다.
3. 세그만트당 하나씩의 데지그네이티드 포트를 갖는다
+ 루트포트나 데지그네이티드 포트가 아닌 나머지 모든 포트는 다 막아버린다

루트 브리지가 선출되는 순서
1. 누가 더 작은 Root BID를 가졌는가?
2. 루트 브리지까지의 Path Cost 값은 누가 더 작은가?
3. 누구의 BID(Sender BID)가 더 작은가
4. 누구의 포트 ID가 더 낮은가

BPDU(Bridge Protocol Data Unit) : 브리지가 프레임을 가지고 스패닝 트리 정보를 자기들끼리 주고받게한다, 가지고 있는 정보엔 Root BID, Root Path Cost, Sender BID, Port ID

Non Root Bridge
    - 루트 브리지가 아닌 브리지나 스위치
    - 모든 Non Root Bridge는 반드시 한 개의 루트 포트를 갖는다

Designated Port
    - 스패닝 트리에서 어떤 포트를 풀어주고 어떤 포트를 막을지 결정해주는 포트
    - 세그먼트당 하나씩의 데지그네이티드 포트를 갖는다
    - 세그먼트상에서 Root Path Cost를 서로 비교해서 더 작은 Cost를 가진 포트가 데지그네이티드 포트로 선출
    - 루트 브리지의 모든 포트들은 언제나 데지그네이티드 포트로 전정

5가지 상태 변화
1. Disabled : 포트가 고장나서 사용할 수 없거나 네트워크 관리자가 포트를 일부러 ShutDown시켜 놓은 상태
    - 아무 정보도 못 보내고 못 받는 상태
2. Blocked : 스위치를 맨 처음 키거나 Disabled되어 있는 포트를 관리자가 다시 살린 포트 상태
    - BPDU 만 주고 받는 상태
3. Listening : 블로킹 상태에 있던 스위치 포트가 루트 포트나 데지그네이티드 포트로 선정된 상태
    - BPDU 만 주고 받는 상태
4. Learning : 리스닝 상태에 있던 스위치 포트가 포워딩 딜레이 디폴트 시간인 15초 동안 그 상태를 계속 유지한 상태
    - Mac address 정보를 배움
    - BPDU를 주고 받음
5. Forwarding : 스위치 포트가 러닝 상태에서 다른 상태( Root port, Desinated port -> Non Designed port)로 넘어가지 않고 다시 포워딩 딜레이 디폴트 시간인 15초 동안 그 상태를 계속 유지하며 상태가 넘어감
    - 데이터 전송
    - Mac address를 배워 브리지 테이블을 만듬
    - BPDU를 주고 받음


Mac-Address
    - 동적 할당
        300초 기억
        Learning 과정을 거쳐야 함
    - 정적 할당
        영원히 기억함
        메모리를 낭비
        자동으로 수정이 불가능함

VLAN
    1. 스위치로 여러 개의 브로드캐스트 영역을 나누어 줄 수 있다
    2. 여러개의 스위치를 사용할 필요가 없어 비용이 절감된다

    - 허브나 브리지에서는 지원하지 않는 기능, 따라서 VLAN을 지원하면 이 장비는 스위치 이상의 장비

    VTP
        1. "Virtual Trunking Protocol"
        
        - VTP가 구성되어 있지 않다면 새로운 VLAN을 추가할떄 다른 스위치에서도 VLAN을 하나 하나 추가해 줘야한다
        - VTP가 구성되어 있다면 다른 스위치와의 트렁크 링크를 통해 VLAN 정보를 자동으로 업데이트 된다

        3가지 형식
            1. Summary Advertisement : 5분마다 한 번 씩 전달하는 메시지, Revision 
            넘버 전송한다 받은 스위치는 그 넘버를 보고 자신들의 VLAN 정보가 최선버전인지 아닌지 판단
            변화가 생겼다면 5분을 기다리지 않고 바로 다음으로 전달
            2. Subset Advertisement : VLAN 구성이 변경되었을 떄나 VTP 
            클라이언트로부터 advertisement request 메시지를 받았을때 전송됨
            3. Advertisement Request : 클라이언트가 VTP 서버에 summary 
            advertisement와 subset advertisement를 요청하는 용도로 쓰임
```