# 클라우드 서비스 모델

![image-20200121131838235](/Users/hongbeen/Library/Application Support/typora-user-images/image-20200121131838235.png)

### On-premise (Traditional IT)

사용자가 직접 인프라,플랫폼,애플리케이션을 관리하는 모델.

규모있는 업체라면 직접 IDC를 구축하고, 일반적인 경우 IDC에 공간을 할당받아 물리서버를 설치하고 하드웨어,운영체제, 서버 애플리케이션을 모두 관리한다.

### laaS (Infrastructure as a Service)

> AWS EC2

하드웨어를 서비스로 제공하는 클라우드 모델.OS와 애플리케이션을 관리한다.

### PaaS (Platform as a Service)

> AWS Elastic Beanstalk

하드웨어에 더해 애플리케이션을 운영하기 위한 OS와 관련 기능들을 서비스로 제공한다.개발자는 애플리케이션과 서비스로 제공되는 기능을 연결하는 로직을 작성해야 한다.

### Saas (Software as a Service)

> Google Apps, Office365

애플리케이션 레벨까지 서비스로 제공된다.개발자보다는 실 사용자에게 바로 제공.



-----------------

대부분의 파일 시스템은 특정 사용자와 사용자그룹에 접근 권한을 할당하는 방식을 제공한다.이러한 시스템들은 사용자가 파일 시스템의 내용을 보거나 변경할 수 있는 기능을 제어한다.

| owner   | group    | everyone   |
| ------- | -------- | ---------- |
| rwx     | r-x      | r-x        |
| r: read | w: write | x: execute |

1. runserver실행을 위해 필요한 것 (Django실행)

- Python
- DJango

2. 외부에서 접근가능한지 확인

3.  screen으로 지속적으로 켜져있게 하기

- ssh 접속

  $ screen S 세션명 / 스크린실행 

  `$ screen -R 세션명 / 스크린나가기`

  `$ screen -list / 모든 screen목록을 보여줌`

4. 새 소스코드 배포

- screen으로 실행되고 있던 서버 종료
- 서버에 있는 소스폴더를 통째로 삭제 ( ssh -i ~/.ssh/wps12th.pem ubuntu@아이피주소 sudo rm -rf /home/ubuntu/projects/instagram )
- 로컬에 있는 소스폴더 올리기 /( scp -i ~/.ssh/wps12th.pem -r ~/projects/wps12th/instagram ubuntu@아이피주소:/home/ubuntu/projects/ )
- screen을 이용해서 서버 실행

