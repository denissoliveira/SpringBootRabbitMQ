# SpringBootRabbitMQ



## Tutorial
https://www.rabbitmq.com/getstarted.html

## Download e Instalação 
https://www.rabbitmq.com/download.html

## Docker image

```sh
docker run -d --hostname my-rabbit --name some-rabbit -e RABBITMQ_DEFAULT_USER=user -e RABBITMQ_DEFAULT_PASS=password rabbitmq:3-management
```

- rabbitmq:3-management : com administrador habilitado.
- RABBITMQ_DEFAULT_USER : Usuário de acesso (admin e cliente)
- RABBITMQ_DEFAULT_PASS : Senha de acesso (admin e cliente)

### docker-compose.yml
```ruby
version: '3'
services:
  my-rabbitmq:
    image: rabbitmq:3-management
    hostname: fasolti-rabbitmq
    ports:
      - "15672:15672"
      - "5672:5672"
    volumes:
      - $PWD/rabbitmq:/var/lib/rabbitmq"
    environment:
      - RABBITMQ_DEFAULT_USER=admin
      - RABBITMQ_DEFAULT_PASS=admin
```     