FROM node:20

WORKDIR /app

COPY package.json ./

RUN npm install

RUN npm install eslint prettier jest

COPY . ./

RUN npm run dev

EXPOSE 3000

CMD ["npm","start"]