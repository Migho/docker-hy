FROM node:10
WORKDIR /usr/src/app
RUN apt-get update
RUN npm install -g serve
COPY . .
RUN npm install
EXPOSE 8000
CMD ["npm","start"]