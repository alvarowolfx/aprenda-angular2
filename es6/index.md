---
layout: default
title: ES6, ES7 e Babel... O que é tudo isso ?
edit_link: https://github.com/alvarowolfx/aprenda-react/edit/gh-pages/es6/index.md
tweet: "ES6, ES7 e Babel... O que é tudo isso ?"
---

_Atualizado em 7 de Setembro de 2016_

### O que é o ES6 ?

Antigamente você apenas incluia seu código Javascript em uma tag \<script\> no cabeçalho da sua páginas e seu código iria rodar como pretendido. Hoje em dia, nós pré-processamos nosso Javascript para poder experimentar funcionalidades e extensões da linguagem que os browsers atuais ainda não suportam, ou talvez nem venham a ser suportadas. 

O padrão para o Javascript no browsers é o ECMAScript. Ele é a especificação da linguagem, utilizada para implementar a linguagem Javascript. ES6, ou ECMAScript 6 é a primeira primeira atualização significante na linguagem desde 2009, que foi lançado o ES5.

Várias funcionalidades do ES6 já estão disponíveis nos motores Javascript mais modernos. Porém usando o [Babel](https://babeljs.io/), temos acesso a muito mais funcionalidades enquanto garante que nosso código Javascript vai rodar em mais plataformas. Muitos desenvolvedores React utilizam o [Babel](https://babeljs.io/) para habilitar as funcionalidades do ES6 e garantir a consistência entre os diferentes navegadores, já que seu código vai rodar no Chrome, Firefox, Safari, Opera e outros navegadores.

### Babel

O [Babel](https://babeljs.io/) é a principal ferramenta utilizada para pré-processar Javascript hoje. Ele é um _parser_ altamente configurável, que deixa você experimentar funcionalidades e extensões, compilando isso para o bom e velho Javascript que é suportado pela maioria das plataformas. Claro, se a plataforma não suporta uma função nativa do ES6, como o Map(), o Babel não vai conseguir te ajudar, mas ele consegue muitas vezes fornecer polyfills de APIs que estejam faltando para prover alguma funcionalidade nova.

A ferramente ainda permite o debug da sua aplicação com o código fonte original, incluindo os _source maps_ junto do Javascript compilado. Os interpretadores vão rodar o seu código compilado e fazer o mapeamento com o código original para que você possa fazer o debug, já que o código compilado a maiorias das vezes é bastante feio.

### Destaques do ES6

Algumas das principais funcionalidades do ES6 estão listados no menu lateral e são melhores explorados para que você possa entender cada um deles.
