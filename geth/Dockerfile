FROM golang:1.19-bullseye

RUN apt-get update -y \
    && apt-get upgrade -y \
    && mkdir /geth

WORKDIR /geth

RUN git clone -b master https://github.com/ethereum/go-ethereum.git

WORKDIR /geth/go-ethereum

RUN make geth

CMD [ "./build/bin/geth" ]
