FROM node:18

RUN mkdir /app && chown node:node /app
USER node
WORKDIR /app
EXPOSE 8080

COPY --chown=node:node package*.json /app/
RUN ls -la
RUN npm ci

COPY . /app/
CMD [ "server.js" ]
