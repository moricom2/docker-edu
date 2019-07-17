FROM node:slim
WORKDIR /usr/src/app
COPY . . 
RUN npm install ip
ENTRYPOINT ["node", "index.js"]
CMD ["Hello World!"]
EXPOSE 8080/tcp
