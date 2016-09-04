---
layout: default
title: Templates
edit_link: https://github.com/alvarowolfx/aprenda-react/edit/gh-pages/templates/index.md
tweet: "Tudo sobre Templates em aplicações Angular 2"
---

_Atualizado em 16 de Julho de 2016_

Os modelos de template são muito semelhantes aos utilizados no Angular 1, apesar de existirem algumas mudanças sintáticas que tornam mais claro o que está acontecendo.

## Exemplo de template

Vamos começar com um template simples que renderiza o valor dos atributos `name` e `things`:

```html
{% raw %}
<div>
  Olá! Meu nome é {{name}} e eu gosto muito de {{thing}}.
</div>
{% endraw %}
```

## `{}`: Renderizando valores

Para renderizar um valor, podemos utilizar a sintaxe de `double-curly`, já utilizada pelo Angular 1:

```html
{% raw %}
Meu nome é {{name}}
{% endraw %}
```

Pipes, previamente conhecido por serem utilizados em "Filtros" no template, transformam um valor em um novo valor, como por exemplo transformar uma string em um valor monetário:

## `[]`: Criando binding de propriedades

Para criar um bind de uma variável a um componente, utilize a sintaxe `[]`. Se tivermos `this.currentVolume` em nosso componente, vamos vincular este atributo para o nosso componente e os valores vão ser sincronizados:

```html
<video-control [volume]="currentVolume"></video-control>
```

## `()`: Manipulando eventos events

Criamos um listener no template de um componente usando a sintaxe `()`

```html
<my-component (click)="onClick($event)"></my-component>
```

## `[()]`: Two-way data binding

Para manter o binding criado em um campo `input` e outros eventos, use a sintaxe `[()]`. Pense nisso como uma combinação de manipulação de um evento e binding da propriedade:

```html
<input [(ngModel)]="myName">
```

O valor do atributo `this.myName` do seu componente está sincronizado com o valor do campo `input`.

## `*`: O asterisco

`*` indica que esta directiva gerencia este componente como um template e tratará a sua renderização. Por exemplo, `ngFor` utilizado em nosso `<my-component>` renderiza o valor do loop de `item` em `itens`,
mas nunca retorna o nossa inicial `<my-component>` uma vez que é um template:

```html
<my-component *ngFor="#item of itens">
</my-component>
```

Outras directivas que trabalham em templates de maneira semelhante são `*ngIf` e `*ngSwitch`.
