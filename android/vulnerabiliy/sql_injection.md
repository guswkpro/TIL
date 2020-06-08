# SQL Injection

SQL Injection이란 db데이터를 SELECT, INSERT, UPDATE, DELETE 등의 기능을 사용하여 수정할 때, 비정상적인 query문을 넣어서 공격하는 방법이다.  
기존에 알고있던 공격 방법이라 서버 코딩을 할 때, 시큐어 코딩을 기본적으로 하고 있었는데, 문득 실제 어떠한 방식으로 시큐어 코딩이 동작하여 SQL Injection을 방어할 수 있는지 알아보기위해 몇가지 테스트를 해 보았다.  

우선적으로 기본적인 공격 방법으로 로그인 할 때 asdf" or 1=1과 같은 아이디와 비밀번호를 입력하여서 항상 true값을 만들어 제일 처음 회원가입한 회원의 아이디로 로그인 하거나( 이 경우 많은 user의 index가 불러와 질 텐데 제일 처음 값만 서버에서 사용한다고 가정 )  
회원의 정보를 받는 페이지에서 내 정보 뿐만 아니라 db에 저장된 모든 정보를 받아오게 한다던지, 테이블을 삭제시켜 디비를 날려버리는 행위 등의 기본적인 공격 기법이 있다.<br>
이를 막기위해서 사용되는 기본적인 시큐어 코딩에는 query문을 입력할 때 영향을 주는 문자들앞에 \ ( 역슬래쉬 ) 를 강제로 삽입시켜 쿼리문에 에러를 유도하는 방법이다.

예를들어, 
> var sql = 'SELECT * FROM mydb.test_users where user_id = "' + req.param("user_id") + '"';

같은 방식으로 string을 구성하여 sql문을 넣을 때 ( 위 쿼리문은 특정 유저의 정보를 모두 불러오는 쿼리문이다. ), asdf" or "1"="1이라는 user_id파라미터를 주게 된다면 실제 만들어지는 쿼리문은

> var sql = 'SELECT * FROM mydb.test_users where user_id = "asdf" or "1"="1"'

이 만들어지게 된다.<br>
이렇게될 경우 user_id의 값이 asdf이거나 "1"="1"인 값을 '모두'불러와라 라는 쿼리문이 만들어지므로<br>
test_users테이블에 있는 모든 유저의 정보를 받아오게 된다. 따라서 상당히 취약한 부분이다.<br>
이를 해결하기 위해서 mysql.escape(req.param("user_id"))와 같은 방식으로 해결할 수 있다.<br>
이 방식을 사용하게 되면 똑같은 문자열을 넣었을 때
> var sql = 'SELECT * FROM mydb.test_users where user_id = "asdf\" or \"1\"=\"1"'

이런식의 쿼리문이 나와 에러를 유도하게 된다.<br>
개발자는 위와같은 상황에 항상 유의해야 할 것이다.
