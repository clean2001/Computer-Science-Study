## Infra

- 가상화, 도커, CI/CD, AWS

### **1. 가상화가 무엇이고, 이것이 가상머신과 어떠한 차이가 있는지 설명해 주세요.**

- **그렇다면 Docker는 둘 중 어디에 속하나요? 왜 사람들이 Docker를 많이 채택할까요?**
- **하나의 Host OS에서 돌아간다면 충분히 한 컨테이너가 다른 컨테이너에 간섭할 수 있는 위험이 있지 않을까요? 이를 어떻게 방어할 수 있을까요?**
- **Docker 위에 Docker를 올릴 순 없을까요?**
- **Docker Engine 은 무엇인가요?**

### **2. CI/CD 를 사용해 본 경험이 있나요? 있다면 간단하게 설명해 주세요.**

### **3. Web Server, Web Application Server 의 차이는 무엇인가요?**

- **Web Server 란?**
  - 클라이언트로부터 HTTP 요청을 받아 HTML 문서나 각종 리소스를 전달하는 컴퓨터. 정적인 데이터(html, css, 이미지) 만 넘겨줄 수 있다.
  - Apache, Nginx
- **WAS 란?**
  - Web Application : 웹 브라우저에서 이용할 수 있는 소프트웨어
  - 웹 어플리케이션과 서버 환경을 만들어 동작시키는 소프트웨어 프레임워크.
  - Web Server + Web Container (HTML 과 같은 정적인 페이지에서 처리할 수 없는 비즈니스 로직이나 DB 조회 같은 동적 컨텐츠 제공)
  - 정적 + 동적 데이터 처리
- **왜 Web Server, WAS 둘 다 두는가?**
  - 기능을 분리하여 서버 부하 방지
  - 물리적으로 분리하여 보안 강화.
    - 공격에 대해 Web Server 를 앞단에 두어 중요한 정보가 담긴 DB나 로직까지 전파되지 못하게 한다.
  - 여러 대의 WAS 연결 가능
    - Load balancing
    - 대용량 웹 어플리케이션의 경우 Web Server 과 WAS 를 분리하여 무중단 운영을 위한 장애 극복에 대응할 수 있다.
  - 다른 종류의 WAS 로 서비스 가능
    - 하나의 서버 (Python Application), 다른 서버 (Java Application)

### 4. Git에 대해 설명해 주세요.

- **여러 브랜치를 합쳐야 할 때, 어떤 방법을 사용할 수 있는지 "모두" 설명해 주세요.**
- **여러 브랜치를 합쳐야 할 때, 어떤 방법을 사용할 수 있는지 "모두" 설명해 주세요.**