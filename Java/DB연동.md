## Eclipse에 Oracle DB 연동

<br></br>

1. 나는 oracle 11g를 사용하기 때문에 ojdbc6.jar 다운
   
2. Bulid Path를 통해서 프로젝트에 jar파일 추가

3. 접속하기

```java
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.ResultSet;
import java.sql.SQLException;
import java.sql.Statement;
import java.util.Scanner;

public class TestDB {

    public static void main(String[] args) throws ClassNotFoundException, SQLException {

        Connection con =null;

        String driver = "oracle.jdbc.driver.OracleDriver";

        //@localhost = @127.0.0.1
        String url = "jdbc:oracle:thin:@localhost:1521:XE";
        String dbId = "hr";
        String dbPassword = "oracle";

        Class.forName(driver);

        con = DriverManager.getConnection(url, dbId, dbPassword);

        System.out.println("접속완료");

        con.close();
        
        System.out.println("접속끝");
    }

}
```

---
<br></br>

## Java로 DB 사용
<br></br>

```java
String sql = "select * from employees";

//sql 실행
Statement st = con.createStatement();

//ResultSet
//1. 결과값을 저장할 수 있다.
//2. 저장된 값을 한 행 단위로 불러올 수 있다.
//3. 한 행에서 값을 가져올때는 타입을 지정해 불러올 수 있다.
ResultSet rs = st.executeQuery(sql);

while(rs.next()) {
    int e_id = rs.getInt("employee_id");
    
    String e_fname = rs.getString("first_name");
    String e_h_date = rs.getString("hire_date");
    String e_hire_date = e_h_date.substring(0, 10);
    System.out.println(rs.getRow()+ "\t" + e_id + "\t" + e_fname + "\t" + e_hire_date);
} //getRow : 행번호 출력
```

---
<br></br>

## 값을 입력받아서 원하는 데이터 출력(Read)
<br></br>

```java
String sql = "select * from employees" 
                + " where lower(first_name) = ?";

PreparedStatement ps = con.prepareStatement(sql); // con.createStatement() 대신 사용
// 일단 삽입한 sql문을 실행할 준비 시켜라.

Scanner sc = new Scanner(System.in);
System.out.print("이름(소문자) :");
String str_1 = sc.next();

// 1 -> '첫번째' 물음표에 str_1이 들어감.
ps.setString(1, str_1); 

// 준비한 sql문을 실행시켜라.
//con.prepareStatement(sql)에서 준비를 했기때문에
//executeQuery에 인자를 넣지 않아도 됨.
ResultSet rs = ps.executeQuery();
```

---
<br></br>

## INSERT문 사용하기(Create)
<br></br>

```java
Scanner sc = new Scanner(System.in);

String sql = "insert into teltable5 values(?,?,?,?)";
PreparedStatement ps = con.prepareStatement(sql);

int id = sc.nextInt();
String name = sc.next();
String phone = sc.next();
String date = sc.next();

ps.setInt(1, id);
ps.setString(2, name);
ps.setString(3, phone);
ps.setString(4, date);

// rowCnt : 반환되는 행 수
int rowCnt = ps.executeUpdate();// DB로 넣는 method 실행
                                // excuteQuery() -> 검색
                                // excuteUpdate() -> 갱신

System.out.print(rowCnt + "행 INSERT 완료!");
```
---
<br></br>
## UPDATE문 사용하기(Update)
<br></br>

```java
Scanner sc= new Scanner(System.in);

String sql = "update teltable5 set tel = ? where name = ?";

PreparedStatement ps = con.prepareStatement(sql);

System.out.print("이름 : ");
String name = sc.nextLine();

System.out.println();

System.out.print("수정할 번호 : ");
String phone = sc.nextLine();

ps.setString(1, phone);
ps.setString(2, name);

int rowCnt = ps.executeUpdate();
System.out.println(rowCnt + "행 Update"); //업데이트 행 갯수

```