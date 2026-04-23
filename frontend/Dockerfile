FROM node:20-slim

ARG VITE_API_BASE
ARG VITE_WS_BASE
ARG PORT

ENV VITE_API_BASE=$VITE_API_BASE
ENV VITE_WS_BASE=$VITE_WS_BASE
ENV PORT=$PORT

WORKDIR /app

# Install pnpm
RUN npm install -g pnpm

# Copy files (context is ./frontend)
COPY package.json pnpm-lock.yaml ./
RUN pnpm install

COPY . .

# Ensure the entrypoint exists in the frontend folder
RUN chmod +x /app/docker-entrypoint.sh

ENTRYPOINT ["/app/docker-entrypoint.sh"]