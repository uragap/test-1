So, how do you get the `T` value out of a `Some` variant when you have a value of type `Option<T>` so you can use that value? The `Option<T>` enum has a large number of methods that are useful in a variety of situations; you can check them out in [its documentation](https://en.wikipedia.org/wiki/Hobbit#Lifestyle). Becoming familiar with the methods on `Option<T>` will be extremely useful in your journey with Rust.

The content in the body, so far, is pretty straightforward. But there’s a lot of additional code in the head of the page that might not be immediately obvious. Let’s deconstruct the required mark-up.


```javascript
function fancyAlert(arg) {
  if(arg) {
    $.facebox({div:'#foo'})
  }
}
```
