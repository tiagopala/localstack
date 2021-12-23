# AWS SQS

## Premissas

- Possuir o aws cli instalado, ou rodar o aws cli via docker.
- Subir o docker-compose previamente.

## Uso

Abaixo estão alguns comandos que podemos utilizar para trabalharmos com as nossas filas.

### Queues

#### Criando uma fila

```aws --endpoint-url=http://localhost:4566 sqs create-queue --queue-name example-queue```

#### Exibindo as filas

```aws --endpoint-url=http://localhost:4566 sqs list-queues```

Se nenhuma fila tiver sido criada ele simplesmente não irá retornar nada.

#### Remover uma fila

```aws --endpoint-url=http://localhost:4566 sqs delete-queue --queue-url http://localhost:4566/000000000000/example-queue```

### Messages

#### Adicionar uma mensagem a fila criada acima

```
    aws --endpoint-url=http://localhost:4566 sqs send-message ^
    --queue-url http://localhost:4566/000000000000/example-queue ^
    --message-body '{'Name':'Tiago'}'
```

#### Receber a mensagem criada acima

```aws --endpoint-url=http://localhost:4566 sqs receive-message --queue-url http://localhost:4566/000000000000/example-queue```