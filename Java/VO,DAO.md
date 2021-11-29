# VO

* VO : Value Object
* DTO와 동일한 개념이지만 read only 속성을 가짐
* 순수한 데이터 객체로 getter,setter 메소드만 가진 클래스임.

```java

public class EmployeesInfoVO {
	
    //employees테이블의 속성값
	private String firstName;
	private String lastName;
	private String hireDate;
    //...etc
	
	public EmployeesInfoVO(String firstName, String lastName, String hireDate) {
		this.firstName = firstName;
		this.lastName = lastName;
		this.hireDate = hireDate;
	}
	
	public String getFirstName() {
		return firstName;
	}
	
	public void setFirstName(String firstName) {
		this.firstName = firstName;
	}
	
	public String getLastName() {
		return lastName;
	}
	
	public void setLastName(String lastName) {
		this.lastName = lastName;
	}
	
	public String getHireDate() {
		return hireDate;
	}
	
	public void setHireDate(String hireDate) {
		this.hireDate = hireDate;
	}

	
}
```

<br></br>
# DAO

* DAO : Data Access Object로서 DB의 data에 접근을 위한 객체
* 데이터를 조회하거나 조작하는 기능을 담당(CRUD)

```java
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.PreparedStatement;
import java.sql.ResultSet;
import java.sql.SQLException;
import java.util.ArrayList;

public class employeesInfoDAO {
	
    String driver = "oracle.jdbc.driver.OracleDriver";
    String url = "jdbc:oracle:thin:@localhost:1521:XE";
    String dbId = "hr";
    String dbPassword = "oracle";
	
	private Connection con = null;
	private PreparedStatement ps = null;
	private ResultSet rs = null;
	
    //클래스 호출시 DB에 접근
	public employeesInfoDAO() throws SQLException, ClassNotFoundException {
		Class.forName(driver);
		this.con = DriverManager.getConnection(url, dbId, dbPassword);
	}
	
    //READ
    //이름을 검색하여 원하는 데이터 추출
	public ArrayList<EmployeesInfoVO> read(String str) throws SQLException{
		
        //VO-type ArrayList 생성
		ArrayList<EmployeesInfoVO> evArray = new ArrayList<EmployeesInfoVO>();

		String sql = "select first_name, last_name, hire_date from employees" + " where lower(first_name) = ?";
		
		ps = con.prepareStatement(sql);
		
		ps.setString(1, str);
		
		//검색 실행
		rs = ps.executeQuery();
		
		//검색 결과를 EmployeesInfoVO에 저장
		while(rs.next()) {
			String firstName = rs.getString("first_name");
			String lastName = rs.getString("last_name");
			String hireDate = rs.getString("hire_date");
			
			EmployeesInfoVO ev = new EmployeesInfoVO(firstName, lastName, hireDate);
			
			evArray.add(ev);
			
		}
		
		//ArrayList로 결과값 보내기(VO 사용)
		return evArray;
	}
	
    //테이블 내의 모든 데이터 추출
	public ArrayList<EmployeesInfoVO> readAll() throws SQLException{
		
		ArrayList<EmployeesInfoVO> evArray = new ArrayList<EmployeesInfoVO>();
		
		String sql = "select * from employees";
		
		ps = con.prepareStatement(sql);
		rs = ps.executeQuery();
		
		while(rs.next()) {
			String firstName = rs.getString("first_name");
			String lastName = rs.getString("last_name");
			String hireDate = rs.getString("hire_date").substring(0, 10);
			
			EmployeesInfoVO ev = new EmployeesInfoVO(firstName, lastName, hireDate);
			
			evArray.add(ev);
			
		}
		
		//ArrayList로 결과값 보내기(VO 사용)
		return evArray;
	}

    //DELETE
    //...

    //CREATE
    //...

    //UPDATE
    //...

    //DB접속 종료
	public void close() throws SQLException {
		if(con!=null) con.close();
	}
}
```
<br></br>
### tip
* commit명령어를 입력하지 않아도 eclipse에서 자동으로 commit 해줌!!