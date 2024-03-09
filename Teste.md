# Capitulo 1, aula 1:

**Perguntas:**
**R1** - Qual é a diferença entre um hospedeiro e um sistema final? Cite os tipos de sistemas finais. Um servidor Web é um sistema final?

R: Um hospedeiro é um dispositivo físico ou virtual que executa aplicativos ou processos. Ex: computador. Um sistema final são dispositivos conectados a internet. Ex: smarphones, computadores pessoais, etc. Um servidor pode sim ser considerado um sistema final, deis que esteja conectado a internet e usado pelo usuário para realizar tarefas específicas.

**R4** -  Cite seis tecnologias de acesso. Classifique cada uma delas nas categorias acesso residencial, acesso corporativo ou acesso móvel.

R:  *Cabo Coaxial:* É constituido de dois condutores de cobre, como o par trançado. Categoria: Acesso Residencial, Acesso Corporativo, Acesso Móvel (em algumas aplicações).

*Fibra óptica:* É um meio delgado e lexível que conduz pulsos de luz, cada um deles representando um bit. Categoria: Acesso Residencial, Acesso Corporativo e Acesso Móvel.

*Canais de rádio terrestre:* Sua instalação pode atravessar paredes e não requer cabos físicos. Categoria: Acesso Residencial

*Canais de rádio por satélite:* Dois tipos de satélites são usados para comunicações: Satélites geoestacionários e de órbita baixa. Categoria: Acesso residencial ou móvel.

*Wi-Fi (Wireless Fidelity):* Permite a conexão sem fio a redes locais. Categoria: Acesso Residencial, Acesso Corporativo e Acesso Móvel

*DSL (Digital Subscriber Line):* Oferece conectividade de banda larga usando linhas telefônicas existentes. Categoria: Acesso Residencial e Acesso Corporativo

**R7** - Qual a taxa de transmimssão de LAN's Ethernet? 

R: As redes Ethernet podem operar em diferentes velocidades de transmissão, e a taxa específica de transmissão pode depender da versão e do tipo de tecnologia Ethernet utilizada

**R16**: -  Considere o envio de um pacote de uma máquina de origem a uma de destino por uma rota fixa. Relacione os componentes do atraso que formam o atraso fim a fim. Quais deles são constantes e quais são variáveis?

R: Atraso de processamento(constante), atraso de fila(variavel), atraso de transmissão(constante), atraso de propagação(constante).

**R18*: - Quanto tempo um pacote de 1.000 bytes leva para se propagar através de um enlace de 2.500 km de distância, com uma velocidade de propagação de 2,5 - 108 m/s e uma taxa de transmissão de 2 Mbits/s? Em geral, quanto tempo um pacote de comprimento L leva para se propagar através de um enlace de distância d, velocidade de propagação s, e taxa de transmissão de R bits/s? Esse atraso depende do comprimento do pacote? Depende da taxa de transmissão?

R: 8000/2*10^6 + 2.500.10^3/108 = 0,023*10^9

Sim, o atraso depende do comprimento do pacote e a taxa de tranmissão.

L/R + D/V 

L = tamanho do pacote em bits

R = taxa de transmissão(vazão escolher a menor)

D = distância

V = velocidade de propagação do sinal

**R19** - Suponha que o hospedeiro A queira enviar um arquivo grande para o hospedeiro B. O percurso de A para B possui três enlaces, de taxas R, = 500 kbits/s, R, = 2 Mbits/s, e R, = 1 Mbit/s.

a. Considerando que não haja nenhum outro tráfego na rede, qual é a vazão para a transferência de arquivo?
R-  A- A vazão é de 500 kbit/s

b. Suponha que o arquivo tenha 4 milhões de bytes. Dividindo o tamanho do arquivo pela vazão, quanto tempo levará a transferência para o hospedeiro B?
R - 32*10^6/500*10^3 = 64 segundos

c. Repita os itens “a” e “b”, mas agora com R, reduzido a 100 kbits/s.
R - A vazão agora é de 100kbits
32*10^6/100*10^3 = 320 segundos.










