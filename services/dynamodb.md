# AWS DynamoDB
## Premissas

- Possuir o aws cli instalado, ou rodar o aws cli via docker.
- Subir o docker-compose previamente.

## Uso

Abaixo estão alguns comandos que podemos utilizar para trabalharmos com o dynamodb localmente.

### Tabelas

#### Criar uma tabela

```
aws --endpoint-url=http://localhost:4566 dynamodb create-table ^
--table-name ExampleTable ^
--attribute-definitions ^
AttributeName=IdPk,AttributeType=S ^
--key-schema ^
AttributeName=IdPk,KeyType=HASH ^
--provisioned-throughput ^
ReadCapacityUnits=5,WriteCapacityUnits=5
```

#### Exibir as tabelas existentes

```aws --endpoint-url=http://localhost:4566 dynamodb list-tables```

#### Excluir uma tabela

```aws --endpoint-url=http://localhost:4566 dynamodb delete-table --table-name ExampleTable```

### Itens

#### Adicionar um item a tabela

```
aws --endpoint-url=http://localhost:4566 dynamodb put-item --table-name ExampleTable ^
--item "{\"IdPk\":{\"S\":\"3D5C3E3F-7188-49B2-9566-E27A3CFBC013\"},\"Name\":{\"S\":\"Tiago\"}}"
```

#### Remover um item a tabela

```aws --endpoint-url=http://localhost:4566 dynamodb delete-item --table-name ExampleTable --key {\"IdPk\":{\"S\":\"3D5C3E3F-7188-49B2-9566-E27A3CFBC013\"}}```