# Операторы сравнения

Возвращают логическое значение (`true/false`). Используются в условиях, циклах и других конструкциях.

```js
var varStr0  = '1';
var varNum  = 1;
var varNaN  = NaN;
var varNull = null;
var varUnd  = undefined;
var varBool = true;

// Равенство (приводит типы данных)
console.log( varStr0 == varNum );  // true, т.к. при сравнении строки и числа строка приведется к числу
console.log( varNull == varUnd );  // true, т.к. null == undefined
console.log( varStr0 == varBool ); // true, т.к. true преобразуется в 1 (false преобразовался бы в 0)
console.log( varNaN == NaN );      // false, т.к. NaN не равен ничему, в т.ч. самому себе

// Неравенство
console.log( varStr0 != varNum );  // false, т.к. при сравнении строки и числа строка приведется к числу
console.log( varNull != varUnd );  // false, т.к. null == undefined
console.log( varStr0 != varBool ); // false, т.к. true преобразуется в 1 (false преоразовался бы в 0)

// Идентичность (НЕ приводит типы данных)
console.log( varNum === 1 );        // true
console.log( varBool === true );    // true
console.log( varStr0 === varNum );  // false
console.log( varNull === varUnd );  // false
console.log( varStr0 === varBool ); // false

// Неидентичность
console.log( varNum !== 1 );        // false
console.log( varBool !== true );    // false
console.log( varStr0 !== varNum );  // true
console.log( varNull !== varUnd );  // true
console.log( varStr0 !== varBool ); // true

// Сравнение
console.log( varNum < 1 );   // false
console.log( varNum > 1 );   // false
console.log( varNum <= 1 );  // true
console.log( varNum >= 1 );  // true
console.log( varStr0 <= 1 ); // true, т.к. строка приведена к числу
console.log( varStr0 >= 1 ); // true, т.к. строка приведена к числу

// Сравнение строк
var varStr1  = 'a';
var varStr2  = '2';
console.log( varStr1 > 'A' );    // true, т.к. в Unicode у символа «a» код 0061, а у символа «A» код 0041
console.log( varStr1 > 'aa' );   // false, т.к. строка «aa» длиннее
console.log( varStr2 > '14' );   // true, т.к. сравнивались символы в строках
console.log( +varStr2 > +'14' ); // false, т.к. унарный плюс привел оба элемента сравнения к числу

// Сравнение с null
console.log( varNull > 0 );  // false, т.к. null приводится к нулю
console.log( varNull < 0 );  // false, т.к. null приводится к нулю
console.log( varNull <= 0 ); // true, т.к. null приводится к нулю
console.log( varNull >= 0 ); // true, т.к. null приводится к нулю
console.log( varNull == 0 ); // false, т.к. работает иначе: null и undefined равны друг другу, но не равны чему-либо ещё

// Сравнение с undefined
console.log( varUnd > 0 );  // false, т.к. undefined, приведённый к числу, даёт NaN
console.log( varUnd < 0 );  // false, т.к. undefined, приведённый к числу, даёт NaN
console.log( varUnd == 0 ); // false, т.к. undefined, приведённый к числу, даёт NaN
```
