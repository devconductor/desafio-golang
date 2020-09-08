### Desafio Conductor de Seleção
Olá, queremos convidá-lo a participar de nosso desafio de seleção.  Pronto para participar? Seu trabalho será visto por nosso time e você receberá ao final um feedback sobre o que achamos do seu trabalho. Não é legal?

### Sobre a oportunidade 
Temos vagas com diversos níveis, Júnior, Pleno, Senior e Especialista, para cada um deles utilizaremos critérios específicos considerando esse aspecto, combinado? 
Se você for aprovado nesta etapa, será convidado para uma entrevista com nosso time de especialistas.

### Desafio Técnico
  
  #### Sobre a Conductor
  Oferecemos soluções em meios de pagamento para empresas de todos os tamanhos e áreas de atuação, tanto no varejo como no setor financeiro. Nossa missão é simplificar e desburocratizar suas trocas financeiras através da tecnologia, com agilidade, foco no cliente, uma visão ampla do negócio e práticas inovadoras.

  #### Nossos Números
  Por se tratar de sistemas financeiros, um dos principais desafios é conseguir ter uma alta disponibilidade, resiliência, escalabilidade e confiabilidade. Ou seja, nossos sistemas precisam ser befeitos o suficientes para atender os seguintes números:

  - 85 milhões de cartões emitods
  - 27 milhões de usuários ativos
  - 1.2 bilhões de transações por ano
  - R$ 100 bilhões processados anualmente. 
  - Mais de 520 mil PDVs e TEFs conectados aos nossos sistemas.
  - 50% de crescimento médio desde 2012

  Complexo, não? Pois é, para conseguirmos atingir esses números com excelência, precisamos de um time robusto, por isso a necessidade de aplicar tal teste. Vamos ao que interessa...


  #### O Desafio

  Nossos clientes são em sua maioria bancos, fintechs e varejistas, muitos ofertão para usuários, além de cartõs de créditos, contas digitais, pagamentos de contas, transferências, recarga de celular e etc. 

  Para esse desafio iremos focar no nosso produto de emissão de cartão de crédito, esse por sua vez precisa de vários serviços, um deles é uma API que permite que os nossos clientes consumão para saber todas as transações de um determinado usuário e também de uma outra API para baixar o PDF contendo a fatura do cartão.

  Portanto, o desafio será a construção de uma API que permita a consulta de todas as transações de uma determinada conta, depois ter um outro serviço que retorne um PDF simples contendo uma tabela com as transações de uma terminada conta.

  Segue no detalhe todas as características do desafio...

  #### Premissas

  - Criar uma API REST em golang com o seguinte context Path: /conductor/v1/api/
  - Todos os end-points deverão ser documentados com Swagger/Open API.
  - Utilizar o banco de dados H2 ou SQL Lite para persistência dos dados em memória, assim facilitará a execução dos projetos durante as correções.
  - Ao subir o projeto, preencher o banco com algum dado fake para testes.
  - Criar o path GET /contas que irá retornar todas as contas com o seguinte body:
  ```json
  [
    {
      "id": "3b1b1c0c-5c68-4352-b937-e3c68b6b1b16",
      "status": "ATIVA"
    },
    {
      "id": "3b1b1c0c-5c68-4352-b937-e3c68b6b1b16",
      "status": "INATIVA"
    }    
  ]
  ```

  - Criar path GET /contas/{id} que irá retonar uma determinada conta com o seguinte body:
  ```json  
    {
      "id": "3b1b1c0c-5c68-4352-b937-e3c68b6b1b16",
      "status": "ATIVA"
    }
  ```

  - Criar path GET /contas/{id}/transacoes que irá retonar todas as transações dessa conta com o seguinte body:
  ```json  
    [
      {
        "id": "3b1b1c0c-5c68-4352-b937-e3c68b6b1b16",
        "id_conta": "45283ddc-5e40-4a75-94d2-c0894f24c911",
        "descricao": "Apple Store",
        "valor": 199.50
      },
      {
        "id": "c203b91a-91a4-41d2-8583-86401c0fb1e4",
        "id_conta": "10ba5050-c69f-40d3-bbeb-c0172520b222",
        "descricao": "Netflix",
        "valor": 27.50
      }
    ]
  ```

  - Criar path GET /contas/{id}/transacoes.pdf que irá retonar todas as transações dessa conta com no formato PDF contendo uma tabela simples com os seguintes dados:
  | CONTA | TRANSAÇÃO | VALOR |
  |-|-|-|
  |3b1b1c0c-5c68-4352-b937-e3c68b6b1b16|Apple Store|199,50|
  |c203b91a-91a4-41d2-8583-86401c0fb1e4|Netflix|27,50|

 
  - O que será diferencial:

    ```
    * GRpc;
    * Criação de Dockefile;
    * Teste Unitários;
    * C.I com Circle CI ou Github Actions;
    * Serviço ser multi tenancy;
    ```
    
  - O que vamos avaliar:

    ```
    * Seu código; 
    * Arquitetura e camadas da sua aplicação;
    * Escalabilidade do código
    * Organização do código
    * Boas práticas;
    * Diferenciais;    
    ```


### Instruções

      1. Faça o fork do desafio e torne o repositório privado.
      2. Desenvolva. Você terá até 7 (sete) dias a partir da data do envio do desafio; 
      3. Após concluir seu trabalho faça um push; 
      5. Responda ao e-mail enviado do desafio, adicionando cópia para: cc2e73ef.Conductor.onmicrosoft.com@amer.teams.ms notificando a finalização do desafio para validação.
