SecurityGroep의 Inbound

Client(IP)

 -> SecurityGroup (Clientd의 IP가 Inbound의 허용범위내에 없으면 거부)

```python
# app/config
ALLOWED_HOSTS[
'phb.kr',
]
# 보낸 사람이 '어디에' 보냈느냐를 기준으로 필터(보낸 사람의 IP는 신경쓰지 않음)
```

Client -> (Request) -> EC2(IP:142.1.1.1, Domain: phb.kr, hhm.kr)

-> EC2에 도달하는 Request를 만들기 위해서는,

142.1.1.1로 요청

phb.kr <-이것만 허용

Django가 거부하므로, SecurityGrop의 Inbound는 이미 통과한 상태

`$ pqsl --host=엔드포인트 --username=phb --dbname=postgres`

Django ORM -> SQL -> Python -> psycopg2 -> PostgreSQL

`$ pip install psycopg2-binary`

그냥 베포하면 이미지가 깨짐(디비는 공유)



### Django기본 (FileSystem)

- `f = FileSystemStorage.open('경로')`

- `f .read()`

- `f.close()`

f-> File객체(FileSystemStorage가 제공하는 Python의 File사용법과 매우 유사한 객체)

----

### Cloud서비스

f = open('경로') <- 파일시스템의 경로가 아닌, 클라우드 드라이브의 경로

S3사용하려면 install해야함

```
$ pip install django-storages
$ pip install boto3
```