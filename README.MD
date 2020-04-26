# Gerador de UUID v4

Esse é uma API bem simples feito em kotlin, utilizando o framework Ktor, que gera um UUID aleatório.

O intuito é mostrar como subir uma aplicação rodando docker no heroku.
Faça um fork do código, e siga os comando abaixo.

## Tecnologias usadas
* KTOR - Servidor de Aplicação
* DOCKER - Conteiner que armazena a aplicação
* HEROKU - Armazenamento do docker

# Preparar o HEROKU
* Fazer uma conta
* Criar um novo app chamado `generator-uuid`

# Como subir a aplicação pelo Ubuntu
CRTL+ALT+T para abrir o terminal

Vá até a pasta raiz do projeto, para rodar os comandos.

* Construir o projeto
`./gradlew build`
* Construir a imagem do dockerfile
`sudo docker build -t generator-uuid-api .`
* Subir a aplicação no docker
`sudo docker run -m512M --cpus 2 -it -p 8080:8080 --rm generator-uuid-api`
Obs: Nesse momento, a aplicação já está funcionando localmente, e pode ser acessado por `http://localhost:8080`
* Fazer login no heroku
`heroku login`
* Logar a container docker no heroku
`sudo heroku container:login`
* Subir o container local para a nuvem do heroku
`sudo heroku container:push web -a generator-uuid` Obs. "generator-uuid" é o nome do app no heroku
* Disponibilizar o app
`sudo heroku container:release web -a generator-uuid`


Thanks! =)
