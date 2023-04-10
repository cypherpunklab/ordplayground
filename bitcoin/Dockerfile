FROM arm64v8/ubuntu:latest

RUN apt-get update && \
    apt-get install -y wget && \
    wget https://bitcoincore.org/bin/bitcoin-core-24.0.1/bitcoin-24.0.1-aarch64-linux-gnu.tar.gz && \
    tar xzf bitcoin-24.0.1-aarch64-linux-gnu.tar.gz && \
    install -m 0755 -o root -g root -t /usr/local/bin bitcoin-24.0.1/bin/*

RUN mkdir -p /root/.bitcoin

RUN echo "regtest=1" >> /root/.bitcoin/bitcoin.conf
RUN echo "rpcallowip=0.0.0.0/0" >> /root/.bitcoin/bitcoin.conf
RUN echo "rpcbind=0.0.0.0" >> /root/.bitcoin/bitcoin.conf
RUN echo "[regtest]" >> /root/.bitcoin/bitcoin.conf
RUN echo "rpcuser=myusername" >> /root/.bitcoin/bitcoin.conf
RUN echo "rpcpassword=mypassword" >> /root/.bitcoin/bitcoin.conf

EXPOSE 18444 18443

CMD ["bitcoind", "-regtest"]
