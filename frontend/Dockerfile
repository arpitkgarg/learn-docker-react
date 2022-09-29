FROM node:18-alpine as builder

WORKDIR /usr/app/frontend

COPY ./frontend/package.json /usr/app/frontend
RUN npm install

COPY ./frontend /usr/app/frontend

RUN npm run build


FROM nginx
COPY --from=builder /usr/app/frontend/build /usr/share/nginx/html

