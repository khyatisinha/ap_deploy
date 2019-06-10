FROM ubuntu:16.04
FROM python:3.5-slim

RUN pip install numpy
RUN pip install keras
RUN pip install pillow
RUN pip install tensorflow

ARG username
ARG password

RUN apt-get update && apt-get upgrade -y && apt-get install -y git
WORKDIR /home/ec2-user
RUN git clone https://${username}:${password}@github.com/khyatisinha/ap_deploy.git
#RUN git clone https://github.com/khyatisinha/ap_deloy.git .
WORKDIR /home/ec2-user/ap_deploy
EXPOSE 80

CMD ["python", "./keras_resnet.py"]
