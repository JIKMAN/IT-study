## FTP의 의미

FTP란 파일 전송 프로토콜(File Transfer Protocol)의 약자입니다. 그 의미를 자세히 살펴봅시다. 기본적으로 '프로토콜'은 전자기기가 서로 통신하는 데 필요한 절차나 규칙을 뜻하죠. FTP는 TCP/IP 네트워크(인터넷)상의 장치가 파일을 전송할 때 사용하는 규칙입니다. 인터넷을 사용할 때 우리는 다양한 프로토콜을 사용합니다. 인터넷을 둘러볼 때는 HTTP를 사용하고, 인스턴트 메시지를 주고받을 때는 XMPP를 사용하죠. 간단히 말해 FTP란 파일을 이동할 때 사용하는 프로토콜이라고 보시면 됩니다.

## FTP 서버란?

FTP 서버란 파일을 하나의 장치에서 다른 장치로 전송하는 소프트웨어 애플리케이션을 말합니다. 복잡하게 들릴 수도 있지만, 기본적으로 FTP 서버는 FTP 주소를 가지고 있고 FTP 연결을 수신하는 데 사용되는 컴퓨터라고 생각하시면 됩니다. FTP 서버는 두 가지 간단한 작업을 실행합니다. '받기'와 '보내기'가 바로 그것이죠. 간단히 말해 우리는 FTP 서버로부터 파일을 '받거나', FTP 서버로 파일을 '보냅니다'. 우리가 파일을 업로드하면 업로드된 파일이 내 개인용 장치에서 서버로 전송되고, 우리가 파일을 다운로드하면 다운로드된 파일이 서버에서 개인용 장치로 전송되죠. 따라서 기본적인 관점에서 보면 FTP 서버는 수신자와 전송자 사이에 위치한 중간 지점과 같습니다.

## FTP의 원리

FTP는 클라이언트-서버 프로토콜입니다. 클라이언트가 파일을 요청하면 서버가 요청된 파일을 제공하죠. 따라서 FTP의 연결 설정을 위해서는 2개의 기본 채널이 필요합니다. 하나는 명령을 내리고 어떤 파일에 액세스할 수 있는지 등의 기본 정보를 전달하는 명령 채널이고, 다른 하나는 2개의 장치 간에 파일 데이터를 전송하는 데이터 채널입니다. 연결을 설정하려면 사용자는 FTP 서버로의 로그인 정보를 제공해야 하는데, 일반적으로는 21번 포트를 기본 통신 모드로 사용합니다. FTP에 관해 알아야 할 또 다른 점은 FTP의 연결 모드에는 능동 모드, 수동 모드 2가지가 있다는 것입니다.

능동 모드에서는 서버가 데이터 요청을 승인하는 능동적인 역할을 합니다. 하지만 능동 모드에서는 방화벽으로 인한 문제가 종종 발생합니다. 제삼자가 권한이 없는 세션에 액세스하려고 하면 해당 세션이 차단되죠. 수동 모드가 제 역할을 발휘하는 순간이 바로 이때입니다. 수동 모드에서는 서버가 능동적으로 연결을 유지하지 않습니다. 즉, 사용자가 데이터 채널과 명령 채널 모두를 설정하죠. 서버는 기본적으로 '듣기만' 할 뿐, 적극적으로 관여하지 않음으로써 다른 장치가 대부분의 작업을 처리하도록 합니다.

## FTP가 유용하게 사용되는 경우

FTP는 주로 대량의 파일을 처리할 때 사용됩니다. 그래서 웹 개발 시 특히 유용하죠. 웹사이트를 수정할 때 FTP 세션을 통해 파일 전송을 관리하면 특정한 파일 업로드, 이미지 파일 추가, 웹 템플릿 이동 등의 작업을 수월하게 처리할 수 있습니다. 이와 유사하게 IT 전문가들도 FTP를 통해 폐쇄형 시스템 내에서 대량의 서버 배치 파일을 간단하게 전송할 수 있죠.

## FTP의 장단점

FTP에는 꼭 알아야 할 몇 가지 장점이 있습니다. FTP는 세상에 첫선을 보인 지 오래된 프로토콜이기 때문에 이미 대부분의 사람들이 이에 대해 잘 알고 있고, FileZilla, WinSCP, Cyberduck 등 FTP를 보다 간편하게 사용할 수 있는 데스크톱 도구도 다양하게 나와 있죠. 또한, 여러 개의 파일을 동시에 전송할 수 있고, 연결이 끊긴 경우 전송을 다시 시작할 수 있으며, 전송 일정을 예약할 수 있다는 것도 FTP의 유용한 점입니다.

하지만 FTP와 관련된 가장 치명적인 단점은 바로 보안이 약하다는 것입니다. FTP는 오늘날 우리가 사용하는 대부분의 사이버 보안 조치가 개발된 시기보다 앞선 1970년대에 개발되었습니다. 보안 프로토콜로 설계된 것이 아니기 때문에 FTP 전송은 파일을 암호화하지 않습니다. 그래서 데이터 패킷을 캡처하려는 해커들이 패킷 캡처 공격을 통해 비교적 쉽게 비밀번호, 사용자 이름, 그 외 기타 민감한 데이터를 읽을 수 있죠.

이러한 보안상의 구멍으로 인해 오늘날에는 FTP에 대한 지원이 점점 줄어들고 있고, SFTP, HTTPS, AS2, FTPS처럼 FTP를 대체할 수 있는 옵션도 시장에 다양하게 출시되었습니다. Google Chrome의 경우 2020년부터 FTP 지원을 중단했고, Firefox도 FTP 관련 코드를 모두 삭제했죠. 그러니 여전히 FTP 서버를 중요한 비즈니스 기능으로 사용하고 있다면 지금이 바로 대안을 찾기에 적기입니다. 지금부터는 FTP의 대안 중 하나인 SFTP를 조금 더 자세히 살펴보도록 하겠습니다.

## SFTP란?

FTP에 관한 정보를 검색해 본 사람이라면 'SFTP'라는 용어도 한 번은 들어봤을 겁니다. 그렇다면 SFTP란 과연 무엇일까요? 기본적으로 SFTP(SSH 파일 전송 프로토콜)란 시큐어 셸(SSH) 데이터 스트림을 통해 보안 등급이 높은 파일 전송을 실현하는 별도의 프로토콜을 말합니다. 21번 포트를 사용하는 FTP 클라이언트와는 달리 SFTP는 22번 포트를 사용하죠. FTP의 취약한 보안으로 인해 많은 사람이 보안 기능을 기본으로 제공하고 SSH 연결을 사용하는 SFTP를 선호합니다.

## FTP 서버의 대안: Dropbox 

FTP 지원이 점점 감소하고 사이버 보안 위협이 점점 정교해지는 오늘날, 비즈니스 파일로의 액세스, 전송, 관리를 지원하는 FTP 대안을 찾아보는 것은 중요합니다. 번거롭지 않은 안전한 방식의 [파일 공유](https://www.dropbox.com/features/share) 기능을 제공하는 Dropbox가 효율적인 [FTP 대안](https://www.dropbox.com/ftp)이 될 수 있습니다. 어떻게 Dropbox를 FTP 대신 사용할 수 있냐고요? 방법은 간단합니다. Dropbox Transfer는 대용량 파일 전송에 이상적인 안전하고 간편한 [파일 전송](https://www.dropbox.com/features/share/file-transfer) 서비스입니다. 받는 사람에게 Dropbox 계정이 있든 없든 누구에게나 최대 100GB의 파일을 전송할 수 있죠. 게다가 다운로드 알림이 전송되어 파일 전송 여부를 확인할 수 있고, 파일에 비밀번호를 설정해 지정한 사람만이 파일을 볼 수 있도록 액세스를 제어할 수도 있습니다.

## 결론

그렇다면 FTP란 과연 무엇일까요? FTP가 파일을 전송하는 효과적인 방법임에는 틀림없지만, 시대에 뒤처진 면이 있고, 오늘날에는 FTP의 기능을 능가하는 서비스형 SFTP 등과 같은 새로운 네트워크 프로토콜도 다양하게 찾아볼 수 있습니다. 게다가 빠르고 간편하게 대용량 파일이나 파일 모음을 전송하려는 비즈니스에 효과적인 파일 전송 솔루션을 제공하는 Dropbox도 있죠.



출처 - https://experience.dropbox.com/ko-kr/resources/what-is-ftp