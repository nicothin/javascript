# Использование javascript

## В браузере

Подключается как отдельный файл(ы) или пишется в коде страницы.

```html
<!-- В коде страницы (выполняется сразу) -->
<script>
  alert('hello world');
</script>
```

```html
<!-- Как внешний файл -->
<!-- Когда браузер дойдёт до этой строки, он обязан скачать и выполнить файл и только потом разбирать последующий код разметки -->
<script src="js/vendors.js"></script>
<script src="js/script.js"><!-- Тут код НЕ СРАБОТАЕТ --></script>
```

```html
<!-- C атрибутом async -->
<!-- Браузер поставит скрипт в очередь загрузки и будет разбирать последующий код разметки -->
<!-- Как только js-файл загрузится, он выполнится, очерёдность подключения НЕ УЧИТЫВАЕТСЯ -->
<script src="js/async-script-01.js" async></script>
<script src="js/async-script-02.js" async></script>

<!-- C атрибутом defer -->
<!-- Браузер поставит скрипт в очередь загрузки и будет разбирать последующий код разметки -->
<!-- Как только js-файл загрузится, он выполнится, но очерёдность УЧИТЫВАЕТСЯ — defer-script-01.js всегда выполнится первым -->
<script src="js/defer-script-01.js" defer></script>
<script src="js/defer-script-02.js" defer></script>

<!-- async + defer -->
<!-- Будет воспринято так, словно есть только async (в IE9- — словно есть только defer) -->
<script src="js/paranoia.js" async defer></script>
```

```html
<!-- Чтобы добавить подключение внешнего файла с помощью JS: -->
<script>
  function addScript(src) {
    var script = document.createElement('script');
    script.src = src;
    // script.async = false; // если важен порядок выполнения
    document.head.appendChild(script);
  }
  addScript('js/additional-script-01.js');
  addScript('js/additional-script-02.js');
</script>
```



## Node.js

Программная платформа, превращающая JavaScript в язык общего назначения.

```bash
node script.js # вызов скриптового файла в терминале
```
