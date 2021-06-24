FROM mattcen/sshbase

# Install documentation that was removed to minimize container image size
RUN yes | unminimize \
  && apt-get clean \
  && rm -rf /var/lib/apt/lists/*

# Pre-install these packages
RUN apt-get update \
  && apt-get install -y \
  man-db \
  && apt-get clean \
  && rm -rf /var/lib/apt/lists/*

# Pre-download these packages, but don't install them
# Speed up subsequent user package installation by pre-downloading package
# cache and required packages.
RUN apt-get update && apt-get -dy install \
  nano \
  nginx

EXPOSE 80 22
