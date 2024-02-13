### Computer Network

<details>
<summary>📚 공부한 자료</summary>

- 네트워크 하향식 접근
- HTTP 완벽 가이드
- 성공과 실패를 결정하는 1%의 네트워크 원리

</details>

### **1. 쿠키와 세션의 차이에 대해 설명해 주세요.**

HTTP 는 connectionless 프로토콜이다. 즉, 클라이언트가 서버에 요청을 했을 때, 그 요청에 맞는 응답을 보낸 후 연결을 끊는 방식이다. 그러나 HTTP 1.1 버전에서는 커넥션을 유지하는 keep-alive 가 디폴트 옵션이 되었다. 또한, stateless 프로토콜로, 커넥션을 끊는 순간 클라 - 서버의 통신이 끝나며 상태 정보는 유지하지 않는다. 하지만 매번 페이지를 넘길 때마다 로그인을 해야 하는 번거로움을 없애기 위해, 즉 stateful 경우를 대처하기 위해 쿠키와 세션을 사용한다. 쿠키는 클라이언트에 저장하며 서버의 자원을 전혀 사용하지 않으며, 세션은 서버에 저장한다.

- **쿠키(Cookies):**
  - 클라이언트 측에서 사용자의 브라우저에 저장되는 작은 데이터 조각입니다. 웹사이트 방문 정보, 사용자 선호도 등을 저장하여 웹사이트 사용자 경험을 개인화합니다.
  - 쿠키는 사용자가 다시 웹사이트를 방문할 때마다 서버에 전송되어, 사용자를 식별하고 상태 정보를 유지하는 데 사용됩니다.
  - 그러나 클라이언트 로컬에 저장되기 때문에 변질되거나 request 에서 스니핑 당할 우려가 있어서 보안에 취약하다.
- **세션(Sessions):**
  - 서버 측에서 사용자 정보를 저장합니다. 세션 ID를 쿠키에 저장하여 클라이언트와 서버 간의 상태를 유지합니다.
  - 사용자가 웹사이트를 탐색할 때, 서버는 세션 ID를 통해 사용자의 상태와 데이터를 유지 관리합니다.
  - 세션은 쿠키를 이용해서 session-id 만 저장하고 그것으로 구분하여 서버에서 처리하기 때문에 비교적 보안성이 높다.
- **세션 방식의 로그인 과정에 대해 설명해 주세요.**
- 1. **로그인 요청:** 사용자가 로그인 정보(예: 사용자명과 비밀번호)를 입력하여 서버에 전송합니다.
  2. **인증:** 서버는 제공된 로그인 정보를 검증합니다.
  3. **세션 생성:** 인증이 성공하면, 서버는 해당 사용자에 대한 세션을 생성하고, 고유한 세션 ID를 발급합니다.
  4. **세션 ID 저장:** 발급된 세션 ID는 쿠키에 저장되어 클라이언트(브라우저)로 전송됩니다.
  5. **세션 사용:** 사용자가 이후 요청을 할 때마다 브라우저는 세션 ID가 포함된 쿠키를 서버에 전송합니다. 서버는 이 세션 ID를 통해 사용자를 식별하고, 상태 정보를 유지합니다.

- **HTTP의 특성인 Stateless에 대해 설명해 주세요.**
  - HTTP 프로토콜은 **Stateless**로 설계되었습니다. 이는 각 요청이 독립적이며 서로 연결되어 있지 않다는 것을 의미합니다. 서버는 클라이언트의 이전 상태나 요청 정보를 기억하지 않습니다. 이로 인해 웹은 기본적으로 사용자의 상태 정보를 유지하지 않는 환경입니다.
- **Stateless의 의미를 살펴보면, 세션은 적절하지 않은 인증 방법 아닌가요?**
- **규모가 커져 서버가 여러 개가 된다면, 세션을 어떻게 관리할 수 있을까요?**
- **토큰 기반 방식은 어떤 장점이 있을까요?**

### **2. HTTP 응답코드에 대해 설명해 주세요.**

- **401 (Unauthorized) 와 403 (Forbidden)은 의미적으로 어떤 차이가 있나요?**
- **200 (ok) 와 201 (created) 의 차이에 대해 설명해 주세요.**
- **필요하다면 저희가 직접 응답코드를 정의해서 사용할 수 있을까요? 예를 들어 285번 처럼요.**

### **3. HTTP Method 에 대해 설명해 주세요.**

- **HTTP Method의 멱등성에 대해 설명해 주세요.**
- **GET과 POST의 차이는 무엇인가요?**
- **POST와 PUT, PATCH의 차이는 무엇인가요?**
- **HTTP 1.1 이후로, GET에도 Body에 데이터를 실을 수 있게 되었습니다. 그럼에도 불구하고 왜 아직도 이런 방식을 지양하는 것일까요?**

### **4. HTTP에 대해 설명해 주세요.**

- **공개키와 대칭키에 대해 설명해 주세요.**
- **왜 HTTPS Handshake 과정에서는 인증서를 사용하는 것 일까요?**
- **SSL과 TLS의 차이는 무엇인가요?**

### **5. 웹소켓과 소켓 통신의 차이에 대해 설명해 주세요.**

- **소켓과 포트의 차이가 무엇인가요?**
- **여러 소켓이 있다고 할 때, 그 소켓의 포트 번호는 모두 다른가요?**
- **사용자의 요청이 무수히 많아지면, 소켓도 무수히 생성되나요?**

### **6. HTTP/1.1과 HTTP/2의 차이점은 무엇인가요?**

- **HOL Blocking 에 대해 설명해 주세요.**
- **HTTP/3.0의 주요 특징에 대해 설명해 주세요.**

### **7. TCP와 UDP의 차이에 대해 설명해 주세요.**

- **Checksum이 무엇인가요?**
- **TCP와 UDP 중 어느 프로토콜이 Checksum을 수행할까요?**
- **그렇다면, Checksum을 통해 오류를 정정할 수 있나요?**
- **TCP가 신뢰성을 보장하는 방법에 대해 설명해 주세요.**
- **TCP의 혼잡 제어 처리 방법에 대해 설명해 주세요.**
- **왜 HTTP는 TCP를 사용하나요?**
- **그렇다면, 왜 HTTP/3 에서는 UDP를 사용하나요? 위에서 언급한 UDP의 문제가 해결되었나요?**
- **그런데, 브라우저는 어떤 서버가 TCP를 쓰는지 UDP를 쓰는지 어떻게 알 수 있나요?**
- **본인이 새로운 통신 프로토콜을 TCP나 UDP를 사용해서 구현한다고 하면, 어떤 기준으로 프로토콜을 선택하시겠어요?**

### **8. DHCP가 무엇인지 설명해 주세요.**

- **DHCP는 몇 계층 프로토콜인가요?**
- **DHCP는 어떻게 동작하나요?**
- **DHCP에서 UDP를 사용하는 이유가 무엇인가요?**
- **DHCP에서, IP 주소 말고 추가로 제공해주는 정보가 있나요?**
- **DHCP의 유효기간은 얼마나 긴가요?**

### **9. IP 주소는 무엇이며, 어떤 기능을 하고 있나요?**

- **IPv6는 IPv4의 주소 고갈 문제를 해결하기 위해 만들어졌지만, 아직도 수많은 기기가 IPv4를 사용하고 있습니다. 고갈 문제를 어떻게 해결할 수 있을까요?**
- **IPv4와 IPv6의 차이에 대해 설명해 주세요.**
- **수많은 사람들이 유동 IP를 사용하고 있지만, 수많은 공유기에서는 고정 주소를 제공하는 기능이 이미 존재합니다. 어떻게 가능한 걸까요?**
- **IPv4를 사용하는 장비와 IPv6를 사용하는 같은 네트워크 내에서 통신이 가능한가요? 가능하다면 어떤 방법을 사용하나요?**
- **IP가 송신자와 수신자를 정확하게 전송되는 것을 보장해 주나요?**
- **IPv4에서 수행하는 Checksum과 TCP에서 수행하는 Checksum은 어떤 차이가 있나요?**
- **TTL(Hop Limit)이란 무엇인가요?**
- **IP 주소와 MAC 주소의 차이에 대해 설명해 주세요.**

### **10. OSI 7계층에 대해 설명해 주세요.**

- **Transport Layer와, Network Layer의 차이에 대해 설명해 주세요.**
- **L3 Switch와 Router의 차이에 대해 설명해 주세요.**
- **각 Layer는 패킷을 어떻게 명칭하나요? 예를 들어, Transport Layer의 경우 Segment라 부릅니다.**
- **각각의 Header의 Packing Order에 대해 설명해 주세요.**
- **ARP에 대해 설명해 주세요.**

### **11. 3-Way Handshake에 대해 설명해 주세요.**

- **ACK, SYN 같은 정보는 어떻게 전달하는 것 일까요?**
- **2-Way Handshaking 를 하지않는 이유에 대해 설명해 주세요.**
- **두 호스트가 동시에 연결을 시도하면, 연결이 가능한가요? 가능하다면 어떻게 통신 연결을 수행하나요?**
- **SYN Flooding 에 대해 설명해 주세요.**
- **위 질문과 모순될 수 있지만, 3-Way Handshake의 속도 문제 때문에 이동 수를 줄이는 0-RTT 기법을 많이 적용하고 있습니다. 어떤 방식으로 가능한 걸까요?**

### **12. 4-Way Handshake에 대해 설명해 주세요.**

- **패킷이 4-way handshake 목적인지 어떻게 파악할 수 있을까요?**
- **빨리 끊어야 할 경우엔, (즉, 4-way Handshake를 할 여유가 없다면) 어떻게 종료할 수 있을까요?**
- **4-Way Handshake 과정에서 중간에 한쪽 네트워크가 강제로 종료된다면, 반대쪽은 이를 어떻게 인식할 수 있을까요?**
- **왜 종료 후에 바로 끝나지 않고, TIME_WAIT 상태로 대기하는 것 일까요?**

### **13. [www.github.com을](http://www.github.xn--com-of0o/) 브라우저에 입력하고 엔터를 쳤을 때, 네트워크 상 어떤 일이 일어나는지 최대한 자세하게 설명해 주세요.**

- **DNS 쿼리를 통해 얻어진 IP는 어디를 가리키고 있나요?**
- **Web Server와 Web Application Server의 차이에 대해 설명해 주세요.**
- **URL, URI, URN은 어떤 차이가 있나요?**

### **14. DNS에 대해 설명해 주세요.**

- **DNS는 몇 계층 프로토콜인가요?**
- **UDP와 TCP 중 어떤 것을 사용하나요?**
- **DNS Recursive Query, Iterative Query가 무엇인가요?**
- **DNS 쿼리 과정에서 손실이 발생한다면, 어떻게 처리하나요?**
- **캐싱된 DNS 쿼리가 잘못 될 수도 있습니다. 이 경우, 어떻게 에러를 보정할 수 있나요?**
- **DNS 레코드 타입 중 A, CNAME, AAAA의 차이에 대해서 설명해주세요.**
- **hosts 파일은 어떤 역할을 하나요? DNS와 비교하였을 때 어떤 것이 우선순위가 더 높나요?**

### **15. SOP 정책에 대해 설명해 주세요.**

- **CORS 정책이 무엇인가요?**
- **Preflight에 대해 설명해 주세요.**

### **16. Stateless와 Connectionless에 대해 설명해 주세요.**

- **왜 HTTP는 Stateless 구조를 채택하고 있을까요?**
- **Connectionless의 논리대로면 성능이 되게 좋지 않을 것으로 보이는데, 해결 방법이 있을까요?**
- **TCP의 keep-alive와 HTTP의 keep-alive의 차이는 무엇인가요?**

### **17. 라우터 내의 포워딩 과정에 대해 설명해 주세요.**

- **라우팅과 포워딩의 차이는 무엇인가요?**
- **라우팅 알고리즘에 대해 설명해 주세요.**
- **포워딩 테이블의 구조에 대해 설명해 주세요.**

### **18. 로드밸런서가 무엇인가요?**

- **L4 로드밸런서와, L7 로드밸런서의 차이에 대해 설명해 주세요.**
- **로드밸런서 알고리즘에 대해 설명해 주세요.**
- **로드밸런싱 대상이 되는 장치중 일부 장치가 문제가 생겨 접속이 불가능하다고 가정해 봅시다. 이 경우, 로드밸런서가 해당 장비로 요청을 보내지 않도록 하려면 어떻게 해야 할까요?**
- **로드밸런서 장치를 사용하지 않고, DNS를 활용해서 유사하게 로드밸런싱을 하는 방법에 대해 설명해 주세요.**

### **19. 서브넷 마스크와, 게이트웨이에 대해 설명해 주세요.**

- **NAT에 대해 설명해 주세요.**
- **서브넷 마스크의 표현 방식에 대해 설명해 주세요.**
- **그렇다면, 255.0.255.0 같은 꼴의 서브넷 마스크도 가능한가요?**

### **20. 멀티플렉싱과 디멀티플렉싱에 대해 설명해 주세요.**

- **디멀티플렉싱의 과정에 대해 설명해 주세요.**

### **21. XSS에 대해서 설명해 주세요.**

- **CSRF랑 XSS는 어떤 차이가 있나요?**
- **XSS는 프론트엔드에서만 막을 수 있나요?**

### **22. HTTPS 는 HTTP 와 어떻게 다른가요?**

HTTP(Hypertext Transfer Protocol)는 클라이언트와 서버 간 통신을 위한 통신 규칙 세트 또는 프로토콜입니다. 사용자가 웹 사이트를 방문하면 사용자 브라우저가 웹 서버에 HTTP 요청을 전송하고 웹 서버는 HTTP 응답으로 응답합니다. 웹 서버와 사용자 브라우저는 데이터를 일반 텍스트로 교환합니다. 간단히 말해 HTTP 프로토콜은 네트워크 통신을 작동하게 하는 기본 기술입니다.

이름에서 알 수 있듯이 HTTPS(Hypertext Transfer Protocol Secure)는 HTTP의 확장 버전 또는 더 안전한 버전입니다. HTTPS에서는 브라우저와 서버가 데이터를 전송하기 전에 안전하고 암호화된 연결을 설정합니다.

- **HTTP 프로토콜은 어떻게 작동하나요?**
  - HTTP는 OSI(Open Systems Interconnection) 네트워크 통신 모델의 애플리케이션 계층 프로토콜입니다. HTTP는 여러 유형의 요청과 응답을 정의합니다. 예를 들어, 웹 사이트의 일부 데이터를 보려는 경우 *HTTP GET* 요청을 전송합니다. 연락처 양식 작성과 같은 일부 정보를 전송하려는 경우 *HTTP PUT* 요청을 전송합니다.
- **HTTPS 프로토콜은 어떻게 작동하나요?**
  - HTTPS는 HTTP 요청 및 응답을 SSL 및 TLS 기술에 결합합니다.
  - SSL 인증서는 사용자가 사이트에 제공하는 정보를 암호화하는데, 쉽게 말해서 데이터를 암호로 바꾼다고 생각하면 쉽습니다. 이렇게 전송된 데이터는 중간에서 누군가 훔쳐 낸다고 하더라도 데이터가 암호화되어있기 때문에 해독할 수 없습니다. 그 외에도 HTTPS는 TLS(전송 계층 보안) 프로토콜을 통해서도 보안을 유지합니다.
- **TLS 기술은 무엇인가요?**
  - Transport Layer Security. 대칭키를 사용해서 암호화한다.

### **23. REST API 는 무엇인가요?**

### **24. 토큰 기반 인증 과 쿠키 / 세션 이용한 인증의 차이는 무엇인가요?**