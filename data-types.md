# Типы данных

- Элементарные
  - число
  - строка
  - логический тип
- Тривиальные
  - null
  - undefined
- Составные
  - массив
  - объект
- Специальные
  - функция

```js
// Число — число (целое, дробное), или Infinity, или NaN
var typeNumber = 1;
console.log(typeof typeNumber);
var typeNumberNan = NaN;
console.log(typeof typeNumberNan);
var typeNumberInf = 1 / 0; // Infinity
console.log(typeof typeNumberInf);

// Строка — символы в кавычках
var typeString = 'Однажды в суровую...';
console.log(typeof typeString);

// Логический тип — или true, или false
// Нужно для хранения значений правда/ложь
var typeBool = true;
console.log(typeof typeBool);

// Null (ссылка на несуществующий объект)
// Нужно для хранения значений «ничего» или «неизвестно»
var typeNull = null;
console.log(typeof typeNull); // object

// Массив
// Нужно для хранения значений списков переменных
var typeArray = ['яблоко', 'вишня', 'апельсин'];
console.log(typeof typeArray); // object

// Объект
// Нужно для хранения коллекций данных
var typeObj = { name: 'Виссарион', age: 67, role: 'Семейный диктатор'};
console.log(typeof typeObj); // object

// Функция
// Нужно для хранения действий (методов)
var typeFunc = function(){ console.log('это функция'); };
console.log(typeof typeFunc);
```
