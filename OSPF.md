### Open Shortest Path First 

- link-state 라우팅 프로토콜
- 최적의 경로를 계산할 때 SPF(Shortest path First) 또는 다익스트라 알고리즘을 이용하여 각 목적지 까지의 최적 경로를 계산
- Multicast를 사용하여 정보를 전달
	- 224.0.0.5 : DR이 DROTHER에게 전송할 때 사용
	- 224.0.0.6 : DROTHER가 DR에게 전송할 때 사용
- AD값은 110을 사용한다.

### OSPF 장점

- OSPF는 area 단위로 구성되어 대규모 네트워크를 안정되게 운영할 수 있음.
	- 특정 area에서 발생하는 상세한 라우팅 정보가 다른 area로 전송되지 않아 큰 규모에서 안정되게 운영할 수 있다. (재분배 설정을 통해 다른 area로 전송 가능)
- Stub 이라는 강력한 축약 기능
	- 기존 라우팅 프로토콜과는 달리 IP주소가 연속되지 않아도 Routing table의 크기를 획기적으로 줄일 수 있다.
- 표준 라우팅 프로토콜
- Convergence time이 전반적으로 빠른 편이다.

### OSPF의 네트워크 분류

- 동작 방식 및 설정이 다르다.
![](https://blog.kakaocdn.net/dn/rCclL/btqA1Ata3vH/9MQNN4lGkhK5i27CqkR0h1/img.png)

#### 1. Broadcast Multi Access
- 하나의 BroadCast패킷을 전송할 경우 동일 네트워크 상의 모든 장비에게 전달되는 네트워크를 Broadcast 네트워크, 하나의 인터페이스를 통해 다수의 장비와 연결된 네트워크를 Multi Access 네트워크라고 한다.
- ex) Ethernet
- broadcast나 multicast 방식을 사용해 하나의 packet만 전송해도 연결된 모든 장비에게 전송 됨.
![](https://blog.kakaocdn.net/dn/tAQhs/btqA4yOuahe/aINKar9ra9MVUpRyVaJgJ1/img.png)

#### 2. Non Broadcast Multi Access(NBMA)
- Broadcast가 지원되지 않는 Multi Access 네트워크를 의미한다.
- 대부분 내부에 Virtual Circuit(가상회로) 방식을 사용
- NBMA 에서는 Broadcast를 사용하여 전송할 경우 가상회로 하나당 하나씩 Broadcast packet을 전송해야 함.
![](https://blog.kakaocdn.net/dn/bhNO2G/btqA6o5p3zF/MnYoTDaEqnmhgR4icCT5O1/img.png)

#### 3. Point-to-Point
- 하나의 인터페이스와 연결된 장비가 하나뿐인 네트워크
![](https://blog.kakaocdn.net/dn/nfyQz/btqA3eQhKoF/GAuDfwiIt03lUUn17AzmW0/img.png)