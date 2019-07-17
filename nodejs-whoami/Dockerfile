FROM node:slim
WORKDIR /usr/src/app
COPY . . 
RUN npm install ip
ENTRYPOINT ["node", "index.js"]
CMD ["Hello World!"]
EXPOSE 80/tcp
