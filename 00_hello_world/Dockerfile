FROM rust:latest

WORKDIR /usr/src/hello-world
COPY . .

RUN cargo install --path .

CMD ["hello-world"]
