---
title: "<picture>"
name: picture
author: ezhkov_d
summary:
  - картинка
  - ретина
  - retina
  - srcset
---

## Кратко

Тег `<picture>` используется, когда для разных устройств или вариантов отображения нам нужны разные картинки.

## Пример

```html
<picture>
  <source srcset="/some/url/to/image-320.jpg" media="(max-width: 800px)">
  <img src="/some/url/to/other-image-640.jpg" alt="" />
</picture>
```

## Как это понять

Одна и та же страница может быть открыта на разных устройствах и в окнах разной ширины. У телефона небольшой экран и бы круто не грузить полноразмерные фотки с большим разрешением. В CSS мы можем изменять фон элемента ([`background-image`](/css/doka/background-image)) в зависимости от ширины экрана, используя медиа-выражения. Но если изображение является контентным, то CSS нам уже не поможет. Мы должны использовать теги `<picture>` и [`<source>`](/html/doka/source)

## Как пишется

В общем случае внутри тега `<picture>` обязательно должен находиться тег [`<img>`](/html/doka/img), и опционально — теги [`<source>`](/html/doka/source).

```html
<picture>
  <source srcset="https://dummyimage.com/600x600/000/fff" media="(min-width: 600px)">
  <img src="https://dummyimage.com/320x320/000/fff" alt="">
</picture>
```
Браузер анализирует каждый тег [`<source>`](/html/doka/source), выбирает тот, который лучше всего подходит под текущие условия и отображает картинку из атрибута `src`. Если тег `<picture>` не поддерживается браузером или ни один из тегов [`<source>`](/html/doka/source) не подходит под условия, то отображается картинка из тега [`<img>`](/html/doka/img).

<p class="codepen" data-height="417" data-theme-id="light" data-default-tab="result" data-user="ezhkov" data-slug-hash="OJWdPqQ" style="height: 417px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="&amp;lt;picture&amp;gt;">
  <span>See the Pen <a href="https://codepen.io/ezhkov/pen/OJWdPqQ">
  &lt;picture&gt;</a> by Denis Ezhkov (<a href="https://codepen.io/ezhkov">@ezhkov</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>

В этом примере при помощи атрибута `media` в теге [`<source>`](/html/doka/source) мы задаём медиа-условие по аналогии с медиа-выражением `@media` в CSS. Если медиа-условие определяется как ложное, то элемент `<source>` пропускается.

## Подсказки

💡 Старайтесь при вёрстке всегда готовить несколько версий одной и той же картинки для отображения разных устройствах. Пользователи мобильных телефонов будут вам очень багодарны, если для них вы будете готовить картинки с меньшим разрешением. В то же время пользователям настольных ПК с экранами высокой чёткости можно показывать картинки с увеличенным разрешением:

<p class="codepen" data-height="265" data-theme-id="light" data-default-tab="html,result" data-user="ezhkov" data-slug-hash="XWpObbJ" style="height: 265px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="&amp;lt;picture&amp;gt; 2">
  <span>See the Pen <a href="https://codepen.io/ezhkov/pen/XWpObbJ">
  &lt;picture&gt; 2</a> by Denis Ezhkov (<a href="https://codepen.io/ezhkov">@ezhkov</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>

В этом примере пользователи с обычными экранами увидят картинку с надписью `768x400`. Пользователи, у которых retina-дисплеи, увидят надпись `1536x800`

<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

{% include "authors/ezhkov_d/author.njk" %}
