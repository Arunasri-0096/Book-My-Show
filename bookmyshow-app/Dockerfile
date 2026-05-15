FROM node:18

WORKDIR /app

COPY package*.json ./

RUN npm install --legacy-peer-deps

RUN npm install chokidar watchpack-chokidar2 --legacy-peer-deps

COPY . .

ENV NODE_OPTIONS=--openssl-legacy-provider
ENV HOST=0.0.0.0
ENV PORT=3000

EXPOSE 3000

CMD ["npm", "start"]
