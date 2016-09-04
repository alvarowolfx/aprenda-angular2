---
layout: default
title: ViewChild
edit_link: https://github.com/alvarowolfx/aprenda-react/edit/gh-pages/viewChild/index.md
tweet: "Acesso entre componentes no Angular 2"
---

_Atualizado em 16 de Julho de 2016_

Como todos os componentes em Angular 2 possuem classes, você pode precisar chamar métodos destas classes. Isto requer acesso ao componente.

#### `@ViewChild`

Para ter acesso a um componente e seus métodos, podemos usar a anotação `@ViewChild`.

Por exemplo, o nosso componente `<user-profile>` pode ter um método chamado `sendData()`.


```javascript
{% raw %}
@Component({
  selector: 'user-profile'
})

export class UserProfile {
  constructor() {}
  sendData(){
    //enviando informações
  }
}
{% endraw %}
```

Quando usarmos o `user-profile` em nossa página principal, faremos referência a classe e, em seguida, atribuí-la a uma propriedade local.

```javascript
{% raw %}
import { Component, ViewChild } from '@angular/core';
import { UserProfile } from '../user-profile';

@Component({
  template: '<user-profile (click)="update()"></user-profile>',
  directives: [UserProfile]
})
export class MasterPage {
  // Passamos o componente queremos pegar
  // atribuído a uma propriedade pública em nossa classe
  // e passamos o tipo para nosso componente
  @ViewChild(UserProfile) userProfile: UserProfile

  constructor() { }
  update(){
    this.userProfile.sendData();
  }
}
{% endraw %}
```

Nós também podemos fazer a mesma coisa com uma variável local.
Ao invés de carregarmos a classe particular, podemos usar outro tipo de abordagem:

```javascript
{% raw %}
import { Component, ViewChild } from '@angular/core';
import { UserProfile } from '../user-profile';

@Component({
  template: '<user-profile #myProfile (click)="update()"></user-profile>',
  directives: [UserProfile]
})
export class MasterPage {
  @ViewChild('myProfile') userProfile: UserProfile
  constructor() { }
  update(){
    this.userProfile.sendData();
  }
}
{% endraw %}
```
