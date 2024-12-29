FROM python:3.11.10

RUN apt-get -y update && apt-get -y upgrade
RUN apt-get install git -y
# Set the default value for the 'app_name' argument
ARG app_name=CapstoneWeb
ENV APP_NAME $app_name  

# Set the PYTHONUNBUFFERED environment variable to ensure Python prints directly to terminal
ENV PYTHONUNBUFFERED 1

# Set the working directory inside the container to '/django'
WORKDIR /django

# Install Django using pip
RUN pip install Django

# RUN apt-get update && apt-get install -y mariadb-client

# Start a new Django project named as specified in the 'app_name' argument
#RUN django-admin startproject $app_name

RUN git config --global user.name "Your Name" \
    && git config --global user.email "youremail@example.com"

# github repository에 있는 파일 가져오기
RUN git clone -b "branch Name" https://github.com/OptiQuantTeam/WebServer.git ./${APP_NAME}


# Update the 'ALLOWED_HOSTS' setting in the Django project's settings.py file
RUN sed -i "s/ALLOWED_HOSTS = \[\]/ALLOWED_HOSTS = \['*'\]/g" ./${APP_NAME}/${APP_NAME}/settings.py

# Expose port 8000 to allow external access
EXPOSE 8000

# Specify the command to run the Django development server when the container starts
#CMD ["sh", "-c", "python ./${APP_NAME}/manage.py runserver 0.0.0.0:8000"]