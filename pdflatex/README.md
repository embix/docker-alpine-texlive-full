# [embix/pdflatex](https://hub.docker.com/r/embix/pdflatex/)

run pdflatex without the hassle of manually installing miktex or texlive, i.e. on your builserver

## Usage

use from windows/powershell

    docker run -it --rm -v ${PWD}:/sources embix/pdflatex:v1  ./main.tex

* `-it` is actually `-i` interactive with `-t` terminal so we can see if pdflatex is complaining and fix it on-demand
* `--rm` dispose container once we're finished, no need to keep it running
* `-v ${PWD}:/sources` use your current directory as workdir, docker may ask you to allow accessing that drive from the container. It should contain everything needed to build the pdf (main tex, includes, images, bib and so on). Most likely this is your *sources*  repository. You do version your tex input in a [git](https://git-scm.com/book/en/v2/Getting-Started-About-Version-Control) repo, don't you? If not, do it now - automating pdf generation can wait.
* `./main.tex` whatever your *entry*-texfile is

Consider putting that line in a script itself and committing it to your sources repository.

`pdflatex` is the entry point of that image. If you don't pass a filename or parameters, `--help` will be used as default parameter. Of course you can pass additional pdflatex parameters between the image and the entry file name.

if you feel the need to fiddle around with other tex related commands, see [embix/texlive-full](https://hub.docker.com/r/embix/texlive-full/) or related images.

## Build it yourself

    docker build -t docker-pdflatex:v1 .

within your sources then directory call

    docker run -it --rm -v ${PWD}:/sources  docker-pdflatex:v1  ./main.tex

where main.tex is your entry file

Output (`pdf`,`aux`,`toc`, etc) is generated in the same directory by default.
