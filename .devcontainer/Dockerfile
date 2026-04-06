FROM docker.io/library/node:22-bookworm

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update && apt-get install -y --no-install-recommends \
  ffmpeg \
  git \
  sudo \
  libasound2 \
  libatk-bridge2.0-0 \
  libatk1.0-0 \
  libcups2 \
  libdbus-1-3 \
  libdrm2 \
  libgbm1 \
  libglib2.0-0 \
  libgtk-3-0 \
  libnss3 \
  libx11-xcb1 \
  libxcomposite1 \
  libxdamage1 \
  libxext6 \
  libxfixes3 \
  libxkbcommon0 \
  libxrandr2 \
  libxshmfence1 \
  libxss1 \
  libxtst6 \
  procps \
  x11-apps \
  xauth \
  && rm -rf /var/lib/apt/lists/*

# Allow the node user to run sudo without a password (needed for X11 socket setup)
RUN echo "node ALL=(ALL) NOPASSWD:ALL" > /etc/sudoers.d/node && chmod 440 /etc/sudoers.d/node

RUN corepack enable && corepack prepare yarn@4.11.0 --activate

ENV ELECTRON_DISABLE_SANDBOX=1
ENV CHOKIDAR_USEPOLLING=1

WORKDIR /workspaces/lossless-cut-lab
