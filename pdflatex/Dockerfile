FROM alpine:3.8

# install TeX Live 20170524
RUN apk --no-cache add texlive-full

RUN pdflatex --version

WORKDIR /sources

VOLUME ["/sources"]

ENTRYPOINT [ "pdflatex" ]

CMD [ "--help" ]