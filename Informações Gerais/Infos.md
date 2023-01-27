# Informações Úteis - Docker
<img src="https://www.svgrepo.com/show/373553/docker.svg" align="right"
     alt="Docker" width="120" height="178">

### Comandos
1. `docker-ps` - Exibi os containers que estão rodando(ativos) na sua máquina.

2.  `docker-ps -a` - Exibi os containers ativos e os que já foram executados mas morreram.

3.  `docker run -it image-name bash` - Um contaner será executado, porém os parâmetros `-it` ou `-i -t` que foram adicionados tem outra definição. O `-i` representa um modo interativo, basicamente esse parametro libera o terminal e mantém o processo sendo executado. O `-t` representar tty, ele permite a digitação no terminal.

4. `docker run -it --rm image-name bash` - Executa o mesmo comando citado acima, porém o parametro `--rm` faz com que todo processo de container que subir usando ele ao ser encerrado o container será deletado automáticamente.
 

 5. `docker run -p 8080:80 nginx` - Executar um container normalmente, porém  o parametro `-p 8080:80` faz com que ao acessar a porta 8080 da sua máquina o docker redirecione para porta 80 do nginx. 

 6. `docker run -d -p 8080:80 nginx` - Executa o mesmo comando citado acima, porém o parametro `-d`liberar o terminal para uso, ou podemos dizer que ele faz o detached. 

7. `docker rm id_do_container` - Ele remove o container usando o id .

8. `docker run -d --name nginx -p 80:80 -v ~/Projetos/Docker/html-to-bind-mount:/usr/share/nginx/` - O comando vai subir um container do nginx com um apelido nginx, porém com alguns detalhes. O parametro `-v ~/Projetos/Docker/html-to-bind-mount:/usr/share/nginx/` está fazendo o que chamamos de bind mounts, ou seja ele está mapeando um diretorio da sua máquina para dentro do container, no meu caso tudo estiver dentro do diretório `~/Projetos/Docker/html-to-bind-mount` da minha máquina será disponibilizado ou linkado no diretório `/usr/share/nginx/` do container do nginx. (Experimente criar um arquivo index.html no diretório da sua máquina e acesse localhost).

10.  `docker rmi ubuntu` - Faz a deleção de uma imagem, nesse caso a imagem ubuntu.

9. `docker run -d --name nginx -p 80:80 --mount type=bind,source="$(pwd)",target=/usr/share/nginx/html nginx` -  Esse comando tem como objetivo executar o mesmo recurso do tópico 8, porém essa é uma versão mais atualizda. O paramêtro `--mount type=bind,source="$(pwd)",target=/usr/share/nginx/html nginx` tem a mesma responsabilidade do anterior, com mais detalhe.O termo `type=bind` define o tipo de mapeamento que será feito,  `source="$(pwd)"` pega o diretório que você está para mapear para dentro do container e `target=/usr/share/nginx/html` como o nome diz define a pasta alvo dentro do container para fazer bind. 
### Informativos

Ao Executar o comando  `docker-ps -a` ou `docker-ps` será exibidos algumnas informações sobre os containers, segue abaixo o que cada uma representa.

1. **CONTAINER ID** - Representa o identificado do container ou nesse caso um id único

2. **IMAGE** - A imagem que foi utiliza pelo container

3. **COMMAND** - Apresenta o comando que foi executado, normalmente chamando também de entrypoint.O container executar internamente o comando apresentado

4. **CREATED** - Data de criação do container

5. **STATUS** - Status do container atualmente

6. **PORTS** - Portas que foram utilizadas pelo container. 
Um ponto importate normalmente essa coluna pode ter um valor por exemplo assim  `0.0.0.0:80->80`, isso significa que todos solicitação feita 0.0.0.0:80 (localhost:80) no nível da sua máquina será redirecionada para porta 80 do container que está sendo executado

7. **NAMES** - Nome ou apelido do container. Gerado automáticamente se você não definir um durante o processo de subir um container

### Volumes

Volumes são diretórios externos ao container que são montados diretamente nele.


### Imagens
