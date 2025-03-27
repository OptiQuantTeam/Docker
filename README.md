# Dockerfile latest Version  
**최신 버전을 꼭 확인할 것!!**  
**이미지 생성시 {imageName}:{version}을 주의하여 적을 것!!**
  
| Repositoty | Version |
|:--:|:--:|
|AI|v1.2.1|
|AI_Lambda|v1.0|
|Trader|v1.1.1|
|FrontEnd|v2.1|
|BackEnd|v2.1|
|~~Web App~~|~~v2.1~~|

## AI
>version : v1.2.1  
>Update :  
>- Date : 2025.03.02
>- Deatails : nvidia GPU용 Docker 이미지 빌드 및 컨테이너 생성 추가    

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
## AI_Lambda
>version : v1.0  
>Update :  
>- Date : 2025.03.27
>- Deatails : AWS Lambda에 올라갈 AI 개발 환경 구축  

<br/><br/>


---
## Trader
>version : v1.1.1  
>Update :  
>- Date : 2025.03.02
>- Deatails : Interface에서 Trader로 이름 변경  

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
## FrontEnd
>version : v2.1     
>Update :  
>- Date : 2025.03.27
>- Deatails : 하나로 통합되어 있던 Web App을 FrontEnd와 BackEnd로 분리


<br/><br/>

---
## BackEnd
>version : v2.1   
>Update :  
>- Date : 2025.03.27
>- Deatails : 하나로 통합되어 있던 Web App을 FrontEnd와 BackEnd로 분리


<br/><br/>


---
## Web App  <span style="color:red"> --> FrontEnd와 BackEnd로 분리</span>
>version : v2.1  
>Update :  
>- Date : 2025.03.02
>- Deatails : Django에서 React로 프레임워크 변경 및 WebApp으로 이름 변경  

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
