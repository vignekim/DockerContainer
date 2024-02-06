# 5. Docker File 빌드하기

### 사용한 Dockerfile 내용

```
FROM centos:7
```

---

### Dockerfile build 기본 명령어

```
docker build [OPTIONS] PATH | URL | -
```

### 사용되는 Option 종류

```-t, --tag``` > 태그를 지정 하기

```
docker build -t [이미지명:태그명] .
```

```-f``` > Docker File 경로 지정 하기

```
docker build -f [디렉토리경로/파일명] .
```

```--pull=true``` > FROM에서 사용한 이미지 최신으로 다시 받기

```
docker build --pull=true . .
```

---

### Docker 컨테이너 이미지로 만들기 (Commit)

```
docker commit [OPTIONS] CONTAINER [REPO/IMG:TAG]
```

### Commit Options

```-a``` > 작성자 설정

```-m``` > 설명(Message) 설정

### 실행 중인 컨테이너 ```test-container```를 test/centos:1.0 만들기

```
docker commit -a "사용자명" -m "설명문" test-container test/centos:1.0
```

---

### Table of Contents

###### [0. Docker 알아보기](../../../../)

###### [1. Docker 설치](../1.docker/)

###### [2. Docker 기본 명령어](../2.docker/)

###### [3. Docker 실행(Run)](../3.docker/)

###### [4. Docker File 만들기](../4.docker/)

#### 5. Docker File 빌드하기

###### [6. Docker Compose 기본 명령어](../6.docker/)

###### [7. Docker Compose 만들기](../7.docker/)

###### [8. Docker Compose 실행(Run)](../8.docker/)

###### [9. DevContainer 알아보기](../9.docker/)

###### [10. DevContainer를 이용한 HTTP Web Server 환경 만들기](../10.docker/)

###### [11. DevContainer를 이용한 Database 환경 만들기](../11.docker/)

###### [12. DevContainer를 이용한 Web Application Server 환경 만들기](../12.docker/)

###### [13. DevContainer를 이용한 Developer Server 환경 만들기](../13.docker/)

