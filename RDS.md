EC2에서는 RDS를 두개 만드는게 아닌 하나의 RDS에서 관리할 수 있도록 데이터베이스를 생성해서 사용합니다.

데이터베이스를 생성하는 명령어는 

```
$ psql --host=데이터베이스의엔드포인트 --username=마스터사용자이름 --dbname=postgres

# 접속 후

$ CREATE DATABASE (db_name) OWNER=(owner_name)
TEMPLATE (template_name) LC_COLLATE 'C';

# 확인
$ \l
```

