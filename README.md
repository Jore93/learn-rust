# Learning Rust

Folders will contain small programs. `Dockerfile.example` is template for Dockerfile used in the folder to create application inside the Docker container.

### Build and run Docker image
```
$ docker build -t my-rust-app .
$ docker run -it --rm --name my-running-app my-rust-app
```

### Compiling application inside the Docker container
There may be occasions where it is not appropriate to run your app inside a container. To compile, but not run your app inside the Docker instance, you can write something like:
```
$ docker run --rm --user "$(id -u)":"$(id -g)" -v "$PWD":/usr/src/myapp -w /usr/src/myapp rust:1.23.0 cargo build --release
```
This will add your current directory, as a volume, to the container, set the working directory to the volume, and run the command cargo build --release. This tells Cargo, Rust's build system, to compile the crate in myapp and output the executable to target/release/myapp.

Source for the [above instructions](https://hub.docker.com/_/rust/).

## 00_hello_world
Simple `Hello World!` example in Rust.
