Entre em uma imagem com o comando abaixo
   1) docker run -ti nomeImagem sh
   2)  Após isso crie um usuário com o comando abaixo
          adduser -h /var/teste -s /bin/bash -D nomeUser
          getent passwd -> para ver o novo diretório

   Modificar o docker file para

                  FROM node:17-alpine3.14

                  LABEL maintainer="teste"
                 
                  #A OPÇÃO ABAIXO É ÓTIMA POIS JÁ CRIA UM VOLUME AUTOMATICAMENTE, O PROFESSOR DISSE QUE NA AWS JÁ RESOLVEU UM 
                    PROBLEMA PARA ELE

                  VOLUME ['/var/nomeUser/]  

                  RUN  adduser -h /var/nomeUser -s /bin/bash -D nomeUser

                  WORKDIR /var/nomeUser

                  COPY app.js .

                  RUN  chown nomeUser:nomeUser arquivo.js 

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

      OBS: Agora se você entrar na imagem com 'docker run  -it nomeImagem sh' e digitar ls -l vai observar que está com o usuário criado
     Depois digitar docker run -d -e PORT=3000 rico123
     Depois pegar o id gerado e digitar  docker exec idGerado ps aux
     Depois digitar 'ps aux | grep rico' para ver os processos com rico