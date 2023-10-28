
### Socket 

- 네트워크를 경유하는 프로세스 간 통신의 종착점.
- OSI 7계층 중 응용 계층에 속하는 프로세스들은 데이터 송수신을 위해 반드시 소켓을 거쳐 전송 계층으로 데이터를 전달해야한다. 
- 즉, 소켓은 전송 계층과 응용 프로그램 사이의 인터페이스 역할을 하며 떨어져 있는 두 호스트를 연결해준다.
- ![](https://velog.velcdn.com/images/newdana01/post/9b90db1e-11f4-4d17-b8f6-331402801d46/image.png)
- 소켓은 3 요소로 정의 된다.
	- 프로토콜
	- IP
	- Port



### 소켓 종류

#### 1. 스트림 소켓
- TCP(Transmission Control Protocol)을 사용하는 연결 지향방식의 소켓
- 송수신자의 연결을 보장하여 신뢰성있는 데이터 송수신이 가능
- 데이터의 순서 보장
- 소량의 데이터보다 대량 데이터 전송에 적합
- 점대점 연결

#### 2. 데이터그램 소켓

- UDP(User Diagram Protocol)을 사용하는 비연결형 소켓

- 데이터의 순서와 신뢰성을 보장하기 어려움

- 점대점 뿐만 아니라 일 대 다 연결도 가능

- accept 과정없이 소켓 생성 후 바로 데이터 송수신.

- ex) 편지 -> 편지를 보내기 위해 편지 봉투에 보내는 사람 받는 사람 주소 정보를 써야한다. 그리고 우체통에 넣으면 된다. 대신 편지의 특성상 보내고 나서 상대의 수신 여부를 확인 할 방법은 없이며, 물론 전송 도중에 편지가 분실될 확률도 존재한다. -> 신뢰성이 떨어진다.


### HTTP 통신

- 클라이언트의 요청이 있을 때만 서버가 응답.
- JSON, HTML, Image 등 다양한 데이터를 주고 받을 수 있음.
- 서버가 응답한 후 연결을 바로 종료하는 단방향 통신이지만 Keep Alive 옵션을 주어 일정 시간동안 커넥션을 유지할 수 있다.
- 실시간 연결이 아닌 데이터 전달이 필요한 경우에만 요청을 보내는 상황에 유리

#### HTTP 요청
- 클라이언트가 서버에게 어떠한 동작을 요청하기 위해 보내는 정보이다. 이 때의 동작은 사용자가 원하는 작업이 무엇이냐에 따라 달라진다. 
- ex) 특정 웹페이지로 접속하는 요청
- 이 대 요청 사항은 "구글 웹페이지 띄워줘"가 될 것이고, 이 정보를 쪽지에 담아 전송한다. 이 쪽지가 http 요청 메시지이다. 요청 메시지에는 URL 정보, 서버에 요구하는 동작, HTTP 버전 정보를 담고 있다.

![](https://mobiinsidecontent.s3.ap-northeast-2.amazonaws.com/kr/wp-content/uploads/2022/09/07185042/%EC%BA%A1%EC%B2%983-1.png)

#### HTTP 응답
 - 클라이언트의 요청에 대해 서버가 답변할 차례이다. 웹 서버는 요청에 맞는 페이지를 찾아 다시 클라이언트에게로 전송해 준다. 웹 브라우저는 응답 받은 페이즐 사용자가 볼 수 있도록 표현 해준다. 
 - 최종적으로 사용자가 보게 되는 화면이 띄워지는 것이다.
	- 구글 접속해줘 -> 구글 메인 페이지 응답 -> 구글 메인 페이지 출력,
	- 회원가입해줘 -> 데이터 저장 후, 결과 응답 -> 완료되었습니다 알림창 출력

	![](https://mobiinsidecontent.s3.ap-northeast-2.amazonaws.com/kr/wp-content/uploads/2022/09/07185520/%EC%BA%A1%EC%B2%987-1.png)

### 소켓 통신

- 클라이언트와 서버가 특정 포트를 통해 양방향 통신을 하는 방식
- 데이터 전달 후 연결이 끊어지는 것이 아니라 계속해서 연결을 유지 -> HTTP에 비해 더 많은 리소스 소모
- 클라이언트와 서버가 실시간으로 계속하여 데이터를 주고받아야하는 경우에 유리
- 실시간 동영상 스트리밍이나 온라인 게임 채팅 프로그램 등에 사용