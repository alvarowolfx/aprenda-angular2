---
layout: default
title: Lifecycle de uma aplicação Angular 2
edit_link: https://github.com/alvarowolfx/aprenda-react/edit/gh-pages/lifecycle/index.md
tweet: "Lifecycle de uma aplicação Angular 2"
---

_Atualizado em 16 de Julho de 2016_

Aplicações Angular passam por um processo várias etapas desde o seu bootstrap e ciclo de vida, podendo
responder a vários eventos como o quando o aplicativo é iniciado, executado e quando se cria/destrói componentes.

## Bootstrap

O Angular 2 (atualmente) precisa ser inicializado usando o componente de raiz para o aplicativo.

No arquivo JS principal da nossa aplicação, vamos colocar isso:


```javascript
{% raw %}
import { bootstrap } from '@angular/platform-browser-dynamic';
import { Component } from '@angular/core';

// Anotações do componente
@Component({
  selector: 'my-app',
  template: '<h1>Olá {{ name }}</h1>'
})
// Controller do componente
class MyApp {
  constructor() {
    this.name = 'Marcos';
  }
}

bootstrap(MyApp)
{% endraw %}
```

O componente `my-app` inicializa a nossa aplicação em um nível configurável, e seu modelo
é o lugar onde todos os nossos componentes são criados.

## Inicializando o nosso Componente

Quando um componente é criado, seu construtor é chamado. Isto acontece quando inicializamos algum estados
para o nosso componente, mas se baseado em algumas propriedades ou dados de componentes filhos, precisamos
esperar pelos componentes filhos para que o componente inicialize pela primeira vez.

Para fazer isso, nós podemos manipular o evento ciclo de vida utilizando o método `ngOnInit`. Existe a opção de utilizar `setTimeout` em nosso construtor para um efeito semelhante:

```javascript
import {Component, bootstrap} from 'angular2/angular2';

// Anotações do componente
@Component({
  selector: 'street-map',
  template: '<map-window></map-window><map-controls></map-controls>'
})
// Controller do componente
class StreetMap {
  constructor() {
    this.name = 'Max';
  }

  setMapWindow(mapWindow) {
    this.mapWindow = mapWindow;
  }

  setMapControls(mapControls) {
    this.mapControls = mapControls;
  }

  ngOnInit() {
    // Quando as propriedades são resolvidades
    // os valores de this.mapWindow e this.mapControls
    // também serão resolvidos para os componentes
    // <map-window> e <map-controls>
  }
}
```

## Ciclo de vida de um componente

Como `ngOnInit`, podemos utilizar e rastrear vários eventos através do ciclo de vida de um componente. Para uma
lista completa, consulte a [seção "Lifecyle Hooks" na documentação oficial do Angular 2](https://angular.io/docs/ts/latest/guide/lifecycle-hooks.html).

```javascript
// Anotações do componente
@Component({
  selector: 'street-map',
  template: '<map-window></map-window><map-controls></map-controls>',
})
// Controller do componente
class StreetMap {
  ngOnInit() {
    // Quando as propriedades são resolvidades
    // os valores de this.mapWindow e this.mapControls
    // também serão resolvidos para os componentes
    // <map-window> e <map-controls>
  }
  ngOnDestroy() {
    // Evento é invocado quando o componente é destruído
  }
  ngDoCheck() {
    // Detecção de mudanças customizável
  }
  ngOnChanges(changes) {
    // Chamado após nosso binding ser checado, validando
    // se um dos bindings foi alterado
    //
    // o parâmetro `changes` é um objeto no formato:
    // {
    //   'prop': PropertyUpdate
    // }
  }
  ngAfterContentInit() {
    // Conteúdo do componente foi inicializado
  }
  ngAfterContentChecked() {
    // Conteúdo do componente foi checado
  }
  ngAfterViewInit() {
    // View do componente foi inicializada
  }
  ngAfterViewChecked() {
    // View do componente foi checada/validada
  }
}
```
