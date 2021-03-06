# Teorias e conceitos sobre Programação

- **API - Application Programming Interface** 
    - "Interface de Programação de Aplicações"
    - É um conjunto de rotinas e padrões estabelecidos por um software para a utilização das suas funcionalidades por outros aplicativos.
    - O conceito de API nada mais é do que uma forma de comunicação entre sistemas. 
    - Permite a integração entre dois sistemas em que um deles fornece informações e serviços que podem ser utilizados pelo outro, sem a necessidade de o sistema que consome a API conhecer detalhes de implementação do software.
- **API REST ou API RESTful** 
    - É uma API que está em conformidade com as restrições do estilo de arquitetura REST.
    - Para que uma API seja considerada do tipo RESTful, ela precisa está em conformidade com os seguintes critérios:
    - Ter uma arquitetura cliente/servidor formada por clientes, servidores e recursos, com solicitações gerenciadas por meio de HTTP.
    - Estabelecer uma comunicação **stateless** entre cliente e servidor. Isso significa que nenhuma informação do cliente é armazenada entre solicitações GET e toda as solicitações são separadas e desconectadas.
    - Armazenar dados em cache para otimizar as interações entre cliente e servidor.
    - Ter uma interface uniforme entre os componentes para que as informações sejam transferidas em um formato padronizado.
    - Ter um sistema em camadas que organiza os tipos de servidores (responsáveis pela segurança, pelo carregamento de carga e assim por diante) envolvidos na recuperação das informações solicitadas em hierarquias que o cliente não pode ver.
    - Link: <https://www.redhat.com/pt-br/topics/api/what-is-a-rest-api>    
    - *REST - Representational State Transfer*
        - "Transferência Representacional de Estado"
        - É um modelo de arquitetura que fornece diretrizes para que os sistemas distribuídos se comuniquem diretamente usando os princípios e protocolos existentes da Web sem a necessidade de SOAP ou outro protocolo sofisticado. 
        - Contém um princípio STATELESSNESS (sem estado)
        - Quando uma solicitação REST é realizada, o servidor envia uma representação dos estados que foram requeridos
        - O REST precisa que um cliente faça uma requisição para o servidor para enviar ou modificar dados.
        - Um requisição consiste em:
        - Um verbo ou método HTTP, que define que tipo de operação o servidor vai realizar;
        - Um header, com o cabeçalho da requisição que passa informações sobre a requisição;
        - Um path (caminho ou rota) para o servidor
        - Informação no corpo da requisição, sendo esta informação opcional.
        - Cada resposta que a aplicação REST retorna, é enviado um código definindo o status da requisição
        - 200 (OK)
        - 201 (CREATED)
        - 204 (NO CONTENT), etc ...
        - Link: <https://developer.mozilla.org/pt-BR/docs/Web/HTTP/Status>
        - Links: 
        - <https://www.alura.com.br/artigos/rest-conceito-e-fundamentos?gclid=Cj0KCQjwvO2IBhCzARIsALw3ASoqXXY10PI0EnjUjoPZhZ1D9RkWPuk6TafisDoc3LC4jIQWN_i83XEaAp7mEALw_wcB>
        - Muito bom: <http://www.macoratti.net/16/05/net_rest1.htm>
- **Classe POCO**
    - Plain Old CLR Object 
    - classe terá apenas propriedades para descrever suas informações básicas que no nosso exemplo serão: o Id , o nome e uma lista de produtos.
- **CRUD**
    - Create, Read, Update, Delete registros
    - Cadastro básico com opções de leitura, listagem, criação, atualização e remoção de registros 
    - <https://en.wikipedia.org/wiki/Create,_read,_update_and_delete>   
- **Endpoint de uma API**
    - é a URL onde seu serviço pode ser acessado por uma aplicação cliente.        
- **Métodos HTTP**
    - método GET é o método mais comum, geralmente é usado para solicitar que um servidor envie um recurso;
    - método POST foi projetado para enviar dados de entrada para o servidor
    - método PUT edita e atualiza documentos em um servidor
    - método DELETE que como o próprio nome já diz, deleta certo dado ou coleção do servidor.
    - Link <https://developer.mozilla.org/pt-BR/docs/Web/HTTP/Methods>
- **Mock Objects**
    - criamos o mock para imitar o comportamento de uma classe
    - mocar objetos ou Mock Objects significa objetos que imitam objetos reais para realização de testes de software.
    - <http://www.macoratti.net/15/08/net_mock1.htm>
    - <https://www.devmedia.com.br/mocks-introducao-a-automatizacao-de-testes-com-mock-object/30641>
    - <https://pt.wikipedia.org/wiki/Objeto_mock>    
- **Padrão MVC - Model-View-Controller**
    - É um padrão de arquitetura que divide a aplicação em 3 camadas: 
    - Camadas:
    - **Controller** (controlador): 
        - Recebe todas requisições, controla qual model usar e qual view será mostrada ao usuário
        - A interface se comunica com o controlador que se comunica com as regras de negócio.
    - **Model** (modelo): 
        - parte lógica da aplicação, que gerencia o comportamento dos dados através de regras de negócios, lógica e funções.
        - é a ponte entre as camadas Visão (View) e Controle (Controller)
        - leitura, validação e escrita de dados
    - **View** (visão): 
        - interações com usuário, exibe dados: HTML, XML
    - Pode ser aplicado em projetos desktop, web e mobile.
    - Isola as regras de negócio da interface com o usuário.
    - Links:
    - <https://pt.wikipedia.org/wiki/MVC#Camada_de_modelo_ou_da_l%C3%B3gica_da_aplica%C3%A7%C3%A3o_(Model)>
- **Protocolo Simples de Acesso a Objetos (SOAP)**
    - aaaaa
- **Scaffold de um controlador**
    - aaaa
- **Swagger**
    - Auxiliar o desenvolvedor de API
- **Uniform Resource Identifier (URI)**
    - aaaa


