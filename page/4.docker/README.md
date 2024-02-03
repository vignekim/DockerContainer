# 4. Docker File 만들기

생성한 이미지를 도커 허브(docker hub)나 배포 시 이미지 자체를 배포하는 대신 이미지 생성하는 방법을 기록해 놓은 DockerFile로 관리 할 수 있습니다.

> [DockerFile Reference](https://docs.docker.com/engine/reference/builder/)

## 기본 지시어

```FROM``` > 생성할 이미지의 베이스가 될 이미지를 결정하는 명령어 입니다.
#### 모든 DockerFile은 반드시 FROM 지시어를 한번 이상 입력해야 하며 ```FROM``` 지시어를 시작으로 DockerFile를 작성합니다.

---
```LABEL``` > 이미지의 메타데이터를 설정하는 명령어 입니다.
#### 메타데이터는 ```키=값```의 형태로 저장되며, 여러개의 메터데이터가 저장될 수 있습니다.

---
```WORKDIR``` > 명령어를 실행할 디렉토리를 지정하는 명령어 입니다.
#### 리눅스 명령으로는 ```cd```와 동일한 역활를 합니다.

---
```EXPOSE``` > DockerFile의 빌드로 생성된 이미지에서 노출할 포트를 지정하는 명령어 입니다.
#### EXPOSE로 설정한 이미지를 기반으로 컨테이너를 생성한다고 해서 이 포트가 호스트의 포트와 바인딩하는 것은 아니며, 단지 해당 이미지를 사용자에게 해당 포트를 사용한다고 문서화하는 목적을 가지는 것 뿐 입니다.
#### Publish 하고 싶다면 docker run 명령어에 ```-p``` 옵션으로 포트를 지정해 주어야 호스트의 해당 포트를 바인딩 됩니다.

---
```COPY``` > 현재 디렉토리 경로의 모든 파일과 디렉토리를 지정한 디렉토리에 모두 복사하는 명령어 입니다.
#### COPY 지시어는 ```COPY <호스트경로> <컨테이너경로>``` 형식으로 정의 할 수 있습니다.

---
```RUN``` > 이미지를 만들기 위해 컨테이너 내부에서 명령어를 실행합니다.
#### DockerFile을 이미지로 빌드하는 과정에서는 별도의 입력이 불가능하기 때문에 package 설치와 같은 명령어 실행 시 유저에게 설치 질의에 대한 [Y/N] 부분은 빌드 시 오류로 간주 하기 때문에 주의해야 합니다.

---
```ADD``` > 파일를 이미지에 추가 합니다.
#### DockerFile이 위치한 디렉토리인 Context에서 가져 옵니다.
#### ADD 명령어는 JSON 배열의 형태로 ```["추가 파일","컨테이너의 추가될 위치"]``` 작성 할수 있으며 여려개 파일를 지정 할 경우에는 마지막 원소가 컨테이너의 추가될 위치를 넣어 주면 됩니다.

---
```ENV``` > 컨테이너에 환경 변수를 추가 합니다.
#### ENV 지시어는 ```ENV <변수명> <변수값>``` 형식으로 정의 할 수 있습니다.

---
```CMD``` > 해당 이미지로 컨테이너를 실행할 때 필요한 명령어를 수행 하도록 지정하는 명령어 입니다.
#### DockerFile에서 한번만 사용할 수 있으며, 컨테이너 내 특정 실행 명령어가 필요 시 사용 됩니다.

---
```ENTRYPOINT``` > 컨테이너가 실행할때 고정적으로 실행되는 스크립트 또는 명령어 입니다.
#### ENTRYPOINT와 CMD의 차이점으로 ENTRYPOINT는 CMD를 인자로 받아서 스크립트 역할를 할 수 있습니다.

```
FROM ubuntu:latest
ENTRYPOINT ["top", "-b"]
CMD ["-c"]
```
#### 위의 내용으로 사용한다면 top -b -c 순서로 실행이 됩니다.

---

### Table of Contents

###### [0. Docker 알아보기](../../../../)

###### [1. Docker 설치](../1.docker/)

###### [2. Docker 기본 명령어](../2.docker/)

###### [3. Docker 실행(Run)](../3.docker/)

#### 4. Docker File 만들기

###### [5. Docker File 빌드하기](../5.docker/)

###### [6. Docker Compose 기본 명령어](../6.docker/)

###### [7. Docker Compose 만들기](../7.docker/)

###### [8. Docker Compose 실행(Run)](../8.docker/)

###### [9. DevContainer 알아보기](../9.docker/)

###### [10. DevContainer를 이용한 HTTP Web Server 환경 만들기](../10.docker/)

###### [11. DevContainer를 이용한 Database 환경 만들기](../11.docker/)

###### [12. DevContainer를 이용한 Web Application Server 환경 만들기](../12.docker/)

###### [13. DevContainer를 이용한 Developer Server 환경 만들기](../13.docker/)

