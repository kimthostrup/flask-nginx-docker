FROM ubuntu:18.04

RUN apt-get update -y && \
    apt-get upgrade -y && \
    apt-get install python3 python3-pip -y

# We copy just the requirements.txt first to leverage Docker cache
COPY ./requirements.txt /app/requirements.txt

WORKDIR /app

RUN pip3 install -r requirements.txt

COPY . /app


EXPOSE 5000

CMD [ "uwsgi", "--ini", "app.ini" ]