FROM node:20.18

RUN apt-get -y update && apt-get -y upgrade
RUN apt-get install git -y

WORKDIR /app

RUN git config --global user.name "Your Name" \
    && git config --global user.email "youremail@example.com"

# github repository에 있는 파일 가져오기
RUN git clone -b "branch Name" https://github.com/OptiQuantTeam/FrontEnd.git /app

# 명령어 실행 (의존성 설치)
WORKDIR /app
RUN npm install



# 3000번 포트 노출
EXPOSE 3050

# npm start 스크립트 실행
#CMD ["npm", "start"]