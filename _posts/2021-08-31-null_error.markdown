---
title: DB에 필드값 존재하는데 null값으로 나올 때
categories:
- Error
last_modified_at: 2021-08-31T14:00:00+09:00
toc: true
---

## DB에 필드값 존재하는데 null값으로 나올 때

DB로부터 data를 가져와 화면에 출력하는 과정에서 문제가 발생했다.<br>
DB에는 분명 존재하는 값인데, null로 출력이 되었다.

문제는 DTO에 있었다. <br>
DTO에서 멤버 변수를 DB와 이름이 같게, 스네이크형식으로 작성했던 것을 카멜형식으로 바꾸었더니 NULL값이 아닌, 해당 컬럼의 필드값이 출력되었다.

---

**DB 컬럼명**은 보통 스네이크 형식으로 **board_name** 처럼 작성한다. <br>
**자바에서 객체의 멤버 변수** 이름은 카멜 형식으로 **boardName** 처럼 작성한다.

그리고 쿼리의 결과 컬럼과 DTO클래스의 멤버변수가 자동으로 매핑되도록 
application.properties에 아래의 설정을 추가해준다.

```
#MyBatis
mybatis.configuration.map-underscore-to-camel-case=true
```





