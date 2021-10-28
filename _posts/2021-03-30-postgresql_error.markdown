---
title: Postgresql 서버 접속 오류
categories:
- Error
last_modified_at: 2021-03-30T14:00:00+09:00
toc: true
---

## Postgresql 서버 접속 오류

postgresql을 설치하는데에도 애를 먹었는데, 설치 후에 서버 접속이 안되는 오류에 부딪혔다.
pgAdmin4.exe를 실행 후, 페이지에 접속하여   PostgreSQL 13 서버 접속 > 비밀번호 입력 후 확인했더니, 아래와 같은 오류가 나온다.

could not connect to server: connection refused (0x0000274d/10061) is the server running on host "localhost" (::1) and accepting tcp/ip connections on port 5432? could not connect to server: connection refused (0x0000274d/10061) is the server running on host "localhost" (127.0.0.1) and accepting tcp/ip connections on port 5432?
{: .notice--danger}

### Solution
1. Window키 + R
2. services.msc 입력
3. postgresql-x64-13 찾아서 클릭
4. 서비스 "시작" 클릭
5. 해결완료!




