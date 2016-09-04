---
layout: default
title: Componentes
edit_link: https://github.com/alvarowolfx/aprenda-react/edit/gh-pages/components/index.md
tweet: "Como utilizar componentes usando Angular 2"
---

_Atualizado em 16 de Julho de 2016_

No Angular 2, Componentes são a principal maneira de criar e especificar elementos e lógica na página.

usando Angular 1, nós conseguimos isso através de directivas, controllers e $scope. No angular 2, todos esses conceitos
são combinados em componentes.

### Criando um componente

Aqui está um componente simples que renderiza o valor do atributo `name`, e um botão que aciona um método para imprimir o nosso nome para o console:

```javascript
{% raw %}
import { Component } from '@angular/core';

@Component({
  selector: 'my-component',
  template: '<div>Olá! Meu nome é {{name}}. <button (click)="sayMyName()">Diga meu nome</button></div>'
})
export class MyComponent {
  constructor() {
    this.name = 'Michael'
  }
  sayMyName() {
    console.log('Meu nome é', this.name)
  }
}
{% endraw %}
```

Quando usamos a tag `<my-component></my-component>` em nosso HTML, este componente será criado, o nosso construtor chamado e renderizado no DOM.
