# Informações úteis - Docker
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

### Informativos

Ao Executar o comando  `docker-ps -a` ou `docker-ps` será exibidos algumnas informações sobre os containers, segue abaixo o que cada uma representa.

1. **CONTAINER ID** - Exibi os containers que estão rodando(ativos) na sua máquina.]

2. **IMAGE** - A imagem que foi utiliza pelo container para subir 

3. **COMMAND** - Apresentar o comando que foi executado, o normalmente chamando também de entrypoint.O container executar internamente o comando apresentado

4. **CREATED** - Data de criação do container

5. **STATUS** - Status do container atualmente

6. **PORTS** - Portas que foram utilizadas pelo container. 
Um ponto importate normalmente essa coluna pode ter um valor por exemplo assim  `0.0.0.0:80->80`, isso significa que todos solicitação feita 0.0.0.0:80 (localhost:80) no nível da sua máquina será redirecionada para porta 80 do container que está sendo executado

7. **NAMES** - Nome do container



