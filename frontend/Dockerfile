# Stage 1: Build
FROM node:18 AS builder

WORKDIR /app

COPY . .

RUN npm install
RUN npm run build

# Stage 2: Production
FROM nginx:latest

COPY --from=builder /app/build /usr/share/nginx/html