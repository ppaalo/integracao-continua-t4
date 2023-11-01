FROM node:18-alpine AS build
WORKDIR /dist/src/app
RUN npm cache clean --force

COPY . .
RUN npm install -g @angular/cli@16
RUN npm install
RUN ng build

COPY --from=build /dist/src/app/dist/sgcmapp/ /usr/share/nginx/html
COPY /nginx.conf  /etc/nginx/conf.d/default.conf
EXPOSE 80