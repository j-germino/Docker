# syntax=docker/dockerfile:1

FROM python:3.9.12-bullseye

WORKDIR /notebook

RUN pip3 install jupyterlab

EXPOSE 8888
ARG pwd=''
ENV password=$pwd
RUN echo Jupyter pwd: ${password}
CMD ["sh", "-c", "jupyter lab --port=8888 --no-browser --ip=0.0.0.0 --allow-root --NotebookApp.token=${password}"]