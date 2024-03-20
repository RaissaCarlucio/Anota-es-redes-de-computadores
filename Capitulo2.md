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

Aplicação de rede: Web (cliente-servidor, que permite aos usuarios obter documentos de servidores por demanda).
Protocolo de camada de aplicação: HTTP (define o formato e a sequência das mensagens que são passadas entre o navegador e o servidor).

**HTTP**: HyperText Transfer Protocol - protocolo da camada de aplicação da web. É executado em sistemas finais diferentes e em dois programas: um cliente e outro servidor. Coonversam entre si por meiio de troca de mensagens. Ele define como os clientes requisitam páginas aos servidores e como eles as transferem aos clientes. Ele usa o TCP como seu protocolo de transporte subjacente. O cliente HTTP primeiro inicia uma conexão TCP com o servidor. Uma vez estabelecida, os processos di navegador e do servidor acessa o TCP por meio de suas interfaces de socket. **Prtocolo sem estado**( não mantem informação alguma sobre clientes ).

*Página da web*: (documento), é constituida de objetos, e ela tem um URL que tem 2 componentes: o nome do hospedeiro(hostname) do servidor que abriga o objeto e o nome do caminho do objeto.

*Conexoes nao persistentes*: Cada conexao TCP é encerrada apos o servidor enviar o objeto. Desvantagens: uma nova conexao deve ser estabelecida e mantida para cada objeto solicitado; Para cada coexao, devem ser alocados buffers TCP e conservadas variaveis TCP, sobrecarregando o servidor Web.
* Tempo de viagem de ida e volta*: Tempo que leva para um pequeno pacote viajar do cliente ao servidor e de volta ao cliente (sao 2 RTTs(um para estabelecer a conexao ao TCP e outro para solicitar e receber um objeto) mais o tempo de transmissao do arquivo HTML no servidor).

*Conexoes persistentes*: o servidor deixa a conexao TCP aberta apos enviar resposta.

Metodo GET: usado quando o navegador requisita um objeto.
Metodo POST: usado quando o usuario preenche um formulario.
Metodo HEAD: quando um servidor recebe uma requisicao com o metodo HEAD, responde com uma mensagem HTTP, mas deixa de fora o objeto requisitado.
Metodo PUT: usado junto com ferramentas de edicao da Web e por aplicacoes que precisam carregar objetos para servidores Web.


200 OK: requisicao bem sucedida.
301 Moved Permanetly: Objeto requisitado foi removido em definitivo.
400 Bad Request: O codigo generico de erro que indica que a requisicao nao pode ser entendida pelo servidor.
404 Not Found: O documento requisitado nao existe no servidor.
505 HTTP Version Not Supported: a versao do protocolo HTTP requisitada nao é suportada pelo servidor.

*Cookies*: permitem que sites monitorem seus usuarios. Normalmente o site usa um banco de dados de apoio. O usuario tem um numero de identificacap proprio (Set cookie).

*Cache Web*: tambem denominado: servidor proxy, tem seu proprio disco de armazenagem e mantem, dentro dele, copias de objetos recentemente requisitados. O cache é um servidor e um cliente. Ele é utlizado para: diminuir o tempo de resposta para a requisicao de um cliente em um site ja acessado 1 vez; podem diminuir o trafego no enlance de acesso de uma instituicao qualquer à Internet. Problema: a copia de um objeto existente no cache pode estar desatualizada, mas existe o **GET condicional** que verifica se os objetos estao atualizados. "If-Modified-Since"


--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------


A












