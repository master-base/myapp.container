FROM continuumio/miniconda3

WORKDIR /box
COPY . /box

RUN mkdir /box/workspace

RUN conda env create \
    --yes \
    --no-default-packages \
    --prefix /box/prefix \
    --file ./environment.yml

RUN conda run \
    --live-stream \
    --prefix /box/prefix \
    pip install \
    --requirement ./requirement.txt
