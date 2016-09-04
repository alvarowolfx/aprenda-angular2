---
layout: default
title: Variáveis no ES6/7
edit_link: https://github.com/alvarowolfx/aprenda-react/edit/gh-pages/es6/variables/index.md
tweet: "Entendendo as variáveis no ES6/7"
---

_Atualizado em 16 de Julho de 2016_

A partir do ES6, nós temos um novo jeito de inicializar variáveis, diga olá ao: `let`

## Var

Antes do ES6, nós só tinhamos `var`, que nos possibilitava criar uma variável no escopo da função mais próxima.

Isso era um problema pois o valor variáveis ficava disponível para toda a função, mesmo quando eram utilizadas apenas num escopo mais interno.

Veja esse exemplo de loop no ES6:

```javascript
for(var i in meuArray) {
}
```

Mesmo após o loop ser executado, a variável `i` ainda está disponível!

## Let

Com o `let`, esse "vazamento" de valor não é mais um problema. O `let` cria uma variável que só é disponível no *bloco* mas próximo. Não na função mais próxima.

Isso é maravilhoso em loops e closures, perceba:

```javascript
for(let i in thing) {
 // i está disponível
}

// i NÃO está disponível
```

No geral, sempre use `let`, ao menos que você tenha um motivo muito bom pra usar `var`.
