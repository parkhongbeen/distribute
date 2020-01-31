### poetry란?

파이썬 패키지 관리자 

```
poetry init
```

```
$ poetry add 'django<3' boto3 django-extensions django-secrets-manager django-storages Pillow psycopg2-binary requests notebook

#장고3이하버전기준으로 다른 패키지들을 설치함
```



EC2 - Container(80:8000) - (screen)runserver:8000 - Django



EC2 - Container(80:8000) - gunicorn:8000 - Django

EC2 - Container(80:8000) - Nginx:80 - gunicorn:UnixSocket - Django

#한번에 하려고 하면 오류나는 경우가 많기때문에  하나씩 해보는걸 추천함



Nginx(WebServer)

​		외부에서 오는 요청을 어딘가로 전달

​		정적 콘텐츠 서빙

Gunicorn(WSGI)

​		웹 서버로 전달된 요청을 파이썬 애플리케이션에게 적절히 번역

​		-> 반대로, 파이썬 애플리케이션의 응답을 적절히 웹 서버에게 번역해서 전달

Django(Web application)

​		외부에서 오는 요청에 대한 동적 응답을 생성





