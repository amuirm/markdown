# Part 5

## 라우터에서 IP 주소 이해하기
```
Ethernet : 우리가 내부에서 사용하기 위해 부여받은 IP 주소 중 하나를 배정,라우터에 부여한 주소는 또 다시 PC에 부여하면 안 된다
Serial : 라우터가 접속하는 상대편 라우터의 시리얼 인터페이스와 IP 주소를 서로 맞추어야 한다, 서브넷 마스크는 서로 같아야 함
```
## IP 주소
```
32자리 2진수로 구성
네트워크 부분 + 호스트 부분
어떠한 네트워크에서든지 서로 다른 PC가 통신을 하기 위해선 네트워크 부분은 같고 호스트 부분은 모두 달라야 된다
네트워크 부분이 같아야 라우터를 거치지 않고 통신할 수 있다
호스트 부분이 같으면 충돌이 일어나 통신이 되지 않는다
```

## TCP/IP
```
TCP/IP가 사용하는 주소가 바로 IP 주소이다
A, B, C, D, E , 총 5개의 클래스로 IP 를 구분할 수 있다
보통 쓰이는 클래스는 A, B, C이다 ( 나머지 D, E는 각각 멀티캐스트, 연구목적으로 쓰이는 클래스이다)
```

## Subnet Mask
```
메인이 아닌 어떤 가공을 통한 네트워크를 위해서 씌우는 마스크
예를 들어 클래스 B의 주소를 받았다 하지만 필요한 host는 별로 없다고 할때 브로드캐스트의 영향이 크기 때문에 나눠주어야 하는데 이때 이 네트워크에 서브네팅을 사용해야 한다
```
<!-- 157p.g -->

