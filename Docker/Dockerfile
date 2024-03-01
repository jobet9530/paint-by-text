FROM node:20

WORKDIR /app

COPY package.json ./

RUN npm install

RUN npm install eslint prettier jest

COPY . ./

RUN apt-get update \
    && apt-get -y install curl gnupg \
    && curl -sL https://deb.nodesource.com/setup_16.x | bash \
    && apt-get -y install nodejs git \
    && npm install -g npm@latest \
    && curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | apt-key add - \
    && echo "deb https://dl.yarnpkg.com/debian/ stable main" | tee /etc/apt/sources.list.d/yarn.list \
    && apt-get update && apt-get install yarn

RUN npm run dev

EXPOSE 3000

CMD ["npm","start"]