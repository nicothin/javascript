# Конструкторы

Конструктор — специальная функция, задача которой — заполнить пустой объект свойствами и методами. Позволяют создавать что-то вроде своего типа данных.

- Именуются с большой буквы.
- Функция, принадлежащая объекту, назвается методом.

## Встроенные

```js
// Создаём пустой объект
var test = new Object();

// Создаём объект c текущими датой и временем
var myDate = new Date();
console.log(myDate);

// Создаём объект, являющийся массивом (4 элемента)
var arr = new Array(1, 2, 3, 4, 'пять');
console.log(arr);

// Создаём объект строкового типа
var str = new String('строка на четыре слова');

// Создаём функцию (нежелательно, ибо замедляет)
var func = new Function('x', 'y', 'return x + y;'); // последний аргумент — тело функции
console.log(func(1, 4));
```



## Свои конструкторы

```js
// Простейший конструктор со свойствами
function Place(x, y) {
  this.x = x;
  this.y = y;
}
var positionTop = new Place(0, 0);
var positionBottom = new Place(0, 100);
console.log(positionTop);
console.log(positionBottom′);

// Конструктор со свойствами и методами
function Cat(name) {
  this.name = name;
  this.sayMeou = function() {
    console.log('Meou from ' + this.name);
  }
}
var cat = new Cat('Барсик');
cat.sayMeou();
```
