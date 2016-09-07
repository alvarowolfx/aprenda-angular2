---
layout: default
title: Entendedo Promises
edit_link: https://github.com/driftyco/learn-angular2/edit/gh-pages/es6/promises.md
tweet: "Entendendo Promises"
---

_Atualizado em 7 de Setembro de 2016_

[Work in Progress]

<!--

Promises permite escrever código assíncrono de maneira mais fácil, comparada por exemplo ao o uso de callbacks. Muitas bibliotecas e Web APIs retornam promessas para operações assíncronas, como `fetch()`:

```javascript
loadUsers() {
  fetch('/api/usuarios').then((response) => {
    return response.json();
  }).then((data) => {
    this.users = data;
  }).catch((ex) => {
    console.error('Erro: usuários não puderam ser listados', ex);
  });
}
```

Nós também podemos criar nossas próprias promessas usando o construtor `new Promise()`, porém isso deve ser evitado se você utiliza alguma biblioteca ou framework que já possui uma API como o `fetch()`:

```javascript
respostaDaVidaDoUniversoETudoMais() {
  return new Promise((resolve, reject) => {
    resolve(42);
  });
}
```

Promises parecem simples a um primeiro momento, mas são complexas e extremamente poderosas na prática. Se ligue para não vacilar e fazer [anti-patterns](http://www.datchley.name/promise-patterns-anti-patterns/) no seu código.

-->
