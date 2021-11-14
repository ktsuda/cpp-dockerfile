FROM amd64/alpine:latest
RUN apk update && \
  apk add --no-cache gcc libc-dev g++ make cmake wget git && \
  rm -rf /var/cache/
WORKDIR /tmp
RUN wget https://github.com/google/googletest/archive/refs/tags/release-1.11.0.zip && \
  unzip release-1.11.0.zip && \
  cd googletest-release-1.11.0 && \
  cmake -S . -B build && \
  cmake --build build && \
  cmake --install build && \
  cd .. && \
  rm -rf release-1.11.0.zip googletest-release-1.11.0
CMD ["/bin/ash"]
