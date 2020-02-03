1. EC2생성에서 인스턴스 생성
2. .pem파일 다운로드 받고
3. cd downloads
4. mv 000.pem ~/.ssh
5. cd ~/.ssh
6. chmod 400 000.pem
7. ssh -i ~/.ssh/000.pem ubuntu@15.164.103.235
8. scp -i ~/.ssh/000.pem -r instagram ubuntu@IPv4 퍼블릭 IP:/home/ubuntu/





Docker

1. docker build -t 생성될이미지이름 -f Dockerfile <파일위치> or .으로 해도 됨
2. docker image / 이미지들을 확인
3. docker push pack122/wps-instagram
4. docker pull  pack122/wps-instagram 
5. docker run --rm -it -p 8001:8000 instagram /bin/bash

