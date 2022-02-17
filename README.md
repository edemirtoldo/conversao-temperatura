# Kubedev - Desafio Docker - Questão 03

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

.dockerignore

```bash
node_modules/
```
 
Processo de construção da imagem com Dockerfile

```bash
docker image build -t edemirtoldo/conversao-temperatura:v1 .
```
Enviar a imagem v1 para o Docker Hub.

```bash
docker push edemirtoldo/conversao-temperatura:v1
```

Vamos fazer um TAG da imagem.

```bash
docker tag edemirtoldo/conversao-temperatura:v1 edemirtoldo/conversao-temperatura:latest
```

Enviar a imagem latest para o Docker Hub.

```bash
docker push edemirtoldo/conversao-temperatura:latest
```

Executar a aplicação NodeJS em container.

```bash
docker container run -d -p 8080:8080 --name conversao-temperatura  edemirtoldo/conversao-temperatura:v1
```

Link de acesso a aplicação de conversão de temperatura <http://localhost:8080/>

Aplicação Conversão de Temperatura em NodeJS

![nodejs](https://github.com/edemirtoldo/conversao-temperatura/blob/main/img/conversaotemperatura.png)
