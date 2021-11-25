# BUILD SPA
FROM node:14-alpine AS build

WORKDIR /app

COPY package.json ./
COPY package-lock.json ./

RUN yarn

COPY . ./

ENV VUE_APP_API_ENDPOINT=http://localhost:4001/api

RUN yarn build

# RUN Frontend
FROM nginx:alpine AS production

COPY --from=build /app/dist /app
COPY nginx.conf /etc/nginx/nginx.conf