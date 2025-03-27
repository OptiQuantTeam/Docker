FROM python:3.11.10

# 시스템 패키지 업데이트 및 필요한 패키지 설치
RUN apt-get -y update && apt-get -y upgrade
RUN apt-get install git -y
RUN pip3 install --upgrade pip

WORKDIR /app
# Python 패키지 설치
RUN git config --global user.name "Your Name" \
&& git config --global user.email "youremail@example.com"
RUN git clone -b "branch Name" https://github.com/OptiQuantTeam/AI_Lambda.git .

RUN pip install -r requirement.txt
RUN pip install torch==2.5.1 torchvision==0.20.1 torchaudio==2.5.1 --index-url https://download.pytorch.org/whl/cpu
