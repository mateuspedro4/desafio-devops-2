# Desafio-devops-2


  # Como executar o projeto:

-Baixar os arquivos.

-No terminal, iniciar as imagens:  docker-compose up -d.

-Entre no container do php: docker exec -ti <id do container> sh.
  
-Dentro do container do php, instale o mysqli: docker-php-ext-install mysqli.

-Reinicie o Apache: /etc/init.d/apache2 reload.

-Acessar o localhost pelo navegador.

Pronto

  # Como fiz


  - Primeiro: criei o diretório do projeto. Dentro dele criei o diretório 'www'.

  - Segundo: dentro do diretório do projeto, criei o arquivo docker-compose.yml.

      - No arquivo docker-compose.yml, criei o container 'php' com a imagem do php 5.6 e a imagem do apache embarcada.
  
	      - Em ports, utilizei a porta 8080 no host, e 80 na porta do container.
 
        - Em volumes, foi mapeada a pasta 'www', no host, para /var/www/html no container.
  
	     - Em links, criei um link entre este container, e o container 'db'.

    - Ainda no docker-compose, criei o container ‘db’ utilizando a imagem do mysql 5.7
  
       - Em volumes, coloquei o diretório /var/lib/mysql do container. Obs: Não consegui fazer a mapeação das pastas no mysql, como fiz no php.
       - em environment, defini a senha do usuario root.



- No diretório ‘www’ criei o index.php.
  
# Observações:

Não consegui subir um Dockerfile com as imagens pois o windows não estava conseguindo encontrar o diretório do mesmo no momento do build. Então acabei colocando as imagens dentro do Docker-compose.

Consegui conectar os dois containers, porém não com os arquivos sql e php passados.

Antes de fazer o projeto, assisti algumas vídeo aulas no youtube sobre Docker, visto que eu não era muito familiar com  o mesmo.

E utilizei de vários artigos na internet sobre PHP/MYSQL com Docker, para realizar o desafio.
