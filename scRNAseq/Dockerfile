# syntax=docker/dockerfile:1
FROM python:3.9.12-bullseye

WORKDIR /notebook

# install other dependencies
COPY requirements.txt requirements.txt
RUN pip3 install -r requirements.txt
RUN pip3 install torchmetrics==0.6.0
RUN pip3 install protobuf==1.30.1

# Setup jupyter server
EXPOSE 8888
ARG pwd=''
ENV password=$pwd
RUN echo Jupyter pwd: ${password}
CMD ["sh", "-c", "jupyter lab --port=8888 --no-browser --ip=0.0.0.0 --allow-root --NotebookApp.token=${password}"]