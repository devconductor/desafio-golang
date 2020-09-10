### Desafio Conductor de Seleção
Olá, queremos convidá-lo a participar de nosso desafio de seleção.  Pronto para participar? Seu trabalho será visto por nosso time e você receberá ao final um feedback sobre o que achamos do seu trabalho. Não é legal?

### Sobre a oportunidade 
Temos vagas com diversos níveis, Júnior, Pleno, Senior e Especialista, para cada um deles utilizaremos critérios específicos considerando seu nível, combinado? 
Se você for aprovado nesta etapa, será convidado para uma entrevista com nosso time de especialistas.

### Desafio Técnico
  
#### Sobre a Conductor
Oferecemos soluções em meios de pagamento para empresas de todos os tamanhos e áreas de atuação, tanto no varejo como no setor financeiro. Nossa missão é simplificar e desburocratizar suas trocas financeiras através da tecnologia, com agilidade, foco no cliente, uma visão ampla do negócio e práticas inovadoras.

#### Nossos Números
Por se tratar de sistemas financeiros, um dos principais desafios é conseguir ter uma alta disponibilidade, resiliência, escalabilidade e confiabilidade. Ou seja, nossos sistemas precisam ser benfeitos o suficiente para atender os seguintes números:

  - 85 milhões de cartões emitidos;
  - 27 milhões de usuários ativos;
  - 1.2 bilhões de transações por ano;
  - R$ 100 bilhões processados anualmente;
  - Mais de 520 mil PDVs e TEFs conectados aos nossos sistemas;
  - 50% de crescimento médio desde 2012.

  Complexo, não? Pois é, para conseguirmos atingir esses números com excelência, precisamos de um time robusto, por isso a necessidade de aplicar tal teste. Vamos ao que interessa...

  #### O Desafio

  Nossos clientes são em sua maioria bancos, fintechs e varejistas, muitos ofertam para seus usuários, além de cartões de crédito, contas digitais, pagamentos de contas, transferências, recarga de celular e etc. 

  Para esse desafio iremos focar no nosso produto de emissão de cartão de crédito, esse por sua vez precisa de vários serviços, um deles é uma API que permite que os nossos clientes consumam para saber todas as transações de um determinado usuário e também de uma outra API para baixar um PDF contendo a fatura do cartão.
  
  A problemática é que quando você possuí mais de 27 milhões de usuários, a performance e escalabilidade desses serviços precisam ser muito alta, principalmente a geração de faturas em PDF, essa por sua vez necessita de muitas informações e consome um certo processamento para gerar o arquivo.

  Portanto, o desafio será a construção de uma API que permita a consulta de todas as transações de uma determinada conta, depois ter um outro serviço que retorne um PDF simples contendo uma tabela com as transações de uma determinada conta.

  Segue no detalhe todas as características para o desafio...
  
  #### Premissas

  - Crie uma API REST Full em golang com todos os CRUDS com o context path(/conductor/v1/api) e as seguintes tabelas: 
  
  ```
    Table Account{
      id int [pk, increment]
      status varchar
      created_at datetime
      updated_at datetime
      deleted_at datetime
    }

    Table Transactions{
      id int [pk, increment]
      valor numeric
      id_card int
      created_at datetime
      updated_at datetime
      deleted_at datetime  
    }


    Table Cards{
      id int [pk, increment]
      amount numeric
      id_account int
      created_at datetime
      updated_at datetime
      deleted_at datetime  
    }

    Ref: Cards.id_account > Account.id
    Ref: Transactions.id_card > Cards.id      
  ```
  
  ![diagrama](https://github.com/devconductor/desafio-golang/raw/master/img/diagrama.png)
    
  - Todos os end-points deverão ser documentados com Swagger/Open API.
  - Utilizar o banco de dados H2 ou SQLite para persistência dos dados em memória, assim facilitará a execução dos projetos durante as correções.
  - Ao subir o projeto, preencher o banco com algum dado fake para testes.
  - Criar path GET /contas/{id}/transacoes.pdf que irá retonar todas as transações dessa conta em um documento no formato PDF contendo uma tabela simples com os seguintes dados:
  
   | CONTA | TRANSAÇÃO | VALOR |
   |-|-|-|
   |3b1b1c0c-5c68-4352-b937-e3c68b6b1b16|Apple Store|199,50|
   |c203b91a-91a4-41d2-8583-86401c0fb1e4|Netflix|27,50|
  
  - O que será diferencial:

    ```
    * GRpc;
    * Criação de Dockerfile;
    * Testes Unitários;
    * C.I com Circle CI ou Github Actions;
    * Serviço ser multi tenancy;
    * Layout e design para o PDF gerado;
    ```
    
  - O que vamos avaliar:

    ```
    * Seu código; 
    * Arquitetura e camadas da sua aplicação;
    * Documentação do projeto e seu README.md
    * Organização do código;
    * Boas práticas;
    ```

### Instruções

   1. Faça um fork deste repositório, torne ele privado, desenvolva a sua solução e comit dentro desse seu repositório.
   2. Desenvolva. Você terá até 7 (sete) dias a partir da data do envio do desafio; 
   3. Após concluir o desenvolvimento faça um push e adicione o usuário @devconductor ao seu repositório para que possamos ter permissão ao código.
   4. Para que possamos testar sua solução, faço o deploy do seu projeto para alguma conta no http://heroku.com
   5. Informe a URL externa do seu projeto no heroku.
   6. Informe a URL externa de acesso ao swagger.
   5. Responda ao e-mail enviado do desafio, adicionando cópia para: cc2e73ef.Conductor.onmicrosoft.com@amer.teams.ms notificando a finalização do desafio para validação.


Boa Sorte!!!!
