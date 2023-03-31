FROM debian:bullseye-slim

WORKDIR /home/kbrzezinska/ilv_automatisierung_abschlussprojekt_kb

LABEL author = "Klaudia"
LABEL description = "this is my first container"
ENV LANG C.UTF-8

RUN apt-get update && \ 
    apt-get install -y \ 
    bzip2 \
    build-essential \
    libncurses-dev \
    zlib1g-dev \
    libbz2-dev \
    liblzma-dev 

ADD https://github.com/samtools/samtools/releases/download/1.14/samtools-1.14.tar.bz2 /home/kbrzezinska/ilv_automatisierung_abschlussprojekt_kb/Download/
WORKDIR /home/kbrzezinska/ilv_automatisierung_abschlussprojekt_kb/Download

RUN tar -x -f samtools-1.14.tar.bz2

WORKDIR  /home/kbrzezinska/ilv_automatisierung_abschlussprojekt_kb/Download/samtools-1.14
RUN  ./configure && \ 
     make && \
     make install 

ENTRYPOINT ["samtools"]
