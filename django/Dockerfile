FROM python:3
ENV PYTHONDONTWRITEBYTECODE=1
ENV PYTHONUNBUFFERED 1

RUN mkdir /code

WORKDIR /code

ADD requirements.txt /code/

RUN pip install --upgrade pip && \
    pip install -r requirements.txt && \
    apt-get update && \
    apt-get install -y vim && \
    useradd -ms /bin/bash local

ADD . /code/