# HtmlMakeup

### Блочная верстка
Существуют различные способы верстки. 
Раньше распространенным способом верствки была верстка на основе таблиц. 
Таблицы позволяет разделить вcе пространство веб-страницы на строки и столбцы.
Минус табличной верстки в том, что она не гибкая.
На замену пришла блочная верстка.
Блочная верстка - это когда для разметки используется CSS-свойство float, а основным элементов является элемент <div>.
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
  
  
