# Dockerfile latest Version  
**최신 버전을 꼭 확인할 것!!**  
**이미지 생성시 {imageName}:{version}을 주의하여 적을 것!!**
```
AI         : v1.2   
Interface  : v1.1  
Web Server : v1.1
```   
  



## AI
>version : v1.2  
>Update :  
>- Date : 2025.01.05
>- Deatails : jupyter, pandas, matplotlib 라이브러리를 포함하는 requirement.txt 추가  

>version : v1.1  
>Update :  
>- Date : 2024.12.29
>- Deatails : git clone 명령어로 repository의 파일을 다운 받을 수 있게 변경  

>version : v1.0  
>Update :  
>- Date : 2024.12.29
>- Deatails : AI 개발 환경 구축  

<br/><br/>

---
## Interface
>version : v1.1  
>Update :  
>- Date : 2024.12.29
>- Deatails : git clone 명령어로 repository의 파일을 다운 받을 수 있게 변경

>version : v1.0  
>Update :  
>- Date : 2024.12.29
>- Deatails : Interface 개발 환경 구축


<br/><br/>

---
## Web Server
>version : v1.1  
>Update :  
>- Date : 2024.12.29
>- Deatails : git clone 명령어로 repository의 파일을 다운 받을 수 있게 변경

>version : v1.0  
>Update :  
>- Date : 2024.12.29
>- Deatails : Web Server 개발 환경 구축  


<br/><br/>
<br/><br/>

# **Docker 명령어 정리**

## **1. Docker 설치 및 버전 확인**
- **Docker 설치 확인**
  ```bash
  docker --version
  ```
- **Docker Compose 설치 확인**
  ```bash
  docker-compose --version
  ```

---

## **2. Docker 이미지 관련 명령어**
- **이미지 목록 보기**
  ```bash
  docker images
  ```
- **이미지 다운로드 (pull)**
  ```bash
  docker pull [이미지 이름]:[태그]
  ```
  *예시:* `docker pull nginx:latest`

- **이미지 빌드 (build)**
  ```bash
  docker build [옵션] -t [이미지 이름]:[태그] [Dockerfile 경로]
  ```
  - 주요 옵션:
    - `-t`: 이미지에 태그를 지정
    - `.`: 현재 디렉토리를 빌드 컨텍스트로 사용

  *예시:* 
  ```bash
  docker build -t my-app:latest .
  ```

- **이미지 삭제**
  ```bash
  docker rmi [이미지 ID 또는 이름]
  ```
- **이미지 상세 정보 확인**
  ```bash
  docker inspect [이미지 이름 또는 ID]
  ```
- **사용하지 않는 이미지 삭제**
  ```bash
  docker image prune
  ```

---

## **3. Docker 컨테이너 관련 명령어**
- **컨테이너 실행**
  ```bash
  docker run [옵션] [이미지 이름]
  ```
  - 주요 옵션:
    - `-it`: 상호작용 모드(터미널 접속 가능)
    - `-d`: 백그라운드 실행
    - `--name`: 컨테이너 이름 설정
    - `-p`: 포트 매핑
    - `-v`: 볼륨 마운트

  *예시:*
  ```bash
  docker run -d -p 8080:80 --name my-nginx nginx:latest
  ```

- **실행 중인 컨테이너 목록 보기**
  ```bash
  docker ps
  ```
- **모든 컨테이너 목록 보기 (중지된 컨테이너 포함)**
  ```bash
  docker ps -a
  ```
- **컨테이너 중지**
  ```bash
  docker stop [컨테이너 ID 또는 이름]
  ```
- **컨테이너 시작**
  ```bash
  docker start [컨테이너 ID 또는 이름]
  ```
- **컨테이너 재시작**
  ```bash
  docker restart [컨테이너 ID 또는 이름]
  ```
- **컨테이너 삭제**
  ```bash
  docker rm [컨테이너 ID 또는 이름]
  ```
- **컨테이너 로그 확인**
  ```bash
  docker logs [컨테이너 ID 또는 이름]
  ```
  - 실시간 로그 보기: `docker logs -f [컨테이너 이름]`

- **컨테이너 내부 접속**
  ```bash
  docker exec -it [컨테이너 ID 또는 이름] bash
  ```

---

## **4. Docker 네트워크 관련 명령어**
- **네트워크 목록 보기**
  ```bash
  docker network ls
  ```
- **네트워크 생성**
  ```bash
  docker network create [네트워크 이름]
  ```
- **컨테이너를 네트워크에 연결**
  ```bash
  docker network connect [네트워크 이름] [컨테이너 이름]
  ```
- **컨테이너를 네트워크에서 분리**
  ```bash
  docker network disconnect [네트워크 이름] [컨테이너 이름]
  ```

---

## **5. Docker 볼륨 관련 명령어**
- **볼륨 목록 보기**
  ```bash
  docker volume ls
  ```
- **볼륨 생성**
  ```bash
  docker volume create [볼륨 이름]
  ```
- **볼륨 삭제**
  ```bash
  docker volume rm [볼륨 이름]
  ```
- **볼륨 정보 확인**
  ```bash
  docker volume inspect [볼륨 이름]
  ```

---

## **6. 시스템 정리 및 관리 명령어**
- **중지된 컨테이너, 사용하지 않는 네트워크, 이미지, 볼륨 삭제**
  ```bash
  docker system prune
  ```
  - 추가 옵션: `-a`는 사용하지 않는 모든 이미지까지 삭제.
- **디스크 사용량 확인**
  ```bash
  docker system df
  ```

---

## **7. Docker Compose 관련 명령어**
- **Compose 프로젝트 실행**
  ```bash
  docker-compose up
  ```
  - 백그라운드 실행: `docker-compose up -d`

- **Compose 프로젝트 중지**
  ```bash
  docker-compose down
  ```
- **특정 서비스 재시작**
  ```bash
  docker-compose restart [서비스 이름]
  ```
- **Compose 로그 확인**
  ```bash
  docker-compose logs
  ```
  - 특정 서비스 로그: `docker-compose logs [서비스 이름]`
  - 실시간 로그: `docker-compose logs -f`

