# Глобальный объект на примере window

Объект Window — глобальный объект, ответственный за выполнение всего кода в браузере.

- Глобальные переменные являются свойствами объекта `window`.
- Глобальные функции являются методами объекта `window`.

```js
var a = 5;
console.log(window.a); // 5

// Список свойств и методов глобального объекта
console.log(window);
console.log(window);
```

```js
// Запустим функцию один раз через 3 сек.
setTimeout(sayWOW, 3000); // То же, что window.setTimeout()

// Запустим функцию бесконечное число раз с паузой в 2 сек.
setInterval(sayWOW, 2000);

// Запустим функцию бесконечное число раз с паузой в 0.5 сек.
var wower = setInterval(sayWOW, 500);
// Но выключим его
clearInterval(wower);

function sayWOW() {
  console.log('WOW');
}
```
