FROM arm64v8/ubuntu:latest

RUN apt-get update && \
    apt-get install -y curl libssl-dev git build-essential && \
    curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh -s -- -y && \
    export PATH=$PATH:$HOME/.cargo/bin && \
    git clone https://github.com/casey/ord.git && \
    cd ord && \
    cargo build --release

EXPOSE 8080

CMD ["ord", "-r","server"]
