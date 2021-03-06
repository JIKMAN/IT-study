## TCP/IP 프로토콜이란?

[**TCP/IP**](https://ko.wikipedia.org/wiki/TCP/IP)**는** 패킷 통신 방식의 인터넷 프로토콜인 [**IP**](https://ko.wikipedia.org/wiki/인터넷_프로토콜) (인터넷 프로토콜)와 전송 조절 프로토콜인 [**TCP**](https://ko.wikipedia.org/wiki/전송_제어_프로토콜) (전송 제어 프로토콜)로 이루어져 있다. 

**IP**는 패킷 전달 여부를 보증하지 않고, 패킷을 보낸 순서와 받는 순서가 다를 수 있다.

(unreliable datagram service) 

**TCP**는 IP 위에서 동작하는 프로토콜로, 데이터의 전달을 보증하고 보낸 순서대로 받게 해준다. 

[HTTP](https://ko.wikipedia.org/wiki/HTTP), [FTP](https://ko.wikipedia.org/wiki/파일_전송_프로토콜), [SMTP](https://ko.wikipedia.org/wiki/SMTP) 등 TCP를 기반으로 한 많은 수의 애플리케이션 프로토콜들이 IP 위에서 동작하기 때문에, 묶어서 TCP/IP로 부르기도 한다. 

---

> #### TCP/IP 프로토콜의 구조

인터넷을 통해 통신을 수행하는 개체는 크게 **호스트**와 **라우터**로 나눌 수 있습니다.

 

**호스트**(host)는 최종 사용자(end-user) 응용 프로그램을 수행하는 주체가 되며,

인터넷에 연결된 PC , 노트북 , 휴대전화 , PDA 등이 여기에 속합니다.



**라우터**(router)는 호스트에서 생성된 데이터를 여러 네트워크를 거쳐 전송함으로써 서로 다른 네트워크에 속한 호스트 간에 데이터를 교환할 수 있게 하는 장비입니다.



호스트와 라우터, 라우터와 라우터 그리고 호스트와 호스트가 통신하려면 정해진 절차와 방법을 따라야 하는데 이를 **통신 프로토콜**(communication protocol : 프로토콜)이라 부릅니다.



인터넷에서 사용하는 핵심 프로토클은 **TCP**와 **IP**로, 이를 비롯한 각종 프로토콜을 총칭하여

**TCP/IP 프로토콜**이라 부릅니다.



**TCP/IP 프로토콜은** 일반적으로 운영체제의 일부로 구현되며, 응용 프로그램은 운영체제가 제공하는 TCP/IP 프로토콜의 서비스를 사용해 통신합니다.

![라우터](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=http%3A%2F%2Fcfile24.uf.tistory.com%2Fimage%2F214BF13958E523A43376D5)

일반적으로 프로토콜은 기능별로 나누어 계층적으로 구현합니다.

TCP/IP 프로토콜도 이 구조를 따릅니다.

![계층구조](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=http%3A%2F%2Fcfile7.uf.tistory.com%2Fimage%2F245EC83958E523A40F50FC)