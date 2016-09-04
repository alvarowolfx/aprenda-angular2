---
layout: default
title: Forms
edit_link: https://github.com/alvarowolfx/aprenda-react/edit/gh-pages/forms/index.md
tweet: "Criando poderosos formulários com Angular 2"
---

_Atualizado em 16 de Julho de 2016_

Os formulários são fundamentais em qualquer aplicativo. No Angular 2, formulários mudaram um pouco desde a versão 1 do framework.

Onde costumávamos usar `ngModel` e mapear para o nosso modelo de dados internamente, no Angular 2 construímos formulários e controllers de maneira mais explícita.

Se por um lado se tem mais código para escrever, na prática, é mais fácil raciocinar sobre que com v1, e não temos mais
têm de lidar com problemas ngModel e $scope que eram um pouco frustrantes.

## Exemplo de Formulário simples

Vamos começar com um simples formulário de login em HTML com Angular 2:

```html
<form [ngFormModel]="loginForm" (submit)="doLogin($event)">
    <input ngControl="email" type="email" placeholder="Seu email">
    <input ngControl="password" type="password" placeholder="Sua senha">
  <button type="submit">Acessar</button>
</form>
```

E seu correspondente componente JS:

```javascript
import { Component } from '@angular/core';
import { FormBuilder, Validators } from '@angular/common';

@Component({
  selector: 'login-page',
  templateUrl: 'login-page.html'
})
export class LoginPage {
  constructor(fb: FormBuilder) {
    this.loginForm = fb.group({
      email: ["", Validators.required],
      password: ["", Validators.required]
    });
  }
  doLogin(event) {
    console.log(this.loginForm.value);
    event.preventDefault();
  }
}

```

Quando executamos isso, nos é mostrado um simples formulário de login com e-mail e senha:

![ex](ex1.png)

## FormBuilder

O FormBuilder do exemplo acima faz com que seja fácil especificar comportamentos do formulário e validadores que podemos aplicar.

No exemplo acima, estamos criando dois inputs, os campos `email` e `password`:

```javascript
this.loginForm = fb.group({
  email: ['', Validators.required],
  password: ['', Validators.required],
});
```

## ControlGroup

O `FormBuilder` cria instâncias do `ControlGroup`, que possuem referências ao `form`.

Em vez de usar os `FormBuilder`, nós também podemos construir o `ControlGroup` manualmente:

```javascript
this.loginForm = new ControlGroup({
  email: new Control("email", Validators.required),
  password: new Control("password", Validators.required)
});
```

Na prática, usaremos o `FormBuilder` para criar formulários de forma rápida.

## Form Directives

Você vai notar a falta do `ngModel` no formulário. Em vez disso, temos os decoradotors do `ngControl` que mapeiam os inputs para os nossos objetos que controlam o formulário:

```html
  <input ngControl="email" type="email" placeholder="Seu email">
```

Este "binds" no input do campo e-mail para a instância do nosso atributo `email` do formulário.

## Custom validators

Nós podemos construir formulário personalizado validadores como uma função simples:

```javascript
function containsMagicWord(c: Control) {
  if(c.value.indexOf('magic') >= 0) {
    return {
      noMagic: true
    }
  }

  // `null` significa valido
  return null
}

this.loginForm = fb.group({
  email: ['', containsMagicWord]
  password: ['', Validators.required],
});
```

## Handling form values

Podemos facilmente pegar o valor de um objeto Javascript do nosso formulário, ou o valor de um controlador de formulário individualmente:

```javascript
doLogin(event) {
  // Mostra o valor do formulário
  var formData = this.loginForm.value;
  // { email: 'blah@blah.net', password: 'imnottelling1' }

  // ou pega o valor de um form control:
  var email = this.loginForm.controls.email.value

  event.preventDefault();
}
```
