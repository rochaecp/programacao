# ASP.NET

- **.NET**
  - Framework criado pela microsoft voltado para o desenvolvimento web.
  - É diferente de .NET Framework que só funciona em windows - antigo.
  - Na versão 5 em diante chamamos de .NET. Em versões mais antigas chamamos .NET Core.

- **ASP.NET Core**
  - Estrutura da Web gratuita para a criação de sites e aplicativos Web.

- **API**
  - Application Programming Interface - Interface de Programação de Aplicação.
  - É um sistema backend que faz requisições.
  - Alumas requisições: post, get, put e delete (Um CRUD).
    - POST - efetuar cadastros
    - GET - selecionar dados
    - PUT - alterar registros
    - DELETE - remover registros
  - (post, get, put e delete) lembram os comandos sql (insert, select, update e delete).
  - A estrutura da API consiste em:
    - Um cliente que faz a requisição para a API.
    - A API acessa o banco de dados.
    - O banco de dados retorna para a API as informações solicitadas.
    - A API retorna para o cliente em formato JSON ou XML.

- **Entity Framework Core**
  - É um ORM (Object Relational Mapper).
  - O ORM abstrai a camada de banco de dados.
  - O Entity Framework faz as interações com o banco (selects, inserts, updates e deletes) de dados sem que se precise criar códigos SQL.
  - Obs.: o Entity Framework aceita que utilizemos comandos SQL também.

- **Estrutura do projeto**
  - *Controllers*
    - Responsáveis pelas rotas
  - *Startup.cs*
    - Possui um método ConfigureServices que pode efetuar a conexao com o banco de dados, especificar o uso da rota

- **NuGet**
  - Site: <https://www.nuget.org/>
  - É um gerenciador de pacotes.

- **Modelo**
  - Tem 2 funcionalidades:
    - Criar a tabela do banco de dados
    - Características do JSON

- **DataAnnotations**
  - Serve para especificar funcionalidades extra: 
    - Uso de chave primaria, algumas validações.

- **DataContext**
  - Classe responsável por trabalhar com comandos de banco de dados, Ex:
    - selecionar, alterar, cadastrar excluir.
  - Permite não utilizar comandos SQL

- **Migration**
  - Cria uma tabela no banco de dados utilizando como base um modelo. 
  - Doc Microsoft: <https://docs.microsoft.com/pt-br/ef/core/managing-schemas/migrations/?tabs=dotnet-core-cli>

- **Async**
  - Se utilizarmos a palavra reservada await a linha ficará travada e as próximas linhas só serão executadas após terminar a execução da linha await.

## Old

### Entity Framework

- É um ORM (Mapeamento Relacional de Objeto)
- Permite usar banco de dados com objetos .NET
- Linhas de utilização:
  - **Database First**: le banco de dados e carrega as classes que representarão as tabelas do banco
  - **Model First**: cria modelo com EDM designer para gerar a base de dados - Componentes: Entity e Association
  - **Code First**: criamos as classes (classes POCO) e deixamos o Entity Framework criar o banco de dados.

### Data Annotation

- Recurso para adicionar atributos e métodos em classes para alterar convenções e personalizar comportamentos.
- Principais Atributos:
  - Required:
  - RegularExpression: valida o campo por Regex
  - Display: nome a ser mostrado nas interfaces de usuário
  - StringLength: qtd máx de caract
  - MinLength: qtd min de caract
  - DisplayFormat: formato a ser exibido nas interfaces de usuario - datas
  - Range: faixa de dados aceita

### Migrations

- Recurso para atualizar de forma incremental o esquema do banco de dados para manter em sincronia com o modelo de classes do projeto preservando os dados existentes no banco de dados.
- Permite realizar o downgrade para retornar à versões anteriores do BD.
- Mantém histórico de alterações no banco de dados.

### ASP.NET MVC

### O padrão MVC

- É um padrão de arquitetura que divide a aplicação em 3 camadas: o modelo (**model**), a visão (**view**) e o controlador (**controller**).
- Pode ser aplicado em projetos desktop, web e mobile.
- Camadas:
  - Model: leitura, validação e escrita de dados
  - View: interações com usuário, exibe dados: HTML, XML
  - Controller: recebe todas requisições, controla qual model usar e qual view será mostrada ao usuário

### O ASP.NET MVC

- As requisições do navegador são enviadas para uma Ação da Controller tirando a necessidade de cada URL possuir um arquivo físico.

- **Routes**
  - Padrão de rota default para url: "{controller}/{action}/{id}"
  - defaults: controller=Home, action=Index, id=optional

- **Custom Routes**
  - URLs mais amigaveis ao usuario

- **Action Result** 
  - É o resultado de uma ação processada por uma controller, retorna a view que deverá ser exibida

- **HTTP Verbs**
  - São métodos do protocolo HTTP que informam ao servidor qual ação ele deverá executar:
    - GET: busca recurso
    - POST: cria recurso
    - PUT/PATCH: atualiza recurso
    - DELETE: remove recurso

- **Razor**
  - É uma view engine utilizada no ASP.NET MVC que simplifica o des. de aplic .NET
  - É baseado em C#
  - Visual Studio possui IntelliSense para razor - produtividade

- **Middlewares**
  - São componentes que são executadas em todas as solicitações na aplicação ASP.NET
  - Há vários em uma aplicação, nós definimos a ordem de execução

### Alguns conceitos gerais

- **API (Interface de Programação de Aplicações)**
  - Integrar sistemas mesmo que possuam linguagens diferentes.

- **REST**
  - Conjunto de princípios que quando aplicados de maneira correta ...
  - Uma aplicação capaz de aplicar tais princípios chama-se RESTful ...?

- **Swagger**
  - Auxiliar o desenvolvedor de API

- **CRUD**
  - Create, Read, Update, Delete registros
  - Cadastro básico com opções de leitura, listagem, criação, atualização e remoção de registros

## Links

- [Criando API - Youtube](https://www.youtube.com/playlist?list=PLWXw8Gu52TRKoaiSaZVIKOHaAoHMeuzu1)


continua em <https://www.youtube.com/watch?v=DRTips1T8KQ&list=PLWXw8Gu52TRKoaiSaZVIKOHaAoHMeuzu1&index=9>
