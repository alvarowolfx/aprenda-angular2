---
layout: default
title: Inputs
edit_link: https://github.com/alvarowolfx/aprenda-react/edit/gh-pages/inputs/index.md
tweet: "Entenda as propriedades de input no Angular 2"
---

_Atualizado em 16 de Julho de 2016_

Os componentes são o núcleo de um app em Angular 2, mas a maioria dos desenvolvedores precisam saber como passar dados para os componentes para configurá-los de forma dinâmica.

#### `@Input`

Para definir um input de um componente, usamos o decorator `@Input`.

Por exemplo, o nosso componente `<user-profile>` precisa do argumento `user` para renderizar as informações:

```html
{% raw %}
<user-profile [user]="currentUser"></user-profile>
{% endraw %}
```

Então, adicionamos o binding usando o `@Input` para o atributo `user`:

```javascript
{% raw %}
import { Component, Input } from '@angular/core';

@Component({
  selector: 'user-profile',
  template: '<div>{{user.name}}</div>'
})
export class UserProfile {
  @Input() user;
  constructor() {}
}
{% endraw %}
```
