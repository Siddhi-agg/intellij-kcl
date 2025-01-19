FROM mcr.microsoft.com/devcontainers/java:17

# Install additional packages
RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
    && apt-get -y install --no-install-recommends \
    wget \
    unzip \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

# Set up environment variables for Java
ENV JAVA_HOME="/usr/lib/jvm/java-17-openjdk-amd64"
ENV PATH="${JAVA_HOME}/bin:${PATH}"

# Create directories for IntelliJ plugin development
RUN mkdir -p /workspace/src/main/gen

# Copy jflex and skeleton files to a common location
RUN mkdir -p /usr/local/bin