FROM rust:1.67 AS builder

WORKDIR /todo
COPY . /todo
RUN cargo build --release

FROM gcr.io/distroless/cc
COPY --from=builder /todo/target/release/todo /
CMD ["./todo"]
