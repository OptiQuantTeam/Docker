FROM python:3.11.10


RUN apt-get -y update && apt-get -y upgrade
RUN apt-get install git -y
RUN pip3 install --upgrade pip

WORKDIR /app

RUN git config --global user.name "Your Name" \
    && git config --global user.email "youremail@example.com"

RUN git clone -b "branch Name" https://github.com/OptiQuantTeam/Trader.git .

COPY requirement.txt /app
RUN pip3 install --no-cache-dir -r app/requirement.txt