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
