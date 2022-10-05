FROM docker/dev-environments-default

# docker run -d -v ~/ethereum:/ethereum -p 30303:30303 --network host --name ethjs-0 ethjs tail -f /dev/null
# DEBUG=devp2p:* npm run client:start:dev1 -- --datadir=/ethereum/ethjs/sepolia/ --network=sepolia --forceSnapSync=true &> logs/log_0.text

RUN apt-get update -y \
    && apt-get upgrade -y \
    && curl -fsSL https://deb.nodesource.com/setup_18.x | sudo -E bash - \
    && apt-get install -y nodejs build-essential

RUN mkdir /ethjs

WORKDIR /ethjs

RUN git clone --depth 1 --branch master https://github.com/ethereumjs/ethereumjs-monorepo.git

WORKDIR /ethjs/ethereumjs-monorepo

RUN npm i 

WORKDIR /ethjs/ethereumjs-monorepo/packages/client

CMD [ "npm", "run", "client:start" ]
