FROM node:14 as ionic

WORKDIR /usr/app

COPY package*.json .

RUN npm install -f

COPY . .

RUN npx ionic build

### Run 
FROM nginx:alpine
#COPY www /usr/share/nginx/html
COPY --from=ionic  /usr/app/www /usr/share/nginx/html