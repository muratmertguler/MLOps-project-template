FROM ubuntu:22.04

RUN apt-get update -y
RUN apt-get install sudo -y
RUN apt-get update && \
    apt-get install -y build-essential
RUN apt-get install python3-pip -y
RUN pip3 install --upgrade pip

COPY src/ /mlops_finance/src
COPY data/ /mlops_finance/data
COPY models/ /mlops_finance/models
COPY ./requirements.txt /mlops_finance
COPY ./ds_app.py /mlops_finance

WORKDIR /mlops_finance

RUN pip3 install -r requirements.txt
RUN poetry config virtualenvs.create false
#RUN poetry install --no-dev
