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

**Perguntas**:

**R1** - Relacione cinco aplicações da Internet não proprietárias e os protocolos de camada de aplicação que elas usam

R: Aplicacao1: Navegador WEB
Protocolo1: HTTP;

Aplicacao2: Email
Protocolo2: SMTP

Aplicacao3: Transferencia de arquivo
Protocolo3: FTP

Aplicacao4: Correio eletronico
Protocolo4: SMTP

Aplicacao5: Multimidia em fluxo continuo
Protocolo5: HTTP

**R12** - Considere um site de comércio eletrônico que quer manter um registro de compras para cada um de seus clientes. Descreva como isso pode ser feito com cookies.

R: O site pode ter dentro dele um banco de dados. Toda vez que um cliente entrar no site, vai se criar um Set Cookie, que é um numero de acesso para aquele usuario, que vai ser usado para monitorar o que o cliente esta procurando e comprando. Tudo isso vai sendo guardado no banco de dados, facilitando a maneira de monitorar o usuario e oferecer produtos parecidos ao de sua busca pelo site.

**R13** - Descreva como o cache Web pode reduzir o atraso na recepção de um objeto requisitado. O cache Web reduzirá o atraso para todos os objetos requisitados por um usuário ou somente para alguns objetos? Por quê?

R: O cache web pode ajudar a reduzir o atraso de um objeto requisitado pois ele possui seu proprio disco de armazenamento, e mantem, dentro dele, copias de objetos recentemente requisitados. Ou seja, se o cliente acessar o site mais de uma vez, a copia daquele objeto sera emitido para o mesmo. 
O cache web reduzirá o atraso para alguns objetos requisitados por um usuário, mas não necessariamente para todos. Isso ocorre porque o cache web armazena cópias de recursos da web, como imagens, arquivos de estilo, scripts e páginas da web, temporariamente em um servidor mais próximo do usuário. Quando o usuário solicita um recurso, o servidor verifica se uma cópia desse recurso está presente no cache. Se estiver, o servidor entrega o recurso diretamente do cache em vez de buscar no servidor original, reduzindo assim o tempo de resposta. No entanto, o cache web não pode armazenar todos os recursos da web. Alguns recursos podem ser dinâmicos ou exclusivos para cada usuário, como páginas da web personalizadas, conteúdo gerado dinamicamente ou recursos que não são configurados para serem armazenados em cache. Portanto, enquanto o cache web pode reduzir significativamente o atraso para recursos que são armazenáveis em cache e frequentemente acessados, não pode eliminar completamente o atraso para todos os recursos, especialmente aqueles que são dinâmicos ou únicos para cada solicitação de usuário.

**P1** - Falso ou verdadeiro?
a. Um usuário requisita uma página Web que consiste em algum texto e três imagens. Para essa página, o cliente enviará uma mensagem de requisição e receberá quatro mensagens de resposta.

b. Duas páginas Web distintas (por exemplo, www.mit.edu/research.html e www.mit.edu/ students .htm1l) podem ser enviadas pela mesma conexão persistente.

c. Com conexões não persistentes entre navegador e servidor de origem, é possível que um único segmento TCP transporte duas mensagens distintas de requisição HTTP.

d. O cabeçalho Date: na mensagem de resposta HTTP indica a última vez que o objeto da resposta foi modificado.

A - Verdadeiro

B - Verdadeiro

C - Falso: Em uma conexão não persistente, a conexão TCP é fechada após cada transação ou após o término da comunicação entre o cliente e o servidor. Isso significa que, uma vez que uma requisição HTTP é enviada e a resposta é recebida, a conexão TCP é encerrada.

D - Falso - O cabeçalho Date na mensagem de resposta HTTP indica a data e hora em que a mensagem de resposta foi gerada pelo servidor, não a última vez que o objeto da resposta foi modificado.

**P4** Considere a seguinte cadeia de caracteres ASCII capturada pelo Wireshark quando o navegador enviou uma mensagem HTTP GFT (ou seja, o conteúdo real de uma mensagem HTTP GET). Os caracteres <cr><lf> são retorno de carro e avanço de linha (ou seja, a cadeia de caracteres em itálico <cr> no texto abaixo representa o caractere único retorno de carro que estava contido, naquele momento, no cabeçalho HTTP). Responda às seguintes questões, indicando onde está a resposta na mensagem HTTP GET a seguir.

GET /cs453/index.html HTTP/1.1<cr><lf>
Host: gai a.cs.umass.edu<cr><lf>
User-Agent: Mozilla/5.0 ( Windows;U; Windows NT 5.1; en-US; rv:1.7.2) Gec ko/20040804 Netscape/7.2 (ax) <cr><lf>
Accept:ext/xml, application/xml, application/xhtml+xml, text /html;q=0.9, text/plain;q=0.8,image/png,*/*;q=0.5 <cr><1f>
Accept-Language: en-us,en;q=0.5<cr><1f>
Accept-— Encoding: zip,deflate<cr><lf>
Accept-Charset: ISO -8859-1,utf-8;q=0.7,*;q=0.7<cr><lf>
Keep-Alive: 300<cr> <1f>
Connection: keep-alive<cr><1lf><cr><lf>

a. Qual é a URL do documento requisitado pelo navegador?

index.html

b. Qual versão do HTTP o navegador está rodando?

1.1

c. O navegador requisita uma conexão não persistente ou persistente?

Conexao persistente por causa do: Connection: keep-alive<cr><1lf><cr><lf>

d. Qual é o endereço IP do hospedeiro no qual o navegador está rodando?

?

e. Que tipo de navegador inicia essa mensagem? Por que é necessário o tipo de navegador em uma mensagem de requisição HTTP?

User-Agent: Mozilla/5.0; Compatibilidade:, Recursos específicos do navegador, Debugging e suporte, etc.












