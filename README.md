
# Миксин который добавляет стили для ie онли

**1. Вы каким либо способом вешаете к своему тегу html классы ie и ie<номер версии>**

Мы привыкли это делать вот так:
```html
<!DOCTYPE html>
<!--[if (lt IE 7)|(IE 7) ]>    <html xmlns="http://www.w3.org/1999/xhtml" class="ie ie7"> <![endif]-->
<!--[if IE 8 ]>                <html xmlns="http://www.w3.org/1999/xhtml" class="ie ie8"> <![endif]-->
<!--[if IE 9 ]>                <html xmlns="http://www.w3.org/1999/xhtml" class="ie ie9"> <![endif]-->
<!--[if (gt IE 9)|!(IE)]><!--> <html xmlns="http://www.w3.org/1999/xhtml"> <!--<![endif]-->
```
**2. Затем чтобы написать стили для ie в цсс мы делали вот так:**
```css
/* этот стиль будет применён только к ие7 */
.ie7 .my-style {
  background: yellow;
}
```
**3. Чтобы это не вызывало боли, когда мы пишем stylus-код, был сделан очень простой миксин**
```stylus
ie(ieVer = '')
  /.ie{ieVer}
    {selector()}
      {block}
```
**4. Теперь в stylus-файле мы делаем вот так**
```styl
.my-style
  background-color red
  +ie(7)
    background yellow
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
Велосипед подготовил [Гуртовой Андрей](https://github.com/jt3k)

