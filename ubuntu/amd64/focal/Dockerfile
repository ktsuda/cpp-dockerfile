FROM ubuntu:20.04
RUN apt-get update && \
  DEBIAN_FRONTEND=noninteractive apt-get install -y \
    build-essential clang libssl-dev wget unzip tzdata && \
  apt-get clean && \
  rm -rf /var/lib/apt/lists/*
WORKDIR /tmp
RUN wget https://github.com/Kitware/CMake/releases/download/v3.21.4/cmake-3.21.4-linux-x86_64.tar.gz && \
  tar -xzf cmake-3.21.4-linux-x86_64.tar.gz -C /usr/local --strip-components=1 && \
  rm -rf cmake-3.21.4-linux-x86_64.tar.gz
RUN wget https://github.com/google/googletest/archive/refs/tags/release-1.11.0.zip && \
  unzip release-1.11.0.zip && \
  cd googletest-release-1.11.0 && \
  mkdir -p build && \
  cmake -S . -B build && \
  cmake --build build && \
  cd .. && \
  rm -rf release-1.11.0.zip googletest-release-1.11.0
RUN apt-get update && \
  DEBIAN_FRONTEND=noninteractive apt-get install -y \
    libiio-dev && \
  apt-get clean && \
  rm -rf /var/lib/apt/lists/*
CMD ["/bin/bash"]
