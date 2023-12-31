### 소켓 통신

- 클라이언트와 서버가 특정 포트를 통해 양방향 통신을 하는 방식
- 데이터 전달 후 연결이 끊어지는 것이 아니라 계속해서 연결을 유지 -> HTTP에 비해 더 많은 리소스 소모
- 클라이언트와 서버가 실시간으로 계속하여 데이터를 주고받아야하는 경우에 유리
- 실시간 동영상 스트리밍이나 온라인 게임 채팅 프로그램 등에 사용

### 일반적인 소켓 통신의 흐름

![](https://velog.velcdn.com/images/newdana01/post/817b8ba8-4428-4e66-8128-7c01b554f8ff/image.png)\

#### Server
1. 소켓 생성
2. 바인딩(ip, port번호 설정)
3. listen()으로 클라이언트 요청에 대기열을 만들어 몇 개의 클라이언트를 대기 시킬지 결정
4. accept()로 클라이언트 연결
5. 데이터 송수신
6. 소켓 닫기

#### Client
1. 소켓 생성
2. 서버에 설정된 ip, port로 연결 시도
3. accept()로 클라이언트의 socket descrptor 반환
4. 데이터 송수신
5. 소켓 닫기