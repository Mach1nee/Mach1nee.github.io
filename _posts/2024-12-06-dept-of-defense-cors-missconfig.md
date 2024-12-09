---
title: "US Dept of Defense DC3 Cros Missconfig"
date: 2024-12-06 13:00:00 -0300
categories: [Vulnerability]
tags: [Cors Missconfig]
---

# Cors Missconfig no departamento de defesa dos eua (Department of Defense Cyber Crime Center: DC3)
# Entry points
encontrei 2 possíveis entry points em um dos maiores sites do dept de defesa dos eua,
e um válido, o site era do centro de crimes cibernéticos -> encontrei ele em um programa
de bug bounty na HackerOne

# SSL mal configurado
verifiquei o site e achei o primeiro possível entry point
no certificado SSL do site, onde o certificado SSL não correspondia ao CN (common name)
do www.defense.gov essa vulnerabilidade pode permitir atacantes usarem técnicas
de spoofing (se passar por algo como fingir ser o site)
depois de tentar validar o entry point desisti dela porquê os requerimentos
do escopo do programa de bug bounty do dept de defesa era muito rigoroso
e não permitia nada relacionado a exploração de vulnerabilidades encontradas
e eu iria quebrar a cabeça pensando como iria validar essa vulnerabilidade
sem explorar

# ClickJacking
o segundo possível Entry-Point foi uma possível vulnerabilidade de click jacking
foi fácil encontrar, usei o curl pra listar as respostas dos headers do site
quando recebi notei a falta do header ```X-frame-options``` sem ele atacantes
podem fazer ataques Click-Jacking onde ele engana o usuário fazendo
ele clicar em algo diferente do que ele acha que é, ele faz isso
sobrepondo páginas, ele faz isso sobrepondo uma página legítima como
um banco em outra sobrepondo também os botões, tentei testar o Click-jacking
mas não tive sucesso, eu estava certo que o site estava vulnerável a
Click-jacking mas algo no backend deles impedia isso, talvez um
firewall ou alguma política que impedia a requisição do iframe pra
sobrepor a página em outra, pensei em descobrir qual era essa configuração,
se fosse um firewall burlar e mostrar que eles estavam vulneráveis mas
isso já seria exploração e eles eram muitos rigorosos sobre isso
então como no primeiro Entry-Point dropei esse

# Cors Missconfig
depois disso um amigo encontrou um Cors Missconfig e me pediu pra validar, o Cors Missconfig
e uma vulnerabilidade onde o Cors que é um mecanismo de segurança que é implementado em
navegadores pra permitir que recursos de um domínio sejam acessados por scripts em outro 
domínio (utilizado em aplicações web quando se é necessário diferentes serviços podem precisar interagir entre si)
a segurança do cors ajuda a domínios a evitar Cross-site scripting(XSS) e Cross-site Forgery (CSRF), permitindo
que os navegadores controlem quais as origens que podem acessar seus recursos.

# Configuração certa do Cors

1. especificar origens confiáveis
em vez de permitir todas as origens (*), especifique quais domínios tẽm permissão para acessar os recursos
```Exemplo: Access-Control-Allow-Origin: https://www.exemplo.com```

2. limitar métodos permitidos
Permita apenas os métodos HTTP que são realmente necessários para a aplicação. Por exemplo, se você só precisa de GET e POST, configure assim:
```Exemplo: Access-Control-Allow-Methods: GET, POST ```

3. Restringir cabeçalhos permitidos
Permita apenas os cabeçalhos que são necessários para suas solicitações. Por exemplo, se você precisa de Content-Type e um cabeçalho personalizado
```Exemplo: Access-Control-Allow-Headers: Content-Type, X-Custom-Header```

4. Controlar credenciais
Se a sua aplicação precisa enviar cookies ou autenticação, você deve habilitar o suporte a credenciais, mas esteja ciente de que isso requer uma origem específica, não pode ser (*)
```Exemplo: Access-Control-Allow-Credentials: true```
E, neste caso, o cabeçalho Access-Control-Allow-Origin não pode ser *:
```Exemplo como deve ser: Access-Control-Allow-Origin: https://www.exemplo.com```
