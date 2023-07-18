FROM node:13-alpine
WORKDIR /app
COPY package.json /app
RUN npm install
COPY . /app
RUN npm run build


FROM nginx:1.17-alpine
WORKDIR /app
COPY --from=0 /app/dist /usr/share/nginx/html
EXPOSE 80
