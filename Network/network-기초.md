* ISO : 국제 표준화 기구 (international standard organization)

* OSI : global 통신 규약 (protocol)

* 네트워크란?<br>
  근거리 및 원거리 사이의 컴퓨터 연결을 통해 데이터를 통신하는 망으로 데이터 공유가 가능

---
<br>

## OSI 7 계층

1. 물리 (Physical) 계층

2. 데이터 링크 (Datalink) 계층

3. 네트워크 (Network) 계층

4. 전송 (Transport) 계층

5. 세션 (Session) 계층

6. 표현 (Presentation) 계층

7. 응용 (Application) 계층

---

<br>

## OSI 계층간 데이터 전송

* 캡슐화 (capsulation), 디캡슐화 (decapsulation) : <br>
  계층 전송시마다 header,footer가 붙어 신뢰성 보장 및 각 계층에서 인식 가능하도록 함

---

<br>

## PDU

<상부단계부터>

1. Application Layer( 데이터 단위 -> data, Message : A - PDU) : (응용계층)<br>
    * http,ftp 등의 프로토콜

    * user에게 네트워크 리소스에 대한 서비스를 제공 <br>
    ex) e-mail, 파일 전송 등의 서비스를 제공

2. Presentation Layer( 데이터 단위 -> data, Message : P - PDU) : (표현계층)<br>
    * 네트워크의 다양한 데이터 표현 방법들을 하나로 통일시키는 역할로 입출력 데이터를 하나의 표현으로 변환하는 역할들을 말한다.

    * 이를 위해 encoding, decoding 등을 수행

3. Session Layer( 데이터 단위 -> data, Message : S - PDU)<br>
    * 연결을 안정적으로 유지하거나 처리 완료후 연결을 종료하는 역할 (TCP/IP 세션을 생성하거나 종료시키는)

4. Transport Layer( 데이터 단위 -> segments : T - PDU)<br>
    * 장비 사이에 안정적인 통신보장(신뢰성정보전달이 목적), data를 적절히 분할하고 이를 세그먼트(segment)라고 함.

    * 네트워크 계층의 요구에 맞게 세그먼트 데이터에 소스 ip, 목적 ip를 붙여 패킷화 한다.

    * 상방향일때는 패킷을 조립하여 원래의 데이터로 만든다.(TCP : 전화)(UDP : 편지 ,방송, 동영상)

5. Network Layer( packets : N - PDU) : (IP) <br>
    * router기능, packet을 순서대로 전달

    * packet을 해당 "목적지"까지 전달(정확한 목적지냐가 목적)

6. Data Link Layer( frame : DL - PDU) <br>
    * 네트워크 계층의 패킷을 **오류검사**하며 비트 모음인 프레임 단위로 만듦

    * ex) Ethernet 프로토콜

        * Ethernet
            1. 각 컴퓨터가 갖고 있는 고유의 MAC(Media Access Control) 주소로 데이터 전송 및 수신이 가능
            2. 데이터 전송시 컴퓨터간 동시 전송으로 충돌시 임의 시간동안 멈추었다가 다시 보냄

7. Physical Layer( bits : PH - PDU) : <br>
   twist cable, 전압등 체크, bit단위로 전송됨

   (전송은 데이터 > 데이터 > 세그먼트 > 패킷 > 프레임 > 비트 로 되어 전송)

---

<br>

* DNS(Domain Name Server(System))<br>
    * ex) https://www.naver.com -> 원래 네이버로 가려면 https://xxx..xxx.xxx.xxx 이런 스타일
<br>

* Ip Adress<br>
    *    특히 네트워크에서 컴퓨터를 구분하기 위한 컴퓨터 고유주소<br>
    ex)xxx.xxx.xxx.xxx (IPv4)

* port No : 한 컴퓨터내에서 프로세스 구분번호
    * 주소 : 포트번호(예: xxx.xxx.xxx.xxx:8080)
    * 사용가능 숫자 중 앞번호들은 특정번호에 사용<br>
    21 (FTP), 23(telnet) 80(http) ...

---

<br>

## TCP/IP 모델

* TCP/IP 모델 : OSI의 변형판으로 "인터넷"의 구조를 의미

  * |OSI 7계층|TCP/IP 모델|
    |:--:|:--:|
    |A+P+S|Application|
    |Transport|Transport|
    |Network|Network|
    |D+P|NetworkInterface|