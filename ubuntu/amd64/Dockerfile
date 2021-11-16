FROM ubuntu:18.04
RUN apt-get update && \
  DEBIAN_FRONTEND=noninteractive apt-get install -y \
    build-essential cmake clang libssl-dev wget unzip && \
  apt-get clean && \
  rm -rf /var/lib/apt/lists/*
WORKDIR /tmp
RUN wget https://github.com/google/googletest/archive/refs/tags/release-1.11.0.zip && \
  unzip release-1.11.0.zip && \
  cd googletest-release-1.11.0 && \
  mkdir -p build && \
  cd build && \
  cmake .. && \
  make && \
  make install && \
  cd ../../ && \
  rm -rf release-1.11.0.zip googletest-release-1.11.0
CMD ["/bin/sh"]
