FROM node:20.18

RUN apt-get -y update && apt-get -y upgrade
RUN apt-get install git -y

WORKDIR /app

RUN git config --global user.name "Your Name" \
    && git config --global user.email "youremail@example.com"

# github repository에 있는 파일 가져오기
RUN git clone -b "branch Name" https://github.com/OptiQuantTeam/WebApp.git /app


WORKDIR /app/backend
RUN npm install


