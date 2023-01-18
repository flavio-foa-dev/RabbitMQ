Os protocolos de comunicação são os responsáveis pela operação do message broker e de como será o envio/recebimento de mensagens entre os clientes do broker. O RabbitMQ possui suporte a vários protocolos,
AMQP: Advanced Messaging Queue Protocol,
 é o protocolo base no qual foi construído o RabbitMQ. Esse protocolo possui inúmeras vantagens, como enfileiramento confiável de mensagens, roteamento flexível, transações, segurança e interoperabilidade.

 Nesse modelo de protocolo, temos algumas partes envolvidas. A primeira delas é o publisher, que vai publicar mensagens para uma outra entidade denominada exchange. Essa exchange, de acordo com regras programáveis (tipo da exchange e os bindings), vai encaminhar essas mensagens para as filas, que por sua vez vão estar sendo consumidas por algum subscriber, que "assinou" para receber dados dessa fila.

 Uma das características desse protocolo é justamente o fato de que um publisher nunca publica mensagens diretamente na fila. A mensagem sempre é encaminhada à exchange que, de acordo com seu tipo, irá encaminhar para uma determinada fila ou a descartar.


MQTT:
  Message Queue Telemetry Transport é um protocolo para troca de mensagens em ambientes onde se tem alguma restrição de hardware, como pouca memória disponível, por exemplo, ou uma limitação de banda. Teve um crescimento notável pela adoção em dispositivos móveis. O objetivo desse protocolo é ser mais simples que o AMQP, utilizado em cenários de mensagens simples e diretas. É ideal para IoT (Internet das Coisas).

  (AMQP default)	direct	D
  amq.direct	direct	D
  amq.fanout	fanout	D
  amq.headers	headers	D
  amq.match	  headers	D
  amq.rabbitmq.trace	topic	D I
  amq.topic	topic	D

  # latest RabbitMQ 3.10
docker run -it --rm --name rabbitmq -p 5672:5672 -p 15672:15672 rabbitmq:3.10-management

localhost:15672

padrao
Username: guest
Password: guest

docker-compose up
docker-compose down.


As limitações que podem ser causadas por requisições síncronas, visto que um serviço aguarda a resposta do outro;

O acoplamento que é gerado quando utilizamos requisições síncronas, pois é necessário referenciar diretamente o serviço com o qual se deseja comunicar;

Os benefícios e os problemas que podem ser solucionados com o uso de requisições assíncronas;

O que é o RabbitMQ e como ele atua na gestão do envio e recebimento de mensagens;

Os conceitos de queue (filas) e exchanges (trocas) que são utilizados na troca de mensagens;

Como executar o RabbitMQ em um container docker, bem como o acesso ao Dashboard, que é o painel de controle que demonstra inúmeras informações sobre queues, exchanges e propriedades que podem ser configuradas para as filas.