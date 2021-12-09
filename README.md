# Sistema de Pagamentos FC

Desenvolvido durante a [Imersão Full Stack && Full Cycle](https://imersao.fullcycle.com.br/evento/).

Neste projeto, é implementado uma solução para um sistema de pagamentos.

São utilizados conceitos de microserviços, TDD, clean architecture, e diferentes linguagens e ferramentas
para compor cada parte do sistema:

## Frontend

O frontend (será) é desenvolvido em Next.js

## Backend

O backend é desenvolvido em Nest.js (npm), e processa os pedidos vindos do front-end.

## Pagamento

Os pagamentos de cada pedido são processados em uma aplicação desenvolvida em Golang.

## Comunicação

Os serviços se comunicam entre si através do Apache Kafka, e a comunicação do backend com o frontend é feita através 
de APIs REST.

## Observabilidade

O monitoramento de tudo isso (será) é feito através do Prometheus e Grafana.

---

As diferentes partes do sistema foram reunidas em um único repositório para facilitar a organização do projeto em meu perfil, mas poderiam (e deveriam) ser separadas em repositórios individuais.

(wip, assim como os outros readmes e o restante do projeto)