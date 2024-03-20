# Anotações e exercicios capitulo 2

Aplicações que se tornaram populares nas décadas de 1970 e 1980: correio eletrônico, acesso a computadores remotos, transferência de arquivo, grupos de discussão, mensagem instantânea e compartilhamento de arquivos P2P. Em 2000: explosão de aplicações populares de voz e video: Skype.

Arquitetura da aplicação: é projetada pelo programador e deterina coo a aplicação é organizada nos vários sistemas finais. Programado deve aproveitar: arquitetura cliente-servidor (o servidor esta sempre funcionando e atende as requisições dos clientes). Uma das caracteristicas é que: os clientes não se comunicam diretamente uns com os outros.; O servidor tem endereço fixo (endereço IP). Muitas vezes o servidor pode não conseguir atender a requisição de todos os usuários, por isso se usa um **datacenter** (ele pode ter vários servidores). 

Aplicação de rede: consiste em pares de processos que nviam mensagens uns para os outros por meio de uma rede. Na Web, um navegador é um processo cliente eum servidor Web é um processo servidor. No compartilhamento de arquivos P2P, o par que envia o arquivo é o cliente e que recebe é o servidor. No compartilhamento de arquivos, um processo pode ser cliente e servidor (ambos).

**Cliente**: Aquele que inicia a comunicação. **Servidor**: O que espera ser contatado para iniciar a sessão.

*Socket(API)*: Um processo envia mensagens para a rede e recebe mensagens dela através de uma interface de software (Socket), Ex: Um processo é a casae o socket a porta. Quando um process quer enviar uma mensagem a outro processo em outro hospeideiro, ele empurra a mensagem pela porta. A aplicação do lado remetente envia mensagens por meio do socket. Do outro lado, o protocolo de camada de transporte tem a responsabilidade de levar mensagens pela rede até o socket d processo destinatário. 

Para enviar a correspondência postal a um determinado destino, este precisa de um endereço. Para identificar o processo receptor, duas informações devem ser especificadas: 1 - O Endereço do hospedeiro; 2- Um identificador que especifica o processo receptor no hospedeiro de destino. Hospedeiro = endereço IP. O processo de envio tbm precisa identificar o processo receptor( número de porta de destino ).

**Serviços que um protocolo da camada de transporte pode oferecer**:

**Transferência confiável de dados**; **Vazão**: taxa pela qual o processo remetente pode enviar bits ao processo destinatário; **Temporização** (Atraso menor por exemplo para um pensonagem fazer uma ação em um jogo); **Segurança**: dados protegidos.

**Protocolo TCP**: - Serviço orientado para conexão: O TCP faz o cliente e o servidor trocarem informações de contrle de camada de transporte antes que as mensagens de camada de aplicação comecem a fluir, os preparando para a enxuarrada de pacotes;

- Serviço confiavel de transporte: Quando aparece que um pacote não chegou, o TCP fica enviando o pacote que falta várias vezes novamete.

- Mecanismo de controle de congestionameto.

**Protocolo UDP**: Simplificado. Não possui serviço de controle de conexão e provê serviço não confiavel de transferecia de dados. Mensagens podem chegar tambem fora de odem.

 Aperfeiçoamento do TCP: SSL ( Secure Sockets Layer ): oferece serviços importantes de segurança.

Ex de usos para o TCP: Web, transferência de arquivos, multimídia em fluxo contínuo, etc.

**Protocolo de camada de apliação**: ele define:
  - Os tipos de mensagens trocadas;
  - A sintaxe dosvários tipos de mensagens
  - A semântica dos campos
  - Regras para determinar quando e como um processo envia e responde mensagens.

Protocolos especificados RFC são públicos (Web, HTTP, etc).









