FROM node:14 AS development

WORKDIR /nicholas/src/app

COPY package*.json ./

RUN npm install

RUN npm run build

EXPOSE 3000

FROM node:14 AS production

ARG NODE_ENV=production
ENV NODE_ENV=${NODE_ENV}

WORKDIR /nicholas/src/app

COPY --from=development /nicholas/src/app/ .

EXPOSE 3000

CMD [ "node", "dist/main"]
