# HtmlMakeup

### Блочная верстка
Существуют различные способы верстки. 
Раньше распространенным способом верствки была верстка на основе таблиц. 
Таблицы позволяет разделить вcе пространство веб-страницы на строки и столбцы.
Минус табличной верстки в том, что она не гибкая.
На замену пришла блочная верстка.
Блочная верстка - это когда для разметки используется CSS-свойство float, а основным элементов является элемент div.
В начале определим все блоки. 
```
body{
    margin:0;
    padding:0;
}
#header,
#main,
#footer{
    border: 1px solid #000;
    margin: 10px;
    height: 80px;
}
#main{
    height:600px;
}

```
```
<section id="header">header</section>
<div id="main">main</div>
<section id="footer">footer</section>


```  
 ### Эффект обтекания
 - Чтобы переместить блок сайдбара влево по отношению к блоку основного содержимого , нам надо указать свойство float: left и ширину.

```
...
#header{
    float:right;
    width:150px;
}
#main{
    margin-right: 160px;
}
...
```
  
 
### Вложенные (плавающие) блоки
- блок основного содержимого может включать блок собственно содержимого и блок меню
```
...
#one,
#two,
#three,
#four {
  border: 1px solid #000;
  margin: 10px;
  height: 80px;
}
...
```
```
...
<div id="main">
    main
    <section id="one">section one</section>
    <section id="two">section two</section>
    <section id="three">section three</section>
    <section id="four">section four</section>
  </div>
...
```
   
### Выравнивание столбцов по высоте
При блочной верстке можно столкнуться с проблемой высоты с столбцов, если плавающие блоки имеют определенный фон
-  решением проблемы является оборачивание в отдельный элемент, у которого устанавливается фон
```
...
 <div id="wrapper">
  <div id="main">
...
```
```
...
#wrapper {
  margin-right: 160px;
}
...

```
### Свойство display
Кроме свойства float, которое позволяет изменять позицию элемента, в CSS есть еще одно важное свойство - display. Оно позволяет управлять блоком элемента и также влиять на его позиционирование относительно соседних элементов.
Это свойство может принимать следующие значения:
 - inline: элемент становится строчным, подобно словам в строке текста
- block: элемент становится блочным, как параграф
- inline-block: элемент располагается как строка текста
- list-item: элемент позиционируется как элемент списка обычно с добавление маркера виде точки или порядкового номера
- run-in: тип блока элемента зависит от окружающих элементов
- flex: позволяет осуществлять гибкое позиционирование элментов
- table, inline-table: позволяет расположить элементы в виде таблицы
- none: элемент не виден и удален из разметки html
```
body,
#header,
#wrapper {
  margin: 0;
  padding: 0;
}

#main,
#footer,
#one,
#two,
#three,
#four {
  padding: 10px;
  height: 200px;
}
#main {
  background-color: #ddd;
}
#one,
#two,
#three,
#four {
  background-color: #eee;
  margin: 10px;
}
#footer {
  background-color: #ccc;
}
#main {
  height: 1000px;
}

#header {
  background-color: #d1c3c3;
  width: 200px;
  height: 100%;
  display: flex;
  position: fixed;
  right: 0;
}
#wrapper {
  margin-right: 200px;
}

```
```
<meta name="viewport" content="width=device-width">
<link rel="stylesheet" href="main2.css" />
<section id="header">header</section>
<div id="wrapper">
  <div id="main">
    main
    <section id="one">section one</section>
    <section id="two">section two</section>
    <section id="three">section three</section>
    <section id="four">section four</section>
  </div>
  <section id="footer">footer</section>
</div>

```
### Тестирование адаптивного дизайна
   - Google Chrome надо перейти в меню Дополнительные инструменты -> Инструменты разработчика


