### nginx에서 css파일 적용시키기

nginx와 gunicorn을 킨 후 `localhost:8001`로 접근하면 캐시가 남아있어서 css파일이 적용된걸 볼 수 있음

*shift + command + r 을 눌러보면 캐시가 삭제되어 css파일적용이 풀림*

instagram/app/config/settings.py에서

```
STATIC_ROOT = os.path.join(ROOT_DIR, '.static')
```

instagram/instagram.nginx에서

```
locations /static/ {
	alias				/srv/instagram/.static/;
}
```

-  `$ python docker-run-secrets.py`

하고 다시 `localhost:8001` 로 접근해보면 css파일이 적용된걸 볼 수 있다

