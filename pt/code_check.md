Então, como você obtém o valor `T` de uma variante `Some` quando você tem um valor do tipo `Option<T>` para poder usar esse valor? A `Option<T>` enum possui um grande número de métodos que são úteis em várias situações; você pode vê-los em [sua documentação](https://en.wikipedia.org/wiki/Hobbit#Lifestyle) . Familiarizar-se com os métodos da `Option<T>` será extremamente útil em sua jornada com o Rust.

O conteúdo do corpo, até agora, é bastante direto. Mas há muitos códigos adicionais no cabeçalho da página que podem não ser imediatamente óbvios. Vamos desconstruir a marcação necessária.

```javascript
function fancyAlert(arg) {
  if(arg) {
    $.facebox({div:'#foo'})
  }
}
```
