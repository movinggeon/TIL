# HTML5에서 websocket 의 등장

* http request 로 handshake (http ==> websocket으로 변경)<br>
  변경과정 : 브라우저가 서버에게 요청(header에 upgrade에다가 websocket을 실어서 보냄, 서버는 변경을 인신하고 http에서 tcp/ip로 변경)

<Br>

* stateless로 작동하는 http와 달리 접속시간은 http를 사용하고 그 후 websocket 규약에 의해 작동됨

<Br>

* 특정한 port를 통하여 Stateful로 작동하므로 언제나 양방향 통신 가능<Br>
  (기존의 http는 클라이언트가 요청을 보내고 서버가 응답하는 one-way 통신)

<Br>

* server side 의 data 변경시 client에서 변경되는 것이 가능해짐<Br>
  (기존의 http는 서버쪽이 변경되어도 자동으로 클라이언트에 반영되지 않음)

<Br>

### 참고

* websocket 작동시키기(http는 다른 client의 요청이 없으면 응답할 수 없음)<Br>
    <Br>

    client ------전송-------> server --------전송-----> 다른 client