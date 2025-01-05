FROM pytorch/pytorch:2.5.1-cuda12.1-cudnn9-devel

RUN apt-get -y update && apt-get -y upgrade
RUN apt-get install git -y
RUN pip3 install --upgrade pip

RUN git config --global user.name "Your Name" \
&& git config --global user.email "youremail@example.com"
RUN git clone -b "branch Name" https://github.com/OptiQuantTeam/AI.git .
RUN git pull origin "branch Name"

COPY requirement.txt requirement.txt
RUN pip3 install --no-cache-dir -r requirement.txt