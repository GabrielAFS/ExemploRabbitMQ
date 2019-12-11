# ExemploRabbitMQ

Como gerar jar usando maven:

mvn clean compile assembly:single

<hr/>

## Modelos de Comunicação

### Request/Response
- Protocolos: HTTP, FTP, SMTP, ...
- Um processo solicita algo (request) e
outro responde (response).

### Publish/Subscribe
- Protocolos: MQTT, AMQP.
- Um Broker fica responsável por enviar as mensagens
recebidas dos processos que publicam (Publish) para os 
processos que estão inscritos nele (Subscribe).

### Filas de Mensagens
- São as estruturas que encontram-se dentro dos Brokers,
em que os processos **publicam suas mensagens** e se **inscrevem**.
- Protocolo AMQP: 
>> Composto por um Broker que contém filas (FIFOs) de mensagens, 
>> **Exchanges que são vinculados as filas de mensagens**.
>> Tanto as filas como os Exchanges são criados pelos processos.
>> Por padrão, um Exchange já existe inicialmente, denominado por
>> Default, que é vinculado a todas as filas. Porém, as mensagens
>> não propagadas para todas as filas, um **parâmetro extra** deve ser
>> enviado para ele indicando em qual fila a mensagem deve ser
>> publicada.