# Null

Ссылка на несуществующий объект. Нужно для хранения значений «ничего» или «неизвестно».

Единственное возможное значение — `null`.

```js
var typeNull = null;
console.log( typeof typeNull ); // object
```



# Undefined

Имеет смысл «значение не присвоено». Единственное возможное значение этого типа — `undefined`.

Если функция ничего не возвращает, то она возвращает `undefined`.

```js
var typeUndef;
console.log( typeof typeUndef ); // undefined

var x;
if (typeof x === 'undefined') { // необходимо использовать идентичность, т.к. undefined == null
  // этот код выполнится
}

// Проверка с несозданной переменной
if (typeof y === 'undefined') { // не вызовет ошибку
  // этот код выполнится
}
if (y === 'undefined') {}      // Uncaught ReferenceError: y is not defined
```
