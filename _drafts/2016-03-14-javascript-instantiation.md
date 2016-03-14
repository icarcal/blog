---
layout: post
title:  "Javascript - Instanciação"
date:   2016-03-14 14:26:00
categories: javascript
thumbnail: gravatar
tags:
 - javascript
author: Icaro
---

Pessoal, vamos falar um pouco sobre os conceitos básicos sobre instanciação de variáveis no javascript.

### Declaração e inicialização

A delcaração de variáveis no javascript, é feita através da palavra chave ```var``` e, com a chegada do [es2015], foram introduzidos o ```let``` e o ```const```, com algumas diferenças entre eles:

Exemplo de inicialização com ```var```:
{% highlight js %}
var x = 0;
var y = 1;
var z = 2;

console.log(x, y, z);
//0 1 2
{% endhighlight %}

Exemplo de inicialização com ```let```:
{% highlight js %}
let x = 0;
let y = 1;
let z = 2;

console.log(x, y, z);
//0 1 2
{% endhighlight %}

Exemplo de inicialização com ```const```:
{% highlight js %}
const x = 0;
const y = 1;
const z = 2;

console.log(x, y, z);
//0 1 2
{% endhighlight %}

#### Ué, mas não é mesma coisa?

Aparentemente sim, o que difere os tipos de delclaração é o ```escopo``` das variáveis, que falaremos à diante.

#### Inicialização de variáveis

É o momento onde uma variável assume um valor, podem ser
{% highlight js %}
x = 0;
y = 1;
z = 2;

console.log(x, y, z);
//0 1 2
{% endhighlight %}

A grande diferença entre este processo de inicialização e declaração de variáveis é que somente as ```declarações``` de variáveis sofrem o chamado hoisting e são "enviadas" ao início do escopo em que estão.

##### Mas tá tudo muito complicado

Calma!

Vamos agora explicar algumas palavras-chave descritas acima, para tudo ficar mais claro.

### Escopo

O javascript, possui três tipos de escopo que vamos abordar por tópicos.
São eles global, local e bloco (com a introdução do [es2016]).



## Hoisting

## Closure

## Variável Global

## Variável por parâmetro

## Instanciação usando uma IIFE

### Javascript: instanciação de variáveis