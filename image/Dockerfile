FROM ubi9:latest AS builder

RUN dnf install -y git-core golang make
RUN git clone https://github.com/jonasbjork/lernia-app.git && cd lernia-app/src && make


FROM ubi9-minimal:latest
COPY --from=builder /lernia-app/src/lernia /lernia
CMD ["/lernia"]


