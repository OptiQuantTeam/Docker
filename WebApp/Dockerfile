FROM node:20.18

RUN apt-get -y update && apt-get -y upgrade
RUN apt-get install git -y

WORKDIR /app

RUN git config --global user.name lucas \
    && git config --global user.email wymam1@gmail.com

# github repository에 있는 파일 가져오기
RUN git clone -b develop https://github.com/OptiQuantTeam/WebApp.git /app


WORKDIR /app/backend
RUN npm install

# package.json 워킹 디렉토리에 복사 (.은 설정한 워킹 디렉토리를 뜻함)
#COPY package.json .
# 명령어 실행 (의존성 설치)
WORKDIR /app/frontend
RUN npm install
# 현재 디렉토리의 모든 파일을 도커 컨테이너의 워킹 디렉토리에 복사한다.

# 각각의 명령어들은 한줄 한줄씩 캐싱되어 실행된다.
# package.json의 내용은 자주 바뀌진 않을 거지만
# 소스 코드는 자주 바뀌는데
# npm install과 COPY . . 를 동시에 수행하면
# 소스 코드가 조금 달라질때도 항상 npm install을 수행해서 리소스가 낭비된다.



# 3000번 포트 노출
EXPOSE 3050

# npm start 스크립트 실행
#CMD ["npm", "start"]