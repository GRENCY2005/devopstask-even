
FROM node:18-alpine AS build

WORKDIR /app
COPY package*.json ./
RUN npm install --production

COPY . .


FROM node:18-alpine

WORKDIR /app
COPY --from=build /app /app

ENV PORT=5000
EXPOSE 5000

CMD ["node", "server.js"]
