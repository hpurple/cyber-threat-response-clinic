FROM ubuntu:18.04

MAINTAINER Moses Frost "moses@cisco.com"

RUN apt-get update -y && \
    apt-get install -y python-pip python-dev

# We copy just the requirements.txt first to leverage Docker cache
COPY ./heimdal/requirements.txt ./heimdal/requirements.txt

WORKDIR /heimdal

RUN pip install -r requirements.txt

COPY . /heimdal

ENTRYPOINT [ "python3" ]

CMD [ "app.py" ]