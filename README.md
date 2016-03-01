Миксин который добавляет стиль ie

1. Вы каким либо способом вешаете к своему html классы ie и ie<номер версии>
  Мы привыкли это делать вот так:
    ```html
<!DOCTYPE html>
<!--[if (lt IE 7)|(IE 7) ]>    <html xmlns="http://www.w3.org/1999/xhtml" class="ie ie7"> <![endif]-->
<!--[if IE 8 ]>                <html xmlns="http://www.w3.org/1999/xhtml" class="ie ie8"> <![endif]-->
<!--[if IE 9 ]>                <html xmlns="http://www.w3.org/1999/xhtml" class="ie ie9"> <![endif]-->
<!--[if (gt IE 9)|!(IE)]><!--> <html xmlns="http://www.w3.org/1999/xhtml" class="test">   <!--<![endif]-->
```
2. Затем чтобы написать стили для ie в цсс мы пишем такое:
```css
/* этот стиль будет применён только к ие7 */
.ie7 .my-style {
  background: #008000;
}
```
3. Чтобы это не вызывало боли когда мы пишем stylus-код был сделан очень простой миксин
```stylus
ie(ieVer = '')
  select = selector();
  /.ie{ieVer} {select}
    {block}
```
4. Теперь в стилус-файле мы делаем вот так
```stylus
.my-style
  background-color: red
  +ie(7)
   background: yellow;
```
А на выходе получаем вот это:
```css
.my-style {
  background-color: #f00;
}
.ie7 .my-style {
  background: #ff0;
}
```


----
Велосипед подготовил Гуртовой Андрей <iyntx@ya.ru>
