FROM node:latest as builder

WORKDIR /app
COPY . .
RUN npm install
RUN npm run build


# Nginx image
FROM nginx:latest

COPY --from=builder /app/dist/ngApp /usr/share/nginx/html/

EXPOSE 80