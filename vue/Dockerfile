# Building app
FROM node:10.14.1 as build

WORKDIR /app

COPY . .

RUN npm ci --silent
RUN npm run build

# Starting NGINX
FROM nginx

COPY ./nginx.conf /etc/nginx/nginx.conf

COPY --from=build /app/dist /usr/share/nginx/html
