---
layout: post
title: "Lógica da Programação Parte 1"
date: 2015-08-27 20:38:35
image: '/assets/img/'
description: 'Uma introdução ao que você precisa para continuar.'
tags:
- Pseudocódigo 
- Algoritmo
- Visualg
- Requisitos
categories:
- Lógica da Programação
twitter_text: 'Lógica da Programação Parte 1.'
---
Se quiser pular para o que mais necessita nesse momento, segue abaixo o que vamos ver:

- [Introdução a Lógica da Programação](https://raw.githubusercontent.com/aboutlucas/Arquivos-do-Blog/513eb7bc2be1de1fd6b5067dea843794f9eec686/series/logica/Logica.pdf)
- [Visualg Download](https://github.com/aboutlucas/Arquivos-do-Blog/blob/master/series/logica/visualg.zip?raw=true)
- [Linguagem Visualg](https://raw.githubusercontent.com/aboutlucas/Arquivos-do-Blog/513eb7bc2be1de1fd6b5067dea843794f9eec686/series/logica/UDESC_Apostila_sobre_Visualg_2011.pdf)
- [Linguagem Visualg](http://www.cefetsp.br/edu/adolfo/disciplinas/lpro/materiais/Linguagem_Visualg2.0.pdf)
- [Exercícios](http://partilho.com.br/visualg/exercicios-visualg/visualg-lista-de-exercicios/)



## Introdução

Os programas que vemos são feitos a partir de uma lógica onde as coisas acontecem passo a passo.
Vamos vermos como as coisas acontecem passo a passo através do [Visualg](https://github.com/aboutlucas/Arquivos-do-Blog/blob/master/series/logica/visualg.zip?raw=true), que tem a sequinte estrutura:

{% highlight sh %}
algoritmo "semnome"
// Função :
// Autor :
// Data : 
// Seção de Declarações 
inicio
// Seção de Comandos 
fimalgoritmo
{% endhighlight sh %}

A primeira linha é composta pela palavra-chave `algoritmo` seguida do seu nome delimitado por aspas duplas. Este nome será usado como título nas janelas de leitura de dados. A seção que se segue é a de declaração de variáveis, que termina com a linha que contém a palavra-chave `inicio`. Deste ponto em diante está a `seção de comandos`, que continua até a linha em que se encontre a palavra-chave `fimalgoritmo`. Esta última linha marca o final do pseudocódigo: todo texto existente a partir dela é ignorado pelo interpretador.

O VisuAlg permite a inclusão de comentários: qualquer texto precedido de `"//"` é ignorado, até se atingir o final da sua linha. Por este motivo, os comentários não se estendem por mais de uma linha: quando se deseja escrever comentários mais longos, que ocupem várias linhas, cada uma delas deverá começar por `"//"`.

### Condições
{% highlight sh %}
 - Se
 - Senao
 - Para [x] de [y] ate [z] faca
 - Repita
 - Enquanto
 - Escolha
 - Procedimento
 {% endhighlight sh %}
Esses são os inícios delas, não precisam seguir essa ordem mais devem ser fechadas,

**Exemplos:**
{% highlight sh %}
  Se 
  
  Senao
  
  FimSe
   
  Enquanto
  
  FimEnquanto
   
  Escolha
  
  FimEscolha
   
  Procedimento
  
  FimProcedimento
{% endhighlight sh %}

### Váriáveis

Nosso programa é inteligente, conseguimos fazer com que certo caracterer faça coisas incríveis assim como os números,
mas para isso precisamos criar variáveis que são palavavras para armazenar informações de números e caracteres.

Números

- Inteiro (Inteiro): 1 2 3 4 5
- Real (Número com Virgula): 0,1 5,8 1,22

Caracteres

- Caracter: Lucas, Comida, Pao

### Declarando uma variável
Para declarar uma variável no [visualg](https://pt.wikipedia.org/wiki/Visualg) que vai ser o nosso programa de teste de nossos programas fazemos assim:

{% highlight sh %}
nome: caracter
idade: inteiro
{% endhighlight sh %}

Dizemos ao nosso programa que nome é um caracterer assim podendo usar ele para gravar a informação do tipo caracter,
escrevemos nome para associar, poderia ser qualquer outra coisa, mas como vou fazer com que nome armazene meu nome fica mais
facíl de se entender. Assim como idade que vai armazenar a nossa idade que é do tipo inteiro.

### Criando o nosso Programa

Ao entrar no Visualg vemos essa tela:

{% highlight sh %}
algoritmo "semnome"
// Função :
// Autor :
// Data : 
// Seção de Declarações 
inicio
// Seção de Comandos 
fimalgoritmo
{% endhighlight sh %}

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
   leia(idade)
fimalgoritmo
{% endhighlight sh %}

### O que aconteceu?

Já tinhamos as nossas variáveis mais tinhamos que fazer com que aparecesse algo na tela para ai sim armazenar as informações que queriamos, mais para isso precisavamos que aparecesse isso na tela, então usamos o escreva para escrever **"Escreva seu nome"**, assim como para a idade, e para armazenar ambas informações usamos o **leia()**.
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
   leia(idade)
   escreva("Seu nome é: ",nome, "e sua idade é: ",idade)
fimalgoritmo
{% endhighlight sh %}

Legal né?
Usando condições fica mais interessante ainda, deixa nosso programa mais inteligente.


## Conclusão

O que acabamos de fazer foi um algoritmo, fizemos com que o nosso programa armazenasse o nome  e idade, depois escrevesse nosso nome e idade.
Agora para deixar ele mais inteligente veja  a [parte 2](/).

