---
layout: default
title: Classes no ES6/7
edit_link: https://github.com/alvarowolfx/aprenda-react/edit/gh-pages/es6/classes/index.md
tweet: "Como escrever classes do ES6/7"
---

_Atualizado em 16 de Julho de 2016_

Para quem já trabalhou com alguma linguagem orientada a objetos, as classes do ES6 vão fazer você se sentir em casa. Aqui está um exemplo simples:

```javascript
class Beer {
  sell(location) {
  }
}

class Heineken extends Beer {
  constructor() {
    super();
    this.deliciousness = 50;
    this.locations = 'Amsterdã';
    this.name = 'Heineken';
  }
  sell(location) {
    if(location != 'Vaticano') {
      return true
    }

    return false;
  }
}

class Itaipava extends Beer {
  constructor() {
    super();
    this.deliciousness = 1;
    this.locations = 'Petrópolis';
    this.name = 'Itaipava';
  }
  sell(location) {
    if(location == "Brasil") {
      return true;
    }

    return false;
  }
}

let cerva = new Heineken();

console.log('Tô bebendo uma ', beer.name, ' topzeira!');

cerva.sell();
```
