FROM node:18-slim AS builder
COPY . /home/app/
WORKDIR /home/app
RUN npm install
RUN npm run build


FROM nginx:stable-alpine-slim
COPY --from=builder /home/app/dist/sgcmapp /usr/share/nginx/html
COPY --from=builder /home/app/nginx.conf  /etc/nginx/conf.d/default.conf
EXPOSE 80