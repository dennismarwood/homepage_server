FROM rust:1.62 AS builder
COPY . /CONTEXT
WORKDIR /CONTEXT
RUN cargo build --release

FROM debian:buster-slim
#Must have the toml file or rocket will listen on localhost in the container.
COPY --from=builder /CONTEXT/Rocket.toml /Rocket.toml
COPY --from=builder /CONTEXT/target/release/front /front

#We pass in the values from the prior layer (defined as "builder" above) to our new layer. 