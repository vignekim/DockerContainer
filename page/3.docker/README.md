# 3. Docker 실행(Run)

docker run은 ```docker image```를 이용하여 만든 컨테이너에게 명령어를 실행 시키기 위한 명령어 입니다.

### docker run options

* Default Format
```
docker run [options] IMAGE[:TAG|@DIGEST] [COMMAND] [ARG...]
```

* -i / -t / -it
```
docker run -it ubuntu:latest
```
#### 두 옵셥은 컨테이너에 터미널의 입력을 계속해서 전달하기 위해 자주 같이 사용됩니다.
#### ```-i```는 컨테이너에 attach(접속)하지 않은 상태여도 표준 입력(stdin)을 활성화하고 유지합니다.
#### ```-t```는 TTY 모드(pseudo-TTY)를 사용하는 것으로, 쉘에 명령어를 작성할 수 있습니다.
#### ```-it```를 사용하게 되면 두 옵션을 모두 적용하여 docker는 pseudo-TTY를 할당하고, container의 stdin에 연결합니다.

* -d
```
docker run -d ubuntu:latest
```
#### 컨테이너를 백그라운드에서 실행하도록 하는 옵션입니다.
#### 명령어를 실행한 container id를 출력합니다.

* -e
```
docker run -e NEW_KEY=SHELL ubuntu:latest
```
#### 컨테이너에 환경 변수를 추가하는 옵션이다.
#### 환경 변수 여러개를 추가하고 싶다면 ```-e```를 여러번 사용해야 합니다.

* -p
```
docker run -p 80:8080 ubuntu:latest
```
#### 호스트에 연결된 컨테이너의 특정 포트를 외부에 노출하기 위해 사용합니다.
#### 포트는 ```호스트:컨테이너```로 정의 할 수 있습니다.

* -w
```
docker run -w /workspace ubuntu:latest
```
#### 컨테이너의 working directory를 변경하는 옵션입니다.

* -v
```
docker run -v ~/workspace:/workspace ubuntu:latest
```
#### 현재 working directory를 컨테이너에 마운트 하는 옵션입니다.

* --name
```
docker run --name ubuntu_os ubuntu:latest
```
#### 컨테이너의 이름을 설정할 때 사용하는 옵션입니다.

* --rm
```
docker run --rm ubuntu:latest
```
#### 명령어 수행 후 container가 삭제 되도록 하는 옵션입니다.
#### 컨테이너를 일회성으로 사용할 때 주로 사용됩니다.

---

### Table of Contents

###### [0. Docker 알아보기](../../../../)

###### [1. Docker 설치](../1.docker/)

###### [2. Docker 기본 명령어](../2.docker/)

#### 3. Docker 실행(Run)

###### [4. Docker File 만들기](../4.docker/)

###### [5. Docker File 빌드하기](../5.docker/)

###### [6. Docker Compose 기본 명령어](../6.docker/)

###### [7. Docker Compose 만들기](../7.docker/)

###### [8. Docker Compose 실행(Run)](../8.docker/)

###### [9. DevContainer 알아보기](../9.docker/)

###### [10. DevContainer를 이용한 HTTP Web Server 환경 만들기](../10.docker/)

###### [11. DevContainer를 이용한 Database 환경 만들기](../11.docker/)

###### [12. DevContainer를 이용한 Web Application Server 환경 만들기](../12.docker/)

###### [13. DevContainer를 이용한 Developer Server 환경 만들기](../13.docker/)

