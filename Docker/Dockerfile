# We use the official Debian image with the "bullseye-slim" tag as the base image
FROM debian:bullseye-slim

# Set the working directory to /home/kbrzezinska/ilv_automatisierung_abschlussprojekt_kb
WORKDIR /home/kbrzezinska/ilv_automatisierung_abschlussprojekt_kb

# Labels with metadata for the image
LABEL author="Klaudia"
LABEL description="This is my first container"

# Set the LANG environment variable to C.UTF-8
ENV LANG C.UTF-8

# Update the package repository and install necessary tools
RUN apt-get update && \
    apt-get install -y \
    bzip2 \
    build-essential \
    libncurses-dev \
    zlib1g-dev \
    libbz2-dev \
    liblzma-dev 

# Download and unpack the source code of samtools
ADD https://github.com/samtools/samtools/releases/download/1.14/samtools-1.14.tar.bz2 /home/kbrzezinska/ilv_automatisierung_abschlussprojekt_kb/Download/
WORKDIR /home/kbrzezinska/ilv_automatisierung_abschlussprojekt_kb/Download

RUN tar -x -f samtools-1.14.tar.bz2

# Change to the directory with unpacked samtools source code
WORKDIR **YOUR PATH**/ilv_automatisierung_abschlussprojekt_kb/Download/samtools-1.14

# Configure, compile, and install samtools
RUN ./configure && \
    make && \
    make install

# Set the entry point for the container to be able to run samtools as a command
ENTRYPOINT ["samtools"]
