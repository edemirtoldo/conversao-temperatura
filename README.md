# Desafio Docker - Questão 03

## Aplicação escrita em NodeJS

Dockerfile
```bash
FROM node:14.17.5
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
EXPOSE 8080
CMD ["node", "server.js"]
```
 
processo de construção da imagem

docker image build -t conversao-temperatura .

rodar a aplicação em container

docker container run -d -p 8080:8080 conversao-temperatura


```bash

```
