FROM node:12.16.1-alpine as builder

WORKDIR /usr/app

COPY ./package.json .
RUN npm install
COPY . .
RUN npm run build

EXPOSE 80

FROM nginx:1.19.4-alpine
COPY --from=builder /usr/app/build /usr/share/nginx/html
