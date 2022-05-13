# syntax=docker/dockerfile:1

FROM pytorch/pytorch:1.11.0-cuda11.3-cudnn8-devel

WORKDIR /notebook

# install other dependencies
COPY requirements.txt requirements.txt
RUN pip3 install -r requirements.txt

# Setup jupyter server
EXPOSE 8888
ARG pwd=''
ENV password=$pwd
RUN echo Jupyter pwd: ${password}
CMD ["sh", "-c", "jupyter lab --port=8888 --no-browser --ip=0.0.0.0 --allow-root --NotebookApp.token=${password}"]