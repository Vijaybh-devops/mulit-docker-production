From node:alpine as builder
workdir /app
copy ./package.json ./
RUN npm  install
copy ./ ./
RUN ["npm", "run", "build"]

From nginx
expose 3000
copy ./nginx/default.conf /etc/nginx/conf.d/default.conf
copy --from=builder  /app/build /usr/share/nginx/html/

