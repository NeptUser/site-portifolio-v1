+++
title = "Desenvolvendo mecanismo de estágios para foguetes de garrafa PET"
date = "2026-03-25"
author = "Pedrinho"
cover = ""
coverCaption = ""
description = ""
tags=["obafog", "garrafa pet", "manual do mundo"]
draft = true
+++

## Contextualizando o projeto

No ano de 2025, a [OBAFOG](http://www.oba.org.br/site/?idcat=29&p=conteudo&pag=conteudo) (Olimpíada Brasileira de Foguetes) junto ao Iberê do Manual do Mundo lançaram uma nova categoria da competição para foguetes de garrafa PET de dois estágios. O mais interessante dessa categoria foi ver a velocidade com a qual as equipes, formadas por aluno do ensino médio, rapidamente construiram mecanismos realmente inteligentes para soltura do segundo estágio, até mesmo usaram eletrônica controlada via rádio-frequeência.

Vendo todas essa ideias incríveis, me inspirei e resolvi criar um sistema eletrônico e autônomo de soltura do segundo estágio, primeiro porque é legal e segundo porque vejo isso como uma forma de tornar a competição mais acessível. Por isso, estou criando também esse artigo que vai acompanhar o desenvolvimento deste mecanismo, e que ao final será totalmente disponibilizado a quem quiser utilizar de forma totalmente gratuita, ou seja, open source total. Outra coisa que me anima bastante é pensar como as equipes vão modificar e melhorar esse mecanismo, me pergunto em quanto tempo essa primeira versão se tornará obsoleta.

Voltando a falar do mecanismo em sí, a ideia é que ele possa como 

Por fim, semanalmente (ou não), eu vou fazer updates por aqui do que eu fiz e principalmente porque eu fiz, e já vou disponibilizando as partes. Claro que ao final eu vou fazer um artigo bonitinho compilando tudo, e especialmente com uma linguagem mais formal, já neste "cederno de engenharia", a ideia é parecer uma conversa de nerds em um bar, especialmente para que eu possa escrever mais rapidamente.

Se tiver alguma sugestão, dúvida, crítica, elogio ou ameaça, pode me mandar um email ou chamar nas redes sociais, X ou Instagram.

## Direto ao problema

> Agora que sabemos o que quero fazer, precisamos decidir como fazer!

### Restrições do projeto
Já tendo a premissa, precisamos ver as nossas restrições; felizmente, são poucas:

1. Funcionar com qualquer perfil de voo.
2. Ser o mais leve possível.
3. Fácil de operar.
4. (OPICIONAL) Ter algum nível de estanqueidade.

Acho que aqui é melhor eu explicar como cheguei nesses requisitos.

#### 1. Funcionar em qualquer perfil de voo.
O que quero dizer com esse requisito? Basicamente, me refiro ao mecânismo funcionar adequadamente em qualquer voo, seja um de 10m ou um de 500m, independente de ser um voo oblíquo ou vertical.

#### 2. Ser o mais leve possível
Essa eu imagino que seja intuitiva, já que estamos falando de uma aplicação aeroespacial, certo? ERRADO! No foguetemodelismo universitário, podemos propositalmente deixar algo mais pesado, já que em competições como a [LASC](https://www.lasc.space), temos alvos de altitude a atingir. Na OBA, a ideia é ter o maior alcance (distância lateral), dito isso, sim, o mais leve possível, por favor!

#### 3. Fácil de operar
Requisito muito importante porque esse mecanismo poderá ser usado por alunos que entendem bem de eletrônica, mas também quero que o aventureiro que encontrou esse projeto por acaso seja capaz de usar. Além da eletrônica, a parte mecânica precisa ser o mais simples possível e que seja confiável para ser usada em campo.

#### 4. Estanqueidade
Coloquei como opcional, mas na verdade é bem importante porque esses foguetes usam água, ou vinagre (que é uma solução aquosa) como um de seus componentes propelentes, e é interressante que o mecanismo resista a alguns usos e muito provável que ele fique bem onde pode ser molhado.

###  E qual a solução?

Bem, vamos dividir isso em eletrônica e mecânica, ambas devem respeitar as restrições iniciais.

#### Eletrônica, ou eletônica para os mais intimos...

Para a eletrônica, precisamos lidar com o hardware e software.

##### Quanto ao hardware (o circuito, homi)
Pro hardware, a ideia é que seja algo simples, isso implica em mais algumas restrições, como:

- Poucos componentes;
- Componentes baratos e comuns;
- Componentes apenas TH (Trough Hole).

As duas primeiras restrições são simples de entender, já a tarceira é imposta também na ideia de facilitar a montagem da placa, inclusive por pessoas sem experiência prévia.

**Vamos aos componentes escolhidos...**

1. Attiny85
Um microcontrolador pequeno, com arquiterura avr (a mesma do arduino) que consome pouco [falar melhor sobre ele]

2. MPU-6050

Esse é um IMU (Inecial Measurement Unit) [falar melhor sobre]

3. Servo SG-90

[falar melhor sopbre]

4. Bateria????


##### Quanto ao firmware (software)

# POST EM OBRAS


