FROM node:17-alpine3.14

LABEL maintainer="teste"

RUN mkdir /var/node

WORKDIR /var/node

COPY app.js .

EXPOSE 8080

CMD [ "node" , "app.js"]

#Para executar o arquivo acima digitar -> docker build -t nomeDesejado .   //O ponto indica o diretório atual

#Para já setar uma variável de ambiente usar docker run -e PORT=5000 nomeDaImagem por exemplo no Nodejs onde tem process.env.PORT 
  irá pegar essa porta

 ARG VERSION
 #O que foi passado acima como parametro a variável VERSION é passada para o comando abaixo dentro das chaves.

 ENV VERSION=${VERSION:-1.0.0}

 CMD [ "node" , "app.js"]

 #Para executar digitar -> docker build --build-arg VERSION=1.1.0 -t NomeEscolhidoParaAImagem .