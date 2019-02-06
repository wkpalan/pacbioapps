Bootstrap: docker
From: ubuntu:18.04

%labels
Maintainer Matthew Flister
Version v1.0

%help
This container runs includes several PacBio apps.

%environment
    SHELL=/bin/bash
    export PATH="/opt/miniconda3/bin:$PATH"

%post
    # default mount points
    mkdir -p /scratch/global /scratch/local /rcc/stor1/refdata /rcc/stor1/projects /rcc/stor1/depts

    # Install necessary packages
    apt-get update && apt-get install -y --no-install-recommends \
        build-essential \
        gcc-multilib \
        libboost-all-dev \
        libhdf5-serial-dev \
        zlib1g-dev \
        python3-pip \
        pkg-config \
        python3-dev \
        python3-setuptools \
        wget
    apt-get clean

    # install miniconda
    wget https://repo.continuum.io/miniconda/Miniconda3-latest-Linux-x86_64.sh -O miniconda3.sh
    bash miniconda3.sh -b -p /opt/miniconda3
    rm miniconda3.sh
    export PATH="/opt/miniconda3/bin:$PATH"

    # install pacbio apps
    conda install -c bioconda pbccs bax2bam lima bam2fastx pbmm2

    chmod a+rwx /opt/miniconda3/bin

