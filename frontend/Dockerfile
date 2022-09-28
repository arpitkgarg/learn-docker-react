FROM node:18-alpine as builder

WORKDIR /usr/app/frontend

COPY package.json /usr/app/frontend
RUN npm install

COPY ./ /usr/app/frontend

RUN npm run build


FROM nginx
COPY --from=builder /usr/app/frontend/build /usr/share/nginx/html

