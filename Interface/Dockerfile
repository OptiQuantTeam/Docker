FROM python:3.11.10


RUN apt-get -y update && apt-get -y upgrade
RUN apt-get install git -y
RUN pip3 install --upgrade pip

WORKDIR /usr/src/app
RUN mkdir tmp && mkdir Capstone
COPY requirement.txt tmp/requirement.txt
RUN pip3 install --no-cache-dir -r tmp/requirement.txt

RUN git config --global user.name "Your Name" \
    && git config --global user.email "youremail@example.com"

WORKDIR /usr/src/app/Capstone

RUN git clone -b "branch Name" https://github.com/OptiQuantTeam/Interface.git .