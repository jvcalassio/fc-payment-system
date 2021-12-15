# Sistema de Pagamentos Fincycle

_Desenvolvido durante a [Imersão Full Stack && Full Cycle](https://imersao.fullcycle.com.br/evento/)._

Neste projeto, é implementada uma solução para um sistema de pagamentos com o objetivo de aprender um pouco mais sobre conceitos de microsserviços, containers, kubernetes, clean architecture, e diferentes linguagens e ferramentas.

No sistema, há uma interface web para consulta das ordens de pagamento. Essa interface se comunica com um backend através de uma API REST. O servidor backend salva cada ordem e se comunica com um serviço que é responsável por processar cada pagamento (como uma operadora de cartão de crédito) e retornar se foi aprovada ou não.

![Diagrama do sistema](/model/c4model.png "Diagrama do sistema")

## Tecnologias

Todo o sistema é baseado em microsserviços, e foram desenvolvidos utilizando containers Docker.

Kubernetes é utilizado para orquestração dos containers em produção.

## Frontend

##### [jvcalassio/fc-frontend](https://github.com/jvcalassio/fc-frontend)

O frontend do sistema foi desenvolvido em React, utilizando o framework Next.js.
Há um serviço para realizar a renderização em servidor.

## Backend

##### [jvcalassio/fc-backend](https://github.com/jvcalassio/fc-backend)

O backend foi desenvolvido em Nest.js e é responsável por disponibilizar a API REST e armazenar todas as ordens de pagamento.

## Processamento do pagamento

##### [jvcalassio/fc-payment-gateway](https://github.com/jvcalassio/fc-payment-gateway)

Cada pagamento é processado através de um serviço desenvolvido em Golang, que analisa a transação, valida e comunica o resultado ao backend.

## Comunicação

Os serviços se comunicam entre si através do Apache Kafka, fora a já citada API REST.

---

## Execução em desenvolvimento:

Para execução em modo de desenvolvimento, é utilizado o [Docker Compose](https://docs.docker.com/compose/install/).

É necessário clonar este repositório, e também o repositório de cada microsserviço.

```
    git clone https://github.com/jvcalassio/fc-payment-system.git
    cd fc-payment-system
    git clone https://github.com/jvcalassio/fc-payment-gateway.git
    git clone https://github.com/jvcalassio/fc-backend.git
    git clone https://github.com/jvcalassio/fc-frontend.git
```

E então, executar o docker compose deste repositório, que irá subir os containers de todos os serviços:

```
    docker-compose up -d
```

Se tudo ocorrer como esperado, será possível acessar o frontend no endereço http://host.docker.internal:3001

Para o correto funcionamento, é necessário que o endereço _host.docker.internal_ aponte para _127.0.0.1_ no arquivo hosts de seu sistema.
