Os protocolos de comunicação são os responsáveis pela operação do message broker e de como será o envio/recebimento de mensagens entre os clientes do broker. O RabbitMQ possui suporte a vários protocolos,
AMQP: Advanced Messaging Queue Protocol,
 é o protocolo base no qual foi construído o RabbitMQ. Esse protocolo possui inúmeras vantagens, como enfileiramento confiável de mensagens, roteamento flexível, transações, segurança e interoperabilidade.

 Nesse modelo de protocolo, temos algumas partes envolvidas. A primeira delas é o publisher, que vai publicar mensagens para uma outra entidade denominada exchange. Essa exchange, de acordo com regras programáveis (tipo da exchange e os bindings), vai encaminhar essas mensagens para as filas, que por sua vez vão estar sendo consumidas por algum subscriber, que "assinou" para receber dados dessa fila.

 Uma das características desse protocolo é justamente o fato de que um publisher nunca publica mensagens diretamente na fila. A mensagem sempre é encaminhada à exchange que, de acordo com seu tipo, irá encaminhar para uma determinada fila ou a descartar.


MQTT:
  Message Queue Telemetry Transport é um protocolo para troca de mensagens em ambientes onde se tem alguma restrição de hardware, como pouca memória disponível, por exemplo, ou uma limitação de banda. Teve um crescimento notável pela adoção em dispositivos móveis. O objetivo desse protocolo é ser mais simples que o AMQP, utilizado em cenários de mensagens simples e diretas. É ideal para IoT (Internet das Coisas).