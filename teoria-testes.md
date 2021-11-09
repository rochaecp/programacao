- **Teste unitário**
    - Testa uma unidade menor do sistema isoladamente.
    - Esses testes garantem que os componentes individuais do aplicativo funcionem conforme o esperado. Instruções assert testam a API do componente.

- **Teste de caixa-branca**
    - É um dos tipos de teste funcional. Nesse tipo de teste se tem acesso ao código fonte e é orientado à lógica ou fluxo de dados no sistema.

- **Teste de caixa-preta**
    - Outro tipo de teste funcional, mas que ao contrário não se tem acesso ao código fonte. Voltado como uma visão externa em que se baseia nos requisitos funcionais para avaliar o software.

- **Teste de regressão**
    - Utilizado para verificar se trechos anteriores do código que funcionavam não passaram a apresentar erro na nova versão do código.

- **Teste de integração**
    - Diferente do teste unitário, esse teste serve para verificar se as funcionalidades funcionam em conjunto ou se possuem alguma incompatibilidade entre si.
    - Esses testes garantem que as interações de componente funcionem conforme o esperado em relação a artefatos externos, como bancos de dados. Instruções assert podem testar a API do componente, a interface do usuário ou os efeitos colaterais de ações, como E/S de banco de dados, registros em log etc.

- **Teste de instalação**
    - Verifica se é possível ser realizado a instalação do software sobre diferentes situações, como: espaço em memória, processos sendo executados simultaneamente, interrupções no sistema, etc...

- **Teste de carga e estresse**
    - Consiste em levar o software ao "extremo" situações de demanda elevada de requisições, alta fluxo de dados, assim por diante.

- **Teste de performance**
    - Atesta o desempenho do software em diversas situações.

- **Teste de usabilidade**
    - Teste realizado com um pequeno grupo de usuários para avaliar se o software atende as suas necessidades.

- **Teste de segurança**
    - Verifica a segurança do software contra possíveis situações como vírus e hackers que possam comprometer a segurança do software e dos dados que ele armazena.

**Testes de serviço** 
    - Esses testes garantem que os casos de uso de serviço de ponta a ponta, incluindo o teste de vários serviços ao mesmo tempo, sejam testados. Para esse tipo de teste, é necessário preparar o ambiente primeiro. Nesse caso, isso significa iniciar os serviços (por exemplo, usando o Docker Compose).

## Links

[blog onedaytesting](https://blog.onedaytesting.com.br/teste-de-software/)
[blog nibutiratec](https://www.monitoratec.com.br/blog/quais-os-tipos-de-testes-de-software-e-por-que-automatiza-los/)
[blog cronapp](https://blog.cronapp.io/tipos-de-teste-de-software/)


