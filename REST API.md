## REST API (Representational State Transfer API)

### REST 구성

----

- 자원(RESOURCE) - URI
- 행위(Verb) - HTTP METHOD
- 표현(Representations)

### REST의 특징

----

1) Uniform(유니폼 인터페이스)

Uniform Interface는 URL로 지정한 리소스에 대한 조작을 통일되고 한정적인 인터페이스로 수행하는 아키텍처 스타일을 말합니다.

2) Stateless(무상태성)

REST는 무상태성 성격을 갖습니다.다시 말해 작업을 위한 상태정보를 따로 저장하고 관리하지 않습니다.세션 정보나 쿠키정보를 별도로 저장하고 관리하지 않기 때문에 API서버는 들어오는 요청만을 단순히 처리하면 됩니다.때문에 서비스의 자유도가 높아지고 서버에서 불필요한 정보를 관리하지 않음으로써 구현이 단순해집니다.

3) Cacheable(캐시 가능)

REST의 가능 큰 특징 중 하나는 HTTP라는 기존 웹표준을 그대로 사용하기 때문에, 웹에서 사용하는 기존 인프라를 그대로 활용이 가능합니다.따라서 HTTP가 가진 캐싱 기능이 적용가능합니다.HTTp프로토콜 표준에서 사용하는 Last-Modified태그나 E-Tag를 이용하면 캐싱 구현이 가능합니다.

4) Self-descriptveness(자체 표현 구조)

REST의 또 다른 큰 특징 중 하나는 REST API메시지만 보고도 이를 쉽게 이해 할 수 있는 자체 표현 구조로 되어있다는 것입니다.

5) Client - Server구조

REST서버는 API제공, 클라이언트는 사용자 인증이나 컨텍스트등을 직접 관리하는 구조로 각각의 역할이 확실히 구분되기 때문에 클라이언트와 서버에서 개발해야 할 내용이 명확해지고 서로간 의존성이 줄어들게 됩니다.

6) 계층형 구조

REST서버는 다중 계층으로 구성될 수 있으며 보안,로드 밸런싱,암호화 계층을 추가해 구조상의 유연성을 둘 수 있고 PROXY,게이트웨이 같은 네트워크 기반의 중간매체를 사용할 수 있게 합니다.

### REST API 디자인 가이드

----

REST ATI 설계 시 가장 중요한 항목은 다음의 2가지로 요약할 수 있습니다.

1. URI는 정보의 자원을 표현해야 한다.
2. 자원에 대한 행위는 HTTP Method(GET,POST,PUT,DELETE)로 표현한다.

### REST API 중심 규칙

---

1) URI는 정보의 자원을 표현해야 한다.(리소스명은 동사보다는 명사를 사용)

```
GET/members/delete/1
```

위와 같은 방식은 REST를 제대로 적용하지 않은 URI입니다.URI는 자원을 표현하는데 중점을 두어야 합니다.delete와 같은 해우이에 대한 표현이 들어가서는 안됩니다.

2) 자원에 대한 행위는 HTTP Method(GET, POST, PUT, DELETE 등)로 표현

위의 잘못 된 URI를 HTTP Method를 통해 수정해보면

```
DELETE/members/1
```

으로 수정할 수 있겠습니다.

회원정보를 가져올 때는 GET, 회원 추가 시의 행위를 표현하고자 할 때는 POST METHOD를 사용하여 표현합니다.

*회원정보를 가져오는 URI*

```
GET/members/show/1 (x)
GET/members/1			 (o)
```

*회월을 추가할 때*

```
GET/members/insert/2	(x) - GET메서드는 리소스 생성에 맞지 않습니다.
POST/members/2
```

[참고]HTTP METHOD의 알맞은 역할

| METHOD |                             역할                             |
| :----: | :----------------------------------------------------------: |
|  POST  |     POST를 통해 해당 URI를 요청하면 리소스를 생성합니다.     |
|  GET   | GET을 통해 해당 리소스를 조회합니다.리소스를 조회하고 해당 도큐먼트에 대한 자세한 정보를 가져옵니다. |
|  PUT   |             PUT을 통해 해당 리소스를 수정합니다.             |
| DELETE |              DELETE를 통해 리소스를 삭제합니다.              |

다음과 같은 식으로 URI는 자원을 표현하는데에 집중하고 행위에 대한 정의는 HTTP METHOD를 통해 하는 것이 REST한 API를 설계하는 중심 규칙입니다.

URI 설계 시 주의할 점

정리 내용 출처: https://meetup.toast.com/posts/92