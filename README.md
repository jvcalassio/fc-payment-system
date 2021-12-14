# Sistema de Pagamentos FC

Desenvolvido durante a [Imersão Full Stack && Full Cycle](https://imersao.fullcycle.com.br/evento/).

Neste projeto, é implementado uma solução para um sistema de pagamentos.

São utilizados conceitos de microserviços, TDD, clean architecture, e diferentes linguagens e ferramentas
para compor cada parte do sistema:

## Frontend

O frontend foi desenvolvido em Next.js

## Backend

O backend foi desenvolvido em Nest.js (npm), e processa os pedidos vindos do front-end.

## Pagamento

Os pagamentos de cada pedido são processados em uma aplicação desenvolvida em Golang.

## Comunicação

Os serviços se comunicam entre si através do Apache Kafka, e a comunicação do backend com o frontend é feita através
de APIs REST.

---

## Executar:

Executar com o Docker Compose (modo desenvolvimento)

```
    docker-compose up -d
```
