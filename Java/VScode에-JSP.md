1. 기본 확장팩 설치 했다는 가정하에 진행

2. 탐색기 하단에 TOMCAT SERVERS에서 서버 우클릭

3. Open Server Configuration 클릭(server.xml 파일 열림)

4. Host 태그 밑에 ``<Context path="" docBase="실행할 jsp파일 경로"></Context>`` 입력 <br>
   나의 경로 : /Users/geon/Workspace/ldg/src/main/resources/static

 ```xml
    <Host name="localhost" appBase="webapps" unpackWARs="true" autoDeploy="true">
        <Valve className="org.apache.catalina.valves.AccessLogValve" directory="logs" prefix="localhost_access_log" suffix=".txt" pattern="%h %l %u %t &quot;%r&quot; %s %b"/>
    </Host>
   ```