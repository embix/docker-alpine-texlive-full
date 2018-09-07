## Build

    docker build -t docker-pdflatex:v1 .

## Usage

within your sources directory call

    docker run -it --rm -v ${PWD}:/sources  docker-pdflatex:v1  ./main.tex

where main.tex is your entry file

Output (`pdf`,`aux`,`toc`, etc) is generated in the same directory by default.
