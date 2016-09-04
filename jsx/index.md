---
layout: default
title: Entenda o JSX
edit_link: https://github.com/alvarowolfx/aprenda-react/edit/gh-pages/jsx/index.md
tweet: "Entenda o JSX"
---

_Atualizado em 04 de Setembro de 2016_

Temos a polêmica do XML no meio do Javascript, o famoso **JSX**. Ele nada mais é do que um **syntatic sugar**, pensado para simplificar o processo de se montar interfaces simples e declarativas, tudo no final das contas vira Javascript.

Inicialmente também não gostava da ideia, mas depois vi algumas vantagens :

- Você está basicamente o tempo todo trabalhando em Javascript, sem precisar saber tags específicas de algum framework ou coisa do tipo. Quer fazer uma lista ? Faça um *for/map* em uma lista. Quer fazer um condicional ? Escreva um *if/else*. Simples.
- O JSX é compilado, então se você fizer alguma coisa errada, você vai ter um feedback muito mais rápido ao desenvolver, nada de ver o erro só no navegador e após recarregar a página ( ou pior, só em produção ).
- Ao utilizar as tags JSX, você consegue ter um suporte de IDE’s muito mais interessante, não é apenas uma string que não pode ser entendida pela IDE. É possível ter até mesmo validação e auto-completar dos atributos de cada componente.

## Exemplo

Um exemplo simples de um componente escrito usando JSX:

```javascript
{% raw %}

var HelloMessage = React.createClass({
  render: function() {
    return <div>Olá {this.props.name}</div>;
  }
});

ReactDOM.render(<HelloMessage name="John" />, mountNode);
{% endraw %}
```

Depois de compilado, o código gerado será esse :

```javascript
{% raw %}
"use strict";

var HelloMessage = React.createClass({
  displayName: "HelloMessage",

  render: function render() {
    return React.createElement(
      "div",
      null,
      "Olá ",
      this.props.name
    );
  }
});

ReactDOM.render(React.createElement(HelloMessage, { name: "John" }), mountNode);

{% endraw %}
```
