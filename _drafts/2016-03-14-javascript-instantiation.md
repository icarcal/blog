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
A declaração de variáveis no javascript, é feita através da palavra chave ```var``` e, com a chegada do [es2015], foram introduzidos o ```let``` e o ```const```, com algumas diferenças entre eles:

Exemplo de declarações com ```var```, ```let``` e ```const```:
{% highlight js %}
var x;
let y;
const z = 1;

console.log(x, y, z);
//undefined undefined 1
{% endhighlight %}

##### Ué, mas não é mesma coisa?

Aparentemente sim, o que difere os tipos de declaração é o ```escopo``` das variáveis, que falaremos à diante.

#### Inicialização de variáveis

É o momento onde uma variável no javascript assume um valor:
{% highlight js %}
x = 0;
y = 1;
z = 2;

console.log(x, y, z);
//0 1 2
{% endhighlight %}

A grande diferença entre este processo de declaração e inicialização de variáveis é que somente as ```declarações``` de variáveis sofrem o chamado hoisting e são "enviadas" ao início do escopo em que estão.

##### Mas tá tudo muito complicado

Calma!

Vamos agora explicar algumas palavras-chave descritas acima, para tudo ficar mais claro.

### Escopo

O javascript, possui três tipos de escopo que vamos abordar por tópicos.

São eles global, local e bloco (com a introdução do [es2015]).

#### Escopo Global

Toda a declaração/inicialização de variável que está fora de uma função, é automaticamente definida como global e seu valor pode ser utilizado em qualquer parte do seu script:

Exemplo:
{% highlight js %}
var x = 1; //variável global

function display(){
	var y; // Variável local

	console.log(x);
}

display();
// 1
{% endhighlight %}

No exemplo acima, conseguimos utilizar a variável ```x``` sem problemas dentro de uma função, pois ela está no escopo global (foi declarada fora da função);

#### Escopo Local

Toda variável declarada dentro de uma função, é local, ou sej, a variável é sempre destruída e recriada a cada execução daquela função, e não poderá ser acessada do escopo global.

Exemplo:
{% highlight js %}
var x = 1; //variável global

function display(){
	var y = 2; // Variável local

	console.log(x, y);
}

display();
// 1 2

console.log(y);
ReferenceError: y is not defined
{% endhighlight %}

No exemplo acima, dentro da função definimos a variável ```y```, e ela possui o escopo local, sendo assim, caso seja chamada fora desta função, será gerado um erro de referência, pois ela não foi declarada ou incializada no escopo global

### Escopo de bloco

No [es2015], foi introduzido um novo tipo de escopo, o escopo de bloco, ou seja, uma variável declarada com ```const``` ou ```let``` dentro de um bloco que é delimitado por ```{}`` (um ```if{...}```) por exemplo, poderá ser utilizada somente dentro deste escopo, e caso seja atribuído um valor para esta variável dentro do bloco, este valor será mantido somente dentro deste bloco.

Exemplo de declaração no escopo:
{% highlight js %}
let a = 0;

{
 	let b = 1;
	console.log(a, b)
	// 0 1
}

console.log(a, b)
// ReferenceError: b is not defined
{% endhighlight %}

Exemplo de utilização da variável no escopo
{% highlight js %}
let a = 0;
let b = 0;

{
	console.log(a, b)
	// 0 1

	let b = 1;
}

console.log(a, b)
// 0 0
{% endhighlight %}

No primeiro exemplos acima, o bloco ```{}``` define o escopo, ou seja, caso a variável seja declarada dentro do bloco com ```let``` ela só existe neste momento, sendo destruída em seguida, por isso, no primeiro exemplo foi gerado um erro de referência.

Já no segundo exemplo a variável não está em nenhum bloco, e mesmo sendo declarada com ```let```, ela se torna uam variável global, e em seguida, o valor dela é alterado para o bloco em que foi declarada com ```let```.

## Hoisting

O javascript possui uma feature bem bacana, chamada hoisting.

Hoisting consiste no processo de levar a declaração da variável ao início do escopo, ou seja, não importa onde você declarou a mesma, ela será sempre a primeira coisa à ser tratada no escopo, antes da execução do mesmo.

Exemplo:
{% highlight js %}
x = 0;
y = 2;

var x;

console.log(x, y);
// 0 2

var y;
{% endhighlight %}

No exemplo dado, mesmo que a variável ```y``` foi declarada após a exibição com o ```console.log()```, a variável existe e é como se tivessemos o seguinte código:
{% highlight js %}
var x;
var y;

x = 0;
y = 2;

console.log(x, y);
// 0 2
{% endhighlight %}

##### Cuidado com o ```let```
O processo de hoisting não se aplica ao ```let```, ou seja, uma variável declara com ```let``` não é levada ao início do escopo, podendo assim gerar erros para quem não está acostumado com o [es2015].

Exemplo:
{% highlight js %}
let a = 0;
let b = 0;

{
	console.log(a, b)
	let b = 1;
}

console.log(a, b)
//ReferenceError: b is not defined
{% endhighlight %}

#### Dicas
``Apenas a declaração de uma variável é hoisted, sua inicialização não``
``Declare sempre as variáveis no início do escopo para que fique claro e organizado ``

### Hoisting em funções
Para funções o processo de hoisting é diferente e pode acontecer de duas formas:

#### Quando a função é expressamente declarada:
Neste caso, não só o nome será hoisted, mas também o corpo da função.

Exemplo:
{% highlight js %}
funcFoo();
// a

function funcFoo(){
	console.log('a');
}

{% endhighlight %}

## Closure

## Variável por parâmetro

## Instanciação usando uma IIFE


Referências:
http://loopinfinito.com.br/2014/10/29/hoisting-e-escopo-em-javascript/
https://msdn.microsoft.com/en-us/library/bzt2dkta(v=vs.94).aspx
