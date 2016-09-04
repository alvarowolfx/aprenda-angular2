---
layout: default
title: Eventos no Angular 2
edit_link: https://github.com/alvarowolfx/aprenda-react/edit/gh-pages/events/index.md
tweet: "Entendendo eventos no Angular 2"
---

_Atualizado em 16 de Julho de 2016_

Eventos no Angular 2 usam a notação de parênteses nos modelos e métodos de gatilho na classe de um componente. Por exemplo, suponha que temos esta classe de componente:

```javascript
@Component(...)
class MyComponent {
  clicked(event) {
  }
}
```

E este template:

```html
<button (click)="clicked()">Clique aqui</button>
```

Nosso método `clicked()` vai ser chamado quando o botão for clicado.

## Delegando eventos

Eventos no Angular 2 possuem o mesmo comportamento que eventos DOM, possuindo bubbling e propagate. Nada de especial para fazer aqui!

## O object event

Para capturar o evento, basta passar `$event` como atributo no método que está no template:mplate:

```html
<button (click)="clicked($event)"></button>
```

Perceba como é fácil modificar o event, chamando o método `preventDefault`, por exemplo:

```javascript
@Component(...)
class MyComponent {
  clicked(event) {
    event.preventDefault();
  }
}
```
