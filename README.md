# tquic-example-rust

Rust examples of using [TQUIC](https://github.com/Tencent/tquic) on Linux.

## Requirements

Refer to the [TQUIC](https://tquic.net/docs/getting_started/installation#prerequisites) prerequisites.

## Build

```shell
cargo build
```

## Run simple_server

Generate certificate and key.

```shell
cd target/debug
openssl genrsa -out cert.key 2048
openssl req -new -x509 -days 36500 -key cert.key -out cert.crt -subj "/CN=example.org"
```

Run simple_server.

```shell
./simple_server
```

## Run simple_client

```shell
cd target/debug
./simple_client -c 127.0.0.1:4433
```