# Порядок инициализации на примере работы JS в браузере

## 1. Подготовка к запуску

- Поиск в скрипте Function Declaration и создание этих функций.
- Поиск в скрипте `var` и создание соответствующих переменных со значением `undefined` (подъем переменных).

## 2. Выполнение скрипта

Реальное построчное выполнение. Присвоение значений переменных (оператор `=`) происходит тогда, когда выполнение доходит до строки с присвоением.

## Пример

```js
console.log([window.funcDecl, window.num, window.funcExpress]);
// Начало: функция funcDecl и переменные УЖЕ есть
// [function funcDecl() {...}, undefined, undefined]

var num = 99;
console.log([window.funcDecl, window.num, window.funcExpress]);
// Присвоили значение переменной num, теперь она не undefined
// [function funcDecl() {...}, 99, undefined]

function funcDecl() { alert('a'); };
console.log([window.funcDecl, window.num, window.funcExpress]);
// Функция funcDecl() уже существовала, никаких изменений
// [function funcDecl() {...}, 99, undefined]

var funcExpess = function() { alert('b'); };
console.log([window.funcDecl, window.num, window.funcExpress]);
// В переменную funcExpess записано значение (это функция)
// [function funcDecl() {...}, 99, function() {...}]
```



## Function Declaration и Function Expression

### Function Declaration

Такая функция создаётся на этапе подготовки к запуску, поэтому доступна для вызова до того, как написана.

```js
function sayHi(user) {
  console.log( "Hi, " + user );
};
```

### Function Expression

Такая функция добавляется только в момент срабатывания оператора присваивания (`=`).

```js
var sayHi = function(user) {
  console.log( "Hi, " + user );
};
```
