# O arquivo Dockerfile pode ser descrito como uma receita para subir um container,executar diversos passos dentro do container e te entregar tudo pronto.

# Todo Dockerfile inicia a partir de uma imagem existente.
FROM nginx:latest

#Sempre executa esse comando e ele não pode ser alterado. 
ENTRYPOINT ["echo","Gostando do material?"]

#Executa um comando e ele pode ser substituido. Esse comando pode ser modificado e serve como parametro pare ENTRYPOINT
CMD ["Mande uma estrela para mim no repositorio!!!"]

#Executar o um comando dentro do container. Nesse caso instalamos um vim dentro do container  criado.
RUN apt-get update && apt-get install vim -y

# O diretorio que você vai trabalhar dentro do container
WORKDIR /usr/share/nginx/html

# Copia o diretorio html da máquina para dentro do container no diretório  /usr/share/nginx/html
COPY html /usr/share/nginx/html







