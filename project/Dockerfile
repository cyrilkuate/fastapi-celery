# pull official base image
FROM python:3.11.2-slim-buster
RUN apt-get update && apt-get install -y util-linux  # Assurez-vous que setpriv est installé
RUN groupadd mygroup && useradd -m -g mygroup myuser
# set work directory
WORKDIR /usr/src/app

# set environment variables
ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1

# install dependencies
RUN pip install --upgrade pip
COPY ./requirements.txt .
RUN pip install -r requirements.txt

# copy project
COPY . .
USER myuser
