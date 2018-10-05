# Работа с DOM

`document` — глобальная переменная, содержащая структуру узлов, построенную из скачанного HTML.

## Поиск

```js
// Получить элемент по ID (вернёт 1 элемент)
var elem = document.getElementById('content');
elem.style.background = 'red';

// Получить элементы по тегу (вернёт коллекцию (объект, ведущий себя аналогично массиву))
var contentDivs = elem.getElementsByTagName('div');

// Получить элементы по атрибуту name (вернёт коллекцию, используется редко)
var ageElements = document.getElementsByName('age');

// Получить элементы по классу (вернёт коллекцию)
var articles = document.getElementsByClassName('article');

// Получить элементы, удовлетаоряющеие селектору
var li = document.querySelectorAll('ul > li:last-child');
for (var i = 0; i < li.length; i++) {
  console.log( li[i].innerHTML );
}

// Получить только первый удовлетворяющий селектору элемент
var firstOl = document.querySelector('ol');
```


## Создание и добавление узлов

```js
// Создаём узел
var p1 = document.createElement('p');
// Задаём внутри узла текст
p1.innerHTML = 'ПараграфЪ';
// Добавляем узел в конец body
document.body.appendChild(p1);

// Получим элемент с id
var div = document.getElementById('some-id');
// Добави узел p1 перед найденным элементом
document.body.insertBefore(p1, div);
```
