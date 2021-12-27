# Echo-Programing

* socket : Client Program 과 Server Program이 상호 통신시 Network상의  통신 접속점 <br>
  즉, 네트워크 상의 송수신은 socket을 통해 이루어짐

---
<br>

# Chatting 기능 구현하기 위한 자바 예제

## Echo Server

* 소켓에서 입,출력 스트림 얻음
  
<br>

```java
public class EchoSever {

	public static void main(String[] args) throws IOException {

		ServerSocket ss = new ServerSocket(7112); // 7112 -> 포트번호
		
		Socket s = ss.accept();
		
		InputStream is = s.getInputStream(); //소켓에서 inputStream 얻기
		
		OutputStream os = s.getOutputStream(); //소켓에서 outputStream 얻기
		
		int b; //btye stream 처리

		while(true) {

			b= is.read(); //(byte단위로)문자열 읽기 Client -> Server

			if(b == -1) { // -1은 eof, 파일의 끝

				os.write(b); //문자열 출력 Server -> Client
			}
		}
	}

}
```

## Echo Client

* 사용자쪽에서 입력

```java
public class EchoClient {

	public static void main(String[] args) throws IOException, UnknownHostException {

		Scanner sc = new Scanner(System.in);
		
		Socket s = new Socket("127.0.0.1", 7112); //connect
		
		BufferedReader br = new BufferedReader(new InputStreamReader(s.getInputStream()));
		
		BufferedWriter bw = new BufferedWriter(new OutputStreamWriter(s.getOutputStream()));
		
		while(true) {
			System.out.println("글자 넣으세요.");
			
			String sendForServer = sc.nextLine();
			if(sendForServer.length() == 0) {
				break;
			}
			bw.write(sendForServer, 0, sendForServer.length());//server로 키보드에서 입력받은 0~length까지 전부 전송
			bw.newLine(); // 줄바꿈도 전송
			bw.flush(); //무조건!! 서버로 전송한 후 버퍼 비움!
			String send2fromServer = br.readLine(); //server로부터 받음
			
			System.out.println("서버로부터 다시 옴!" + send2fromServer);
		}
		s.close();
		//실행은 서버 먼저 실행(run) 후 클라이언트 실행(run)
	}

}
```