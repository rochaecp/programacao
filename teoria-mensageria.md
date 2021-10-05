# Mensageria (Messaging)

## Interação entre sistemas - modelos:

- **Time-Driven**  
	- Tarefas agendadas/periódicas

- **Request-Reply** (requisição-resposta) - mais comum  
	- Uma entidade quer consumir um recurso e um servidor provê esse recurso.
	- As duas entidades precisam estar no ar.
	- É preciso conhecer o endereço da entidade provedora

- **Message-Driven** (modelo assíncrono)  
	- Send-and-forget: não tem resposta
	- Comunicação é assíncrona
	- Mensagens
	- Estruturas de dados / entidades básicas: filas, tópicos
	- broker de mensagens: coordena a estrutura

## Alguns tópicos

- **O que é uma mensagem?**
	- São estruturas com informações trocadas entre sistemas.
	- Podem ser solicitações, respostas, mensagens de erro ou apenas informações.
	- Podem representar algo a ser feito ou um evento que ocorreu (ex. ocorreu um erro, compra efetuada etc).
	- Devem ser pequenas, mínimo de informações possíveis.
	- Possui um header
	- Possui um payload (corpo): JSON (objetos), ou string ou bytes

- **O que é comunicação síncrona?**
	- Ex.: Temos a aplicação A fazendo uma chamada/requisição para a apliação B, e a aplicação A fica aguardando a resposta da aplicação B.
	- O processamento da aplicação A fica interrompido até a aplicação B dar a resposta.

- **O que é comunicação assíncrona?**
	- Ex.: Temos a aplicação A fazendo uma chamada/requisição para a apliação B, e a aplicação A continua o seu processamento sem a necessidade de aguardar o retorno da aplicação B.

- **Quando usar mensageria?**
	- Quando precisamos de uma comunicação assíncrona
	- Quando houver a necessidade de desacomplamento entre as aplicações
	- Quando se deseja obter escalabilidade: A aplicação começa a receber muitas requisições entao escalamos ela criando novas instancias dela para processar mais mensagens obtendo maior vasão.
	- Quando necessitamos de resiliência: processo de reprocessamento da ferramenta de mensageria caso de problemas de processamento na aplicação que remove da fila, a mensagem pode voltar para fila e ser reprocessada.
	- Quando desejamos processar arquivo muito grande em background
	- Em aplicações distribuídas

- **O que é message broker?**
	- Broker: intermediáro, que faz meio de campo
	- Faz o meio de campo entre a pessoa que está publicando a mensagem e a pessoa que vai consumir ela
	- É um servidor de mensagens, responsável por garantir que a mensagem seja enfileirada e armazenada em disco (opicional), garantindo que ela fique lá enquanto necessário até que algum consumidor a retire de lá.
	- Possui funcionalidades de enfileiramento, roteamento, padrões.
	- Algumas ferramentas existentes no mercado:
		- RabbitMQ, Apache Kafka, Google Cloud pub/sub, Amazon SQS, Azure Service Bus, Redis, ActiveMQ, IBM MQ

## Mensageria  - "Envie e Esqueça"

- Mensageria é um serviço utilizado para intermediar a troca de mensagens entre sistemas, integrando serviços.
- Você envia a mensagem e não fica esperando a resposta mas sabe que o destino recebeu a mensagem.

- Middleware: pedaço de software responsável por uma integração entre 2 sistemas
	- Middleware orientado a mensagem (MOM): Message broker
	- É desacoplado e assíncrono
	- Política de reply

- Existem 2 modelos diferentes de troca de mensagem:
	- O modelo que envia para uma fila
	- O modelo que envia para um tópico

- A aplicação A recebe a requisição e repassa a mesma para uma fila de mensagens e uma aplicação B lê dessa fila, processa em background e pode acessar a um BD.
- A fila de mensagens fornece um armazenamento temporário enquanto o programa de destino estiver ocupado ou não conectado.
- Basicamente a estrutura é:
	- Producer -> Queue (Message Broker) <- Consumer

- Temos o produtor (cliente por ex) que quer enviar uma mensagem.  
- Há um canal para enviar a mensagem, tem uma fila.   
- Temos o consumidor, que consome uma única mensagem da fila. Dois consumidores não podem consumir uma mesma mensagem da fila.  
- Temos um outro tipo de canal, um tópico que não retém a mensagem, mas encaminha para varios consumidores.  
- Quem coordena isso é o Broker de Mensagens, ex RabbitMQ  

**Tópico**
one-to-many, broadcast, pub-sub, publish-subscribe  
publisher é o produtor, publica mensagens  
temos múltiplos subscribers, todos recebem a mesma mensagem  

## RabbitMQ

- É uma aplicação Open Source de mensageria que atua como Message Broker.  
- É desenvolvido em Elang
- Atua como intermediário na gestão de envio e recebimento de mensagens de uma ou mais aplicações.  
- Lida com o tráfego de mensagens da maneira mais rápida e confiável possível.   
- Temos o conceito de consumidores competitivos (só um dos consumer recebe a mensagem)
- Foi desenvolvido para suportar o tráfego de mensagens através do protocolo **AMQP** (para msgs assíncronas).  
- Possui interface de gerenciamento
- Possui roteamento flexível: podemos configurar o exchange para rotear por troca direta, por tópicos, etc

- Utiliza um padrão publish-subscribe (pub-sub) que consiste em:  
	- O produtor publica (publish) a mensagem e envia para a fila.
	- O consumidor assina (subscribe) para receber aquele tipo de mensagem.

- Uma mensagem é dividida em 2 partes:
	1. **label**: rótulo da mensagem
		- O RabbitMQ usa o label para conectar o produtor com o consumidor da mensagem.
	2. **payload**: conteúdo da mensagem
		- Suporta diversos tipos de mídia, streams, arrays

- No ambiente RabbitMQ o produtor não envia mensagem diretamente para a fila.  
- A mensagem é enviada para a **Exchange**, que direciona a mensagem para a fila correta.
- Você faz o binding de uma fila na exchange
- Podemos ter diversas filas simultaneas no RabbitMQ.
- Após a mensagem ser concumida pelo consumidor ela é totalmente perdida.

- Alguns elementos importantes:
	- **Binding**: responsável pela ligação entre a Exchange e a fila.
	- **Binding Key**: chave do binding, é um id para a ligação
	- **Routing Key**: chave enviada junto com a mensagem. É utilizada pela Exchange para decidir para qual fila a mensagem será enviada

- Tipos de Exchange:
	1. **Direct Exchange**: exchange manda mensagem diretamente para uma determinada fila
		- usa routing key
	2. **Topic Exchange**: poe regras na exchange para encaminhar para a fila de acordo com a routing key
		- usa routing key + expressão regular
	3. **Fanout Exchange**: exchange manda msg para todas filas relacionadas com esta esta exchange
	4. **Headers Exchange**: no header da mensagem determinamos para qual fila a exchange deve direcionar a msg

Há uma imagem no Dockerhub para RabbitMQ.

- Propriedades usadas ao declarar **Queues/filas**:
	- durable
	- auto-delete
	- expiry: tempo que fila pode ficar ociosa
	- message TTL: tempo de vida da mensagem
	- overflow: quando fila transborda
		- drop head (remove a última quando ocorre overflow)
		- reject publish (publicador não consegue publicar na fila quando ela está cheia)
	- exclusive: somente canal que criou pode acessar
	- max length ou bytes: tam max permitido

- Dead letter queues: mensagem que ficou muito tempo sem ser lida vai para uma exchange que é associada a uma fila de mensagens que não foram consumidas
- Lazy queues: mensagens armazenadas em disco quando consumidores demoram pois fluxo de mensagens é muito alto
  
## Apache Kafka

- É uma Plataforma de Mensageria e Streaming.  
- É um barramento de mensagens.
- Trabalha com múltiplos consumers.
- Foi desenvolvido pelo Linkedin em 2010.  
- É utilizado em arquiteturas Event-driven Architectures (arquiteturas orientadas a eventos).  
- Eventos: normalmente formados por chave, valor e timestamp.  

## Links

- [Exemplo Colab - Ricardo Lampert](https://colab.research.google.com/drive/1agvs4efXPZdohXcKjkJCXqXejqSV0HEs?usp=sharing)
- [Envie e Esqueça – Messaging 101 - Andre Pastore](https://www.youtube.com/watch?v=xqXYEL0SmyM)
- [Playlist youtube - Gabrel Faraday](https://www.youtube.com/playlist?list=PLqONbZa3fPe4Z6sg7RQGaHlYqUjsliKAH)
- [RabbitMQ: Uma visão geral](https://www.youtube.com/watch?v=FcF5iufd2P0)
- [Instalação do RabbitMQ com Docker](https://www.youtube.com/watch?v=VWjszh6h21o)

## Continua

- [Message Broker & .Net Core - Introdução ao RabbitMQ - 1,5h](https://www.youtube.com/watch?v=iEeJDAU-Sg0)
- [Filas e Mensageria com RabbitMQ - Daniel Archer - youtube - 35m](https://www.youtube.com/watch?v=RnIwwm00UPM)
- [Mensageria com RabbitMQ - youtube - canal do dotnet - 3h](https://www.youtube.com/watch?v=ksiw6sPjK8w)

