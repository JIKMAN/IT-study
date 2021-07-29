## netstat 명령어를 통한 네트워크 상태 확인 방법

**netstat - 네트워크 접속, 라우팅 테이블, 네트워크 인터페이스의 통계 정보를 보여주는 도구**

**사용 방법** :
`netstat [옵션] [| grep 포트 번호 or 서비스 명]`

**option** : 
-l (listen) : 연결 가능한 상태
-n (number port) : 포트 넘버
-t (tcp) : tcp
-u (udp) : udp
-p : 프로그램 이름 / PID
-a : 모두
-i : 이더넷 카드별 정상/에러/드랍 송수신 패킷 수 확인
-r : 라우팅 테이블
-s : 네트워크 통계

![img](https://postfiles.pstatic.net/MjAxODEwMzBfMTY3/MDAxNTQwODczNDMwNjIx.POeqHMb1eKwbtoOLyDc9NbiY4PYElzdXsQpg8Htzsy0g.IV7VLhXAahXXd8H_rg2m6EwNHRIGjeCCCFfNbilT-lYg.PNG.ncloud24/image.png?type=w773)

netstat --help를 치면 옵션에 대한 정보를 볼 수 있다.

**자주 사용 하는 옵션**

* `netstat -nap` : 연결을 기다리는 목록과 프로그램을 보여준다

![img](https://postfiles.pstatic.net/MjAxODEwMzBfMTEy/MDAxNTQwODc4NDU0MjQ4.LRAcTDA8qVmo9Cm0JFRHTk8mvZHh7M8WFa8j1pfAhtAg.z0MUXQyoQbbfZuzyytZzpbd9-R43wDwvoCyXTBpMt6kg.PNG.ncloud24/image.png?type=w773)


* `netstat -an | grep 포트번호` : 특정 포트가 사용 중에 있는지 확인 

![img](https://postfiles.pstatic.net/MjAxODEwMzBfMTEy/MDAxNTQwODc5MDUxNDcy.pv8MbkDySRT29225KTAP4uNIiUVIOF5zNxLy4dzaRXkg.qjtGzn9ngVbFhmXkg00OlLTyqwRR1TNqpkBrsMnROgEg.PNG.ncloud24/image.png?type=w773)


* `netstat -nlpt` : TCP listening 상태의 포트와 프로그램을 보여준다

![img](https://postfiles.pstatic.net/MjAxODEwMzBfMjI5/MDAxNTQwODc5MjE4ODMy.NTA0-ALdLoRfXo9LJ4yZPGNX-iPhpGupeUd2gPzE48wg.9wWCh4HvSEDfgPL97P6b8l_UjBu8MRk0i4JpUXOj5NQg.PNG.ncloud24/image.png?type=w773)



netstat 상태 값

| **State**    | **description**                                              |
| ------------ | ------------------------------------------------------------ |
| CLOSED       | 완전히 연결이 종료된 상태                                    |
| CLOSING      | 흔하지 않으나 주로 확인 메시지가 전송 도중 유실된 상태       |
| CLOSE_WAIT   | TCP 연결이 상위 응용프로그램 레벨로부터 연결 종료를 기다리는 상태 |
| ESTABLISHED  | 서버와 클라이언트 간에 세션 연결이 성립되어 통신이 이루어지고 있는 상태 (클라이언트가 서버의 SYN을 받아서 세션이 연결된 상태) |
| FIN_WAIT1    | 클라이언트가 서버에게 연결을 끊고자 요청하는 상태(FIN을 보낸 상태) |
| FIN_WAIT2    | 서버가 클라이언트로부터 연결 종료 응답을 기다리는 상태 (서버가 클라이언트로부터 최초로 FIN을 받은 후, 클라이언트에게 ACK를 주었을 때 |
| LAST_ACK     | 호스트가 원격지 호스트의 연결 종료 요구 승인을 기다리는 상태 (서버가 클라이언트에게 FIN을 보냈을 때의 상태) |
| LISTEN       | 서버의 데몬이 떠 있어서 클라이언트의 접속 요청을 기다리고 있는 상태 |
| SYN_SENT     | 클라이언트가 서버에게 연결을 요청한 상태                     |
| SYN_RECEIVED | 서버가 클라이언트로부터 접속 요구(SYN)을 받아 클라이언트에게 응답(SYN/ACK)하였지만, 아직 클라이언트에게 확인 메시지(ACK)는 받지 못한 상태 |
| TIME_WAIT    | 연결은 종결되었지만 당분간 소켓을 열어 놓은 상태, 약 1분 정도이며 시간이 지나면 사라짐 |
| UNKNOWN      | 소켓의 상태를 알 수 없음                                     |

![img](https://postfiles.pstatic.net/MjAxODEwMzBfMjQg/MDAxNTQwODg2NTkzMTU2.C5FCYqxmW32NBJZh7EOzWVuyHMOz2Xf8dK4XQ9ZBlbIg.X2xE9i5eRmepCuJzC2VxNJwPQZFosFgMm4FISdEiJlcg.PNG.ncloud24/2018-10-30_16%3B57%3B31.PNG?type=w773)

SYN_RECV 상태로 유입이 있는 경우

상위와 같이 웹서버에 요청을 하고 연결을 끊어버리는 공격을 당하면 웹서버는 이에 대한 대기 상태로 남아있게 됩니다.
웹서버의 자원이 무한대로 지원이 되지 않기 때문에 이런 상태가 늘어나게 되면 웹서버 자원 부족으로 인한 웹서비스 지연 및 기타 서비스들에 대한 자원 부족 문제로 hang 상태로 빠지게 되는 상황까지 이를 수 있습니다.

특히 동일 IP에 대한 유입이 과다한 상태인경우 해당 IP를 차단하시길 바랍니다.



* 출처 : https://blog.naver.com/ncloud24/221388026417