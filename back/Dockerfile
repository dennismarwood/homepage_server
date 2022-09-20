FROM rust:1.62 AS builder
COPY . /CONTEXT
WORKDIR /CONTEXT
RUN cargo build --release
RUN cargo install diesel_cli --version 1.4.1 --no-default-features --features mysql
#RUN diesel migration run --database-url="mysql://

#FROM debian:buster-slim
#Must have the toml file or rocket will listen on localhost in the container.
#COPY --from=builder /CONTEXT/Rocket.toml /Rocket.toml
#COPY --from=builder /CONTEXT/target/release/back /back

#We pass in the values from the prior layer (defined as "builder" above) to our new layer. 

#RUN ["apt", "update", "-y"]
#RUN ["apt", "install", "libmariadb-dev-compat", "-y"]

#Unfortunately, a C library that diesel has as a dependency relies on a library found in most os, but not in buster-slim.
#https://stackoverflow.com/questions/62396248/why-rustc-did-not-include-libmariadb-into-release-binary