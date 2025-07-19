# 🌐 HTTP & HTTPS 정리

## 🔸 Hypertext Transfer Protocol (HTTP)

- **Port:** 80  **Transport Layer Protocol:** TCP
- **설명:**  
  - 하이퍼텍스트(Hypertext)를 전달하는 웹 통신 프로토콜  
  - 웹사이트 브라우징 시 사용됨  
  - **클라이언트**(Client): 웹 서버(Web Server)에 웹 페이지 정보를 요청 (request)  
  - **웹 서버**(Web Server): 요청에 응답(reply)하여 하이퍼텍스트 전달  
  - HTML(Hypertext Markup Language)을 사용하여 정보를 전달  
  - **데이터가 텍스트로 전달되므로 보안이 취약함**

---

## 🔸 Hypertext Transfer Protocol Secure (HTTPS)

- **Port:** 443  **Transport Layer Protocol:** TCP
- **설명:**  
  - **HTTP + 암호화**를 사용한 보안 강화된 프로토콜  
  - 웹 서버에서 정보를 **요청하고 응답받는 과정은 동일**  
  - HTML 사용  
  - **데이터가 암호화되어 전송되므로 보안성이 높음**

---

## 📝 용어 정리

| 용어 | 설명 |
|------|------|
| **하이퍼링크 (Hyperlink)** | 특정 주소로 이동시키는 기능 (예: 링크 클릭) |
| **하이퍼텍스트 (Hypertext)** | 하이퍼링크를 포함하고 있는 텍스트 |
| **프로토콜 (Protocol))** | 기계(컴퓨터)들끼리 서로 통신할 때 지켜야 할 약속이나 규칙 |