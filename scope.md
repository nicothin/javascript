# Область видимости

Переменные в JS могут быть глобальными (доступны везде) и локальными (видны только в текущей области видимости).

Технически, глобальные переменные — это свойства объекта `window`:

```js
// Глобальная переменная
console.log(location);
console.log(window.location); // то же самое
```

Локальная область видимости ограничивается функцией (для `var`) или блоком `{...}` (для `let` и `const`).

```js
var test = 99; // глобальная переменная

(function scopeTest() {
  var test = 0;      // локальная переменная
  console.log(test); // 0
}());

console.log(test);   // 99
```

Глобальные доступны везде, локальные — только в своей области видимости:

```js
var globalTest = 99; // глобальная переменная

(function scopeTest() {
  var localTest = 0;       // локальная переменная
  console.log(globalTest); // 99
  console.log(localTest);  // 0
}());

console.log(globalTest);   // 99
console.log(localTest);    // Uncaught ReferenceError: localTest is not defined
```

Циклы и условные конструкции не влияют на видимость переменных, объявленных с `var`.
