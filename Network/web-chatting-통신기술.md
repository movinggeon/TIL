# 여러가지 통신 기술

## polling 방식

* 클라이언트에서 지속적으로 서버에 http request 하여 response를 받는 방식(client는 일정한 주기로 request를 보냄)

* 클라이언트가 많을 경우 서버 overhead 발생<Br>
  또한 서버에 변경이 없을 경우라도 request마다 response하게 되므로 필요없는 작업이 발생

<Br>

## long polling 방식 

* 클라이언트에서 서버로 http request 후 서버가 데이터 대기하다 response를 주고 클라이언트가 받으면 받자마자 다시 서버로 http request 하는 방식

* 실시간 response가 발생

* 클라이언트가 많을 경우 서버 overhead 발생

<br>

## stream 방식

* 클라이언트에서 서버로 http request 후 request를 유지시키고 response를 지속적으로 받는 방식

* request의 유지가 문제

<br>

