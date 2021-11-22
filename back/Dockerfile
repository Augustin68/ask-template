# Dev container
FROM node:16-alpine as runner

ENV NODE_ENV=development

COPY . /app

WORKDIR /app

RUN yarn install

EXPOSE 3630/tcp

CMD yarn start

# Prod container

FROM runner as builder

ENV NODE_ENV=production

COPY package*.json ./

RUN yarn install
CMD yarn start