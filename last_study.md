Com1 - HTTP:80 = Com2

암호화

````
-대칭키 암호화
원문 -> 키 -> 암호문
암호문 -> 키 -> 원문
-공개키/개인키 암호화
원문 ->공개키(암호화) -> 개인키(복호화) -> 원문
원문 -> 개인키(암호화) -> 공개키(복호화) -> 원문 <- 개인 서명
개인키(private key) <- 절대 노출되면 안됨
공개키(public key) <-외부에 노출되어도 상관 없음
````

```
A가 B와 통신하고 싶다.

1. A가 자신의 공개키를 HTTP를 사용해서 B에게 보냄
2. B는 A에게 HTTP를 사용해서 자신의 공개키를 보냄
3. A는 B에게 보낼 메세지를 B의 공개키를 사용해서 암호화하여 보냄
4. B는 받은 메세지를 자신의 "개인키"로 복화해서 읽음

```

```
A랑 B가 통신 ( 중간에 X가 끼어듬)
A - X - B / 중간자 공격
```



```
HTTP에 공개키/개인키 -> HTTPS
A -> 브라우저 -> naver.com 인지
A -> 브라우저 -> X -> naver.com 인지 알 수 없음
naver.com
-인증서 + 공개키

인증기관
		-naver.com에게 공개키, 개인키를 발급
```

```
Let's Encrypt
-인증서 발급
-인증서와 공개키, 개인키를 Nginx가 사용하도록 설정
-인증서 자동 갱신
```



certbot프로그램을 이요해서 Let's Encrypt기관의 인증서를 받는다.

-직접 설치

-docker를 사용해서 실행

​	-> 인증서, 개인키, 공개키가 저장될 영역을 --volume옵션에 추가



-docker run --volume

Host의 특정 영역 - Container의 특정 영역과 공유

```
-해싱
raw_password(암호화되지 않은 텍스트로 입력받은 password값) -> 서버로직 -> hash value(DB)
```