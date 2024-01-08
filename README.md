# awsStudy (2023.12.30 ~ )
aws 공부

## 목표 1 - ec2로 내 프로젝트 배포해보고 내 로컬 컴퓨터로 접속해보기
## 진행 순서
### 1. aws 회원가입 및 인스턴스 생성

<img src="/pictures/aws1.png">

### 2. 보안 설정과 키페어 생성

<img src="/pictures/aws2.png">

### 3. ssh(putty)로 접속 후 java와 db설치

<img src="/pictures/aws3.png">

Putty 로 호스트, port, data(id), 키페어 입력 후 접속
인스턴스 내 패키지 최신화
- sudo apt-get update
- sudo apt-get upgrade
Java 설치
- sudo apt-get install openjdk-11-jdk
DB 설치
- sudo apt-get install mysql-server
DB 접근권한 설정 및 계정 생성
- cd /etc/mysql/mysql.conf.d
- sudo nano mysqld.cnf     --> bind-address를 127.0.0.1 을 0.0.0.0
- mysql -u root -p
- create user '유저이름'@'%' identified by '비밀번호';
- grant all privileges on *.* to '유저이름'@'%' with grant option;

### 4. 로컬에서 인스턴스 DB에 연결

### 5. jar파일 생성 및 배포
<img src="/pictures/aws4.png">
sftp(filezila)연결 후 jar파일 배포

### 6. 인스턴스에서 배포된 서버에 로컬 컴퓨터로 접속
<img src="/pictures/aws5.png">



### 후기
- aws 관련 공부를 검색으로 독학하다보니 실행오류나 과정에서 막혔을때 방법찾는게 정말 어려웠다.
- **Linux 체제와 그 사용**에 대해 어느정도 이해를 하게 됐고, 
- 인스턴스에 연결된 상태에서의 **사용자, 권한** 에 대한 공부를 할 수 있었다.
- **ip와 포트, 프로토콜**등 계속 오류수정을 하며 찾다보니 **네트워크와 보안쪽 경험**을 해볼 수 있었다.+
