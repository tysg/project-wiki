# syntax=docker/dockerfile

# Builder image for compilation
FROM tysg/fedora-cmake:latest AS builder

# Final image with autotester executable
FROM builder
ARG CMAKE_BUILD_TYPE=Release

WORKDIR /data

COPY Team00 .
WORKDIR /data/Code00/build

RUN cmake -DCMAKE_BUILD_TYPE=${CMAKE_BUILD_TYPE} ..
RUN make -j $(nproc)
RUN ln -s "/data/Code00/build/src/autotester/autotester" "/usr/bin/autotester"

CMD "/bin/bash"