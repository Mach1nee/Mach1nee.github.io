---
title: "Spoofing em Navios SDR"
date: 2024-12-22 11:12:00 -0300
categories: [Guia]
tags: [SDR, Spoofing]
---

![imagem](https://github.com/Mach1nee/Mach1nee.github.io/blob/main/imagens/Logic-of-jamming-and-spoofing-attacks-against-vessels.png)

# Spoofing em Navios SDR

esse é um Guia de como criei um Spoofing de Navios SDR
para contextualizar explicarei toda a lógica e teoria sobre o Spoofing em Navios SDR

# SDR teoria
* SDR Software Defined Radio (software definido por rádio)
é uma tecnologia de rádio que utiliza software para processar sinais de rádio,
em vez de depender apenas de hardware específico. Em resumo, o SDR transforma a forma
como os sistemas de rádio são projetados e operados, oferecendo maior versatilidade e eficiência.

* SDR Hacking
  Pode-se localizar e rastrear Iates, Aviões, Carros qualquer coisa 
  que 
  esteja emitindo sinal de rádio.
  é assim que iates são rastreados. Existem duas maneiras para os 
  grandes iates, eles comunicam sua localização via GPS. os grandes 
  iates e navios e também um AIS, O AIS é um sistema de transmissão de 
  rádio que opera em frequências VHF (161.975 MHz e 162.025 MHz) e é 
  usado para ajudar na navegação marítma. Ele permite que navios 
  transmitam informações como:
* Identificação (nome do navio, número IMO, etc.);
* Localização (coordenadas GPS);
* Velocidade e direção;
* Status (ancorado, navegando, etc.).

Essas informações são transmitidas continuamente e podem ser recebidas por outros navios, estações terrestres e até satélites. O AIS é essencial para evitar colisões, melhorar a segurança marítima e rastrear o tráfego naval global. 

# como funciona o Spoofing do AIS
* O AIS opera em frequências de rádio conhecidas o VHF e essas
  transmissões não são criptografadas.
* As mensagens AIS seguem o protocolo NMEA0183, que é padronizado e bem 
  documentado, permitindo que alguém com conhecimento técnico crie 
  pacotes falsos.
* Com um transmissor SDR ou outro hardware apropriado, é possível 
  transmittir sinais falsos que imitam mensagens AIS legítimas.

# Exemplos de manipulação de spoofing no AIS
* Criar navios fantasmas:
  Transmitir sinais indicando a presença de navios inexistentes em 
  determinadas coordenadas. Isso pode confundir radares e sistemas de 
  monitoramento.
* Alterar a localização de navios reais:
  Substituir as coordenadas reais de um navio por outras, fazendo 
  parecer que ele está em um local diferente.
* Interromper o tráfego marítimo:
  Enviar sinais falsos que indicam colisões iminentes ou situações de 
  perigo, causando confusão entre os operadores.
* Ocultar navios reais:
  Sobrescrever mensagens AIS legítimas com outras que indiquem que o 
  navio está em um estado inativo (como ancorado), quando na verdade 
  ele está em movimento.
* Sabotagem ou atividades ilícitas:
  Grupos que estão envolvidos em atividades ilegais, como contrabando   
  ou pesca ilegal, podem usar spoofing para disfarçar a localização de 
  seus navios.

# Exemplos Reais que já aconteceram e acontecem com o spoofing no AIS
* Navios fantasmas no Mar Negro (2017):
  Navios relataram coordenadas falsas, colocando-os no interior de 
  aeroportos ou em locais impossíveis. Isso foi atribuído a ataques de 
  spoofing coordenados.
* Disfarce de atividades ilícitas:
  Navios envolvidos em contrabando ou pesca ilegal frequentemente 
  desativam seus transponders AIS ou usam spoofing para evitar serem 
  rastreados por autoridades.

# Ferramentas necessários para o spoofing
para realizar o ataque de spoofing no AIS
* Um SDR (Software Defined Radio)
  Equipamentos como o HackRF, BladeRF, ou até mesmo o RTL-SDR (mais 
  barato) podem ser usados para transmitir e receber sinais VHF.
* Existem bibliotecas e ferramentas prontas que podem ser usadas para 
  gerar ou analisar mensagens AIS, como:
  GNU Radio: Um framework popular usado para processamento de sinais.
  AIS Dispatcher ou libais: Para decodificar e criar mensagens AIS.
* Transmissor de rádio VHF:
  Um transmissor capaz de operar nas frequências do AIS seria 
  necessário para transmitir os sinais falsos.

# prevenção de ataques de spoofing no AIS
Embora o AIS por si só não seja seguro (por sua falta de criptografia), algumas medidas podem ser adotadas para mitigar ataques:

* Monitoramento de anomalias:
  Usar sistemas de monitoramento que detectem mensagens AIS         
  inconsistentes (como navios "teletransportando-se" entre locais).
* Fusão com outros sensores:
  Integrar dados AIS com informações de radar ou câmeras para verificar 
  a presença física de navios.
* Criptografia e autenticação (futuro):
  Adicionar mecanismos de autenticação às mensagens AIS poderia 
  dificultar ataques de spoofing, mas isso exige mudanças no padrão 
  global.

  # código
  * aqui um código de exemplo de como seria o spoofing, o código pede pro usuário um nome pra dar spoofing
   
