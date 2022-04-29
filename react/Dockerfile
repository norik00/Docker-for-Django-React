FROM node:lts-alpine3.14
EXPOSE 3000
 
WORKDIR /front

ENV PATH /front/app/node_modules/.bin:$PATH

RUN npm install -g npm@8.1.4

ADD . .

CMD ["npm", "start"]