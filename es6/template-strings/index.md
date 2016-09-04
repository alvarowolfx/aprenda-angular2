---
layout: default
title: Template Strings no ES6
edit_link: https://github.com/alvarowolfx/aprenda-react/edit/gh-pages/es6/template-strings/index.md
tweet: "Usando Template Strings no ES6"
---

_Atualizado em 16 de Julho de 2016_

ES6 adiciona a possiblidade de escrever uma string em várias linhas, sem tem que fazer aquele concatenamento terrível. Tudo que a gente precisa é usar backticks (o acento grave) no início e no fim da string:

```html
let template = `
  <div>
    <h2>Template</h2>
    <p>Este é um template de exemplo</p>
    <p>Viu como é bem mais simples?</p>
  </div>
`;
```

A gente agora consegue até fazer interpolação de uma expressão, usando `${expression}`:

```html
let x = 5;
let y = 10;
let template = `
  <div>O valor da soma é <span>${ x + y }</span></div>
`;
```
