FROM node

#install app dependencies
COPY package.json .
RUN npm install 

#bundle app source
COPY . .

EXPOSE 8080

CMD ["node", "new-server"]

