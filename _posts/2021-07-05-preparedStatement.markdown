---
title: PreparedStatement
categories:
- Java
last_modified_at: 2021-07-05T14:00:00+09:00
toc: true
---
## Statement 클래스
- SQL 구문을 실행하는 역할
- 스스로는 SQL 구문 해석 X -> 전달 역할
- SQL 관리 O, 연결 정보 X

## PreparedStatement 클래스
- Statement 클래스의 기능 향상(SQL 구문 실행)
- 인자와 관련된 작업에 특화(매개변수)
- 코드 안정성 높음, 가독성 높음
- 코드량 증가 -> 매개변수 set 해줘야 함
- 텍스트 SQL 호출


```java
private Connection conn;
private PreparedStatement pstmt;

String SQL = "INSERT INTO user VALUES (?,?,?,?);";
pstmt = conn.preparedStatement(SQL);

// 매개변수 값 대입 + 매개변수 유효화 처리
pstmt.setString(1, userName);
pstmt.setString(2, userAge);
pstmt.setString(3, userGender);
pstmt.setString(4, userEmail);
```
