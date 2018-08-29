# Число

Число (целое, дробное), или `Infinity`/`-Infinity`, или `NaN`.

- Хранятся в памяти по стандарту IEEE 754. На число выделяется 8 байт(64 бита).
- Могут быть записаны в десятеричной, шестнадцатиричной системах, а также «научным» способом (`1e3`).
- Некоторые числа при вычислениях дают парадоксальный результат (`0.1 + 0.2`).
- Имеется [встроенный глобальный объект Math](https://developer.mozilla.org/ru/docs/Web/JavaScript/Reference/Global_Objects/Math), в свойствах которого хранятся мат. константы и функции.

```js
console.log( 1000 ); // 1000
console.log( 1e3 );  // 1000 (единица и ТРИ нуля после единицы)
console.log( 1e-3 ); // 0.001 (единица, сдвинутая на ТРИ позиции вправо за десятичную точку)
console.log( Number.MAX_VALUE ); // 1.7976931348623157e+308 (наибольшее представимое положительное число)
console.log( Number.MIN_VALUE ); // 5e-324 (наименьшее представимое положительное число)

var typeNumber = 1.2;
console.log( typeof typeNumber ); // number
```



## Бесконечность

Возникает при делении на нуль и превышении макс. возможного числа.

```js
var typeNumberInf = 1 / 0;   // Infinity
var typeNumberInf2 = -1 / 0; // -Infinity
console.log( typeof typeNumberInf ); // number
console.log( Infinity > 100500 ); // true
console.log( Infinity + 100500 ); // Infinity
console.log( 1e309 ); // Infinity
```



## NaN («ошибка вычислений», «не число»)

На самом деле, число. Обозначает математическую ошибку.

- Не равно ничему, в т.ч. самому себе.
- Можно проверить функцией `isNaN()` (приведёт к числу, вернёт `true`, если это `NaN`).
- Любая операция с `NaN` возвращает `NaN`.

```js
console.log( 0 / 0 ); // NaN
var typeNumberNan = NaN;
console.log( typeof typeNumberNan ); // number

console.log( isNaN(true) );     //  false, это не NaN, т.к. значение приведено к числу 1
console.log( isNaN(false) );    //  false, это не NaN, т.к. значение приведено к числу 0
console.log( isNaN(null) );     //  false, это не NaN, т.к. значение приведено к числу 0
console.log( isNaN({}) );       //  true, это NaN
console.log( isNaN([]) );       //  false, это не NaN, т.к. значение приведено к числу 0
console.log( isNaN("\n  \n") ); //  false, это не NaN, т.к. значение приведено к числу 0
```



## Преобразование к числу

```js
// С помощью унарного плюса — жёсткое
console.log( +'99' );         // 99 — строка «содержит число»
console.log( +'  \n99' );     // 99 — то же, но с пробельными символами вначале (игнорируются)
console.log( +'1e3' );        // 1000 — строка «содержит число»
console.log( +'9 9' );        // NaN — из-за пробела в строке
console.log( +'99 франков' ); // NaN — из-за пробела и нечисловых символов

// С помощью функций parseInt и parseFloat — мягкое, до первой ошибки
console.log( parseInt('99px') );    // 99 (ошибка на символе «p»)
console.log( parseInt(' 99px') );   // 99 (пробельные символы игнорируются)
console.log( parseFloat('99.3.4') ) // 99.3 (ошибка на второй точке)
console.log( parseInt('a123') );    // NaN (сразу ошибка)
console.log( parseInt('FF', 16) );  // 255 (указана Шестнадцатеричная система счисления)
```



## Проверка на «конечность» числа `isFinite()`

Приводит переданный аргумент к числу. Вернёт `true`, если это получилось и результат не `NaN` и не `Infinity`.

```js
console.log( isFinite(99) );       // true
console.log( isFinite('99') );     // true
console.log( isFinite('99 фр.') ); // false
console.log( isFinite(Infinity) ); // false
console.log( isFinite(NaN) );      // false
console.log( isFinite('NaN') );    // false
```



## Своя функция для проверки числа

Отсеивает всё, кроме чисел и строк, содержащих числа.

- Отсекает `Infinity/-Infinity/NaN` (они считаются числами).
- Отсекает `true/false/null` и пустую строку (они корректно преобразуются в числа).

```js
function isNumeric(n) {
  return !isNaN(parseFloat(n)) && isFinite(n);
}
```



### Округление

```js
console.log( Math.floor(3.1) ); // 3 (округление ВНИЗ)
console.log( Math.ceil(3.1) );  // 4 (округление ВВЕРХ)
console.log( Math.round(3.4) ); // 3 (округление до ближайшего целого)
console.log( Math.round(3.5) ); // 4 (округление до ближайшего целого)

// До заданной точности
var n = 3.456;
console.log( Math.round(n * 100) / 100 ); // 3.456 -> 345.6 -> 346 -> 3.46
```



### Неточности

```js
// 0.1 и 0.2 в двоичной системе счисления — это бесконечные дроби (хранятся с потерей точности).
var res1 = 0.1 + 0.2;
console.log( res1 ); // 0.30000000000000004
var res2 = 9999999999999999;
console.log( res2 ); // 10000000000000000

console.log( 6.35.toFixed(20) ); // 6.34999999999999964473

// Решение — округление методом toFixed() до 10-го символа после точки
console.log( +res1.toFixed(10) ); // 0.3000000000
console.log( +res2.toFixed(10) ); // 10000000000000000.0000000000
```
