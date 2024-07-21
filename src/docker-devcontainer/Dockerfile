# syntax=docker/dockerfile:1.4


# =============================================================================
# Base Image
# =============================================================================

# Use a base image with Docker installed, such as Docker's dind image
FROM docker:dind as base

# # Utilize build arguments to control versions and other parameters
# ARG BASH_VERSION=5.1.16-r0
# ARG GIT_VERSION=2.36.2-r0
# ARG CURL_VERSION=7.83.1-r3
# ARG CA_CERTIFICATES_VERSION=20220614-r0

# # Install essential packages using specific versions to ensure reproducibility
# RUN --mount=type=cache,target=/var/cache/apk \
#     apk add --no-cache \
#     bash=${BASH_VERSION} \
#     git=${GIT_VERSION} \
#     curl=${CURL_VERSION} \
#     ca-certificates=${CA_CERTIFICATES_VERSION}

# Install essential packages
RUN --mount=type=cache,target=/var/cache/apk apk add --no-cache \
    bash \
    git \
    curl \
    ca-certificates

# =============================================================================
# User Configuration
# =============================================================================

FROM base AS runner

# Create a non-root user with a specific user ID for better security and compatibility
ARG USER_ID=1000
ARG GROUP_ID=1000

RUN addgroup -g ${GROUP_ID} developer && \
    adduser -D -u ${USER_ID} -G developer developer

USER developer

# Set the working directory
WORKDIR /workspace

# Healthcheck to ensure Docker daemon is running (optional)
HEALTHCHECK --interval=30s --timeout=30s --start-period=5s --retries=3 \
  CMD docker info || exit 1