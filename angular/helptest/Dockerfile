FROM   node:alpine3.16 as build
RUN mkdir -p /app

WORKDIR /app

COPY package.json /app/
RUN   npm install

COPY . /app/
RUN npm run build --prod

# finall stage
# helptest project name
FROM  nginx:alpine
COPY --from=build  /app/dist/helptest /usr/share/nginx/html
