FROM pytorch/pytorch:2.5.1-cuda12.1-cudnn9-devel

RUN apt-get -y update && apt-get -y upgrade
RUN apt-get install git -y

RUN git config --global user.name "Your Name" \
    && git config --global user.email "youremail@example.com"
RUN git clone -b "branch Name" https://github.com/OptiQuantTeam/AI.git ./workspace
