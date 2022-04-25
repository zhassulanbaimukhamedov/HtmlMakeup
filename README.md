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
  <style>
    div{
        margin:10px;
        border:1px solid black;
        font-size:20px;
        height:80px;
    }
    #header{
        background-color: #CCC;
    }
    #sidebar{
        background-color: #DDD;
    }
    #main{
        background-color: #EEE;
        height: 200px;
    }
    #footer{
        background-color: #CCC;
    }
</style>
<div id="header">Header</div>
<div id="sidebar">Sidebar</div>
<div id="main">Main content</div>
<div id="footer">Footer</div>

```  
 ### Эффект обтекания
 - Чтобы переместить блок сайдбара влево по отношению к блоку основного содержимого , нам надо указать свойство float: left и ширину.

```
#sidebar{
        background-color: #DDD;
        /* float: left; */
        float: right;
        width: 150px;
    }
    #main{
        background-color: #EEE;
        height: 200px;
        /* margin-left: 170px; */
        margin-right: 170px;
    }
```
  
### Более сложная структура
```
#leftsidebar{
        background-color: #DDD;
        float: left;
        width: 150px;
    }
    #rightsidebar{
        background-color: #BBB;
        float: right;
        width:150px;
    }
    #main{
        background-color: #EEE;
        height: 200px;
        margin-left: 170px;
        margin-right: 170px;
    }
```

### Вложенные (плавающие) блоки
- блок основного содержимого может включать блок собственно содержимого и блок меню
```
#sidebar{
        background-color: #BBB;
        float: right;
        width:150px;
    }
    #main{
        background-color: #EEE;
        height: 200px;
        margin-right: 170px;
    }
    #menu{
        background-color: #DDD;
    }
    #content{
        background-color: #EEE;
    }
```
```
<div id="sidebar">RightSidebar</div>
<div id="main">
    <div id="menu">Menu</div>
    <div id="content">Content</div>
</div>
```

### Применим обтекание к блоку меню
```
#main{
        background-color: #EEE;
        height: 200px;
        margin-right: 170px;
    }
    #menu{
        background-color: #DDD;
        float: left;
        width: 160px;
    }
```
 - Аналогично можно сделать блок меню справа:
```
#menu{
        background-color: #DDD;
        float: right;
        width: 160px;
    }
    #content{
        background-color: #EEE;
        margin-right: 180px;
    }
```
### Выравнивание столбцов по высоте
При блочной верстке можно столкнуться с проблемой высоты с столбцов, если плавающие блоки имеют определенный фон
```
<style>
  body,
  h2,
  p {
    margin: 0;
    padding: 0;
  }
  body {
    font-size: 18px;
  }
  #header {
    background-color: #EEE;
    border-bottom: 1px solid #CCC;
    height: 80px;
  }
  #menu{
      background-color: #DDD;
      float: left;
      width:150px;
  }
  #main{
      background-color: #F7F7F7;
      border-left: 1px solid #CCC;
      margin-left: 150px;
      padding: 10px;
  }
  #footer{
      border-top:1px solid #CCC;
      background-color: #DEDEDE;
  }
</style>
<div id="header">
  <h2>MySyte.com</h2>
</div>
<div id="menu">
  <ul>
    <li><a href="#">Main</a></li>
    <li><a href="#">Blog</a></li>
    <li><a href="#">Contacts</a></li>
    <li><a href="#">About</a></li>
  </ul>
</div>
<div id="main">
  <h2>Lorem ipsum dolor</h2>
  <p>
    Lorem ipsum dolor sit amet consectetur adipisicing elit. Quibusdam eos error
    commodi nihil provident similique, beatae excepturi doloribus quas ipsum
    fugiat ipsa modi molestias placeat cumque, ex, aperiam eaque et?
    Lorem ipsum dolor sit amet consectetur adipisicing elit. Quibusdam eos error
    commodi nihil provident similique, beatae excepturi doloribus quas ipsum
    fugiat ipsa modi molestias placeat cumque, ex, aperiam eaque et?
    Lorem ipsum dolor sit amet consectetur adipisicing elit. Quibusdam eos error
    commodi nihil provident similique, beatae excepturi doloribus quas ipsum
    fugiat ipsa modi molestias placeat cumque, ex, aperiam eaque et?
  </p>
</div>
<div id="footer">Copyright &copy; MySite.com, 2022</div>

```
-  решением проблемы является оборачивание в отдельный элемент, у которого устанавливается фон
```
#wrapper{
    background-color: #ddd;
  }
  #menu {
    float: left;
    width: 150px;
  }
```
```
<div id="wrapper">
  <div id="main">
  ...
```
 
