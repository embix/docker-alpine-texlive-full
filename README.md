# embix/docker-alpine-texlive-full

this is a work in progress with the final goal to have an image to be used as tex build-env

## Usage

it's currently pretty much useless, but if you like you can run it in interactive mode `docker run --rm -it embix/texlive-full:v1 bash`:

    PS C:\Users\you> docker run --rm -it embix/texlive-full:v1 bash
    bash-4.4# pdflatex --version
    pdfTeX 3.14159265-2.6-1.40.18 (TeX Live 2017/Alpine Linux)
    kpathsea version 6.2.3
    Copyright 2017 Han The Thanh (pdfTeX) et al.
    There is NO warranty.  Redistribution of this software is
    covered by the terms of both the pdfTeX copyright and
    the Lesser GNU General Public License.
    For more information about these matters, see the file
    named COPYING and the pdfTeX source.
    Primary author of pdfTeX: Han The Thanh (pdfTeX) et al.
    Compiled with libpng 1.6.34; using libpng 1.6.34
    Compiled with zlib 1.2.11; using zlib 1.2.11
    Compiled with poppler version 0.56.0
    bash-4.4# exit
    exit

## Build

build and tag version:

    docker build -t docker-texlive:v1 .

*Don't this, it's just a personal reminder:* build for docker hub and push:

    docker login
    docker build -t embix/texlive-full:v1 .
    docker push embix/texlive-full:v1
