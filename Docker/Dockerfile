FROM node:16

WORKDIR /app

COPY package.json ./

RUN npm install

RUN npx eslint

RUN npx eslint --init @eslint/config

RUN npm install prettier

RUN npm run prettier

COPY . ./

RUN npm run build

RUN npm install jest

RUN npm run test

EXPOSE 3000

CMD ["npm","start"]