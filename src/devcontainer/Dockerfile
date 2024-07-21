# Use a base image with Docker installed, such as Docker's dind image
FROM docker:dind

# Install essential packages
RUN apk add --no-cache \
    bash \
    git \
    curl \
    ca-certificates

# Switch to a non-root user (optional, recommended)
RUN adduser -D developer
USER developer

# Set working directory
WORKDIR /workspace
