---
layout: post
title: "Lógica da Programação Parte 1"
date: 2015-08-27 20:38:35
image: '/assets/img/'
description: 'Uma introdução ao que você precisa para continuar.'
tags:
- logica
- programacao
categories:
- Logica da Programacao
twitter_text: 'Lógica da Programação Parte 1.'
---
Se quiser pular para o que mais necessita nesse momento, segue abaixo o que vamos ver:

- [Introdução a Lógica da Programção](https://github.com/aboutlucas/Arquivos-do-Blog/blob/master/series/logica/Apostila-de-Logica-de-Programacao.pdf/)
- [Visualg](https://github.com/aboutlucas/Arquivos-do-Blog/blob/master/series/logica/visualg.zip/)
- [Visualg - Documentação](https://github.com/aboutlucas/Arquivos-do-Blog/blob/master/series/logica/UDESC_Apostila_sobre_Visualg_2011.pdf/)
- [Exercícios](#/)


## Introdução

Para criar um programa é necessário criar condições, espaço para armazenar informações e fazer o controle deles.

### Condições

 - Se
 - Senao
 - Para [x] de [y] ate [z] faca
 - Repita
 - Enquanto
 - Escolha
 - Procedimento
 
### Váriáveis

Nosso programa é inteligente, conseguimos fazer com que certo caracterer faça coisas incríveis assim como os números,
mas para isso precisamos criar variáveis que são palavavras para armazenar informações de números e caracteres.

Números

- Inteiro (Inteiro)
- Real (Número com Virgula)

Caracteres

- Caracter

### Declarando uma variável
Para declarar uma variável no [visualg](https://pt.wikipedia.org/wiki/Visualg/) que vai ser o nosso programa de teste de nossos programas fazemos assim:

{% highlight sh %}
nome: caracter
idade: inteiro
{% endhighlight sh %}

Dizemos ao nosso programa que nome é um caracterer assim podendo usar ele para gravar a informação do tipo caracter,
escrevemos nome para associar, poderia ser qualquer outra coisa, mas como vou fazer com que nome armazene meu nome fica mais
facíl de se entender. Assim como idade que vai armazenar a nossa idade que é do tipo inteiro.

### Criando o nosso Programa

Ao entrar no Visualg vemos essa tela:

...

Em algoritmo as informações de nosso programa, em **var** colocamos as nossas variáveis, e começamos a lógica de nosso programa em inicio não podendo escrever algo depois de fimalgoritmo, se escrever algo depois de fimalgoritmo vai resultar em erro na execução.


{% highlight sh %}
algoritmo
// Função :
// Autor :
// Data : 30/08/2015
// Seção de Declarações
var
   nome: caracter
   idade: inteiro
inicio
   escreva("Escreva seu nome: ")
   leia(nome)
   escreva("Escreva sua idade:")
   leia(inteiro)
fimalgoritmo
{% endhighlight sh %}

### O que aconteceu?

Já tinhamos as nossas variáveis mais tinhamos que fazer com que aparecesse algo na tela para ai sim armazenar as informações que queriamos, mais para isso precisavamos que aparecesse isso na tela, então usamos o escreva para escrever "Escreva seu nome", assim como para a idade, e para armazenar ambas informações usamos o leia().
Agora podemos fazer o controle das informações veja.

{% highlight sh %}
algoritmo
// Função :
// Autor :
// Data : 30/08/2015
// Seção de Declarações
var
   nome: caracter
   idade: inteiro
inicio
   escreva("Escreva seu nome: ")
   leia(nome)
   escreva("Escreva sua idade:")
   leia(inteiro)
   escreva("Seu nome é: ",nome, "e sua idade é: ",idade)
fimalgoritmo
{% endhighlight sh %}

Legal né?
Usando condições fica mais interessante ainda, deixa nosso programa mais inteligente.


## Conclusão

O que acabamos de fazer foi um algoritmo, fizemos com que o nosso programa armazenasse o nome  e idade, depois escrevesse nosso nome e idade.
Agora para deixar ele mais inteligente veja  a [parte 2](/).

