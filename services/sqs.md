# AWS SQS

## Premissas

- Possuir o aws cli instalado, ou rodar o aws cli via docker.
- Subir o docker-compose previamente.

## Uso

### Criando uma fila

```aws --endpoint-url=http://localhost:4566 sqs create-queue --queue-name example-queue```

### Exibindo as filas

```aws --endpoint-url=http://localhost:4566 sqs list-queues```

Se nenhuma fila tiver sido criada ele simplesmente não irá retornar nada.