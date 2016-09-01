# reviewboard-docker

Review Board na porta 80 com docker-compose com MySQL

Rodar um container para ser o banco:

    docker run --name mysql_reviewboard -e MYSQL_ROOT_PASSWORD=review -e MYSQL_USER=review -e MYSQL_PASSWORD=review -e MYSQL_DATABASE=reviewboard -d -p 3306:3306 mysql:5.5

Trocar PGHOST para o IP do seu host

    web:
      build: ./web
      restart: always
      environment:
          - PGHOST=192.168.0.10
        
Em seguida executar:

    git clone https://github.com/Lhuckaz/reviewboard-docker.git
    cd reviewboard-docker
    docker-compose up
