---
title: "sticky"
name: sticky
author: lenaryan
summary:
  - sticky
  - position
  - липкое позиционирование
---

## Кратко

`position: sticky` фиксирует блок на экране, когда этот блок находится на указанном расстоянии от края вьюпорта.

## Пример

Сделаем «липкий» заголовок, а также «липкий» блок в правом нижнем углу для каждого из `section`:

<p class="codepen" data-height="350" data-theme-id="light" data-default-tab="result" data-user="lenaryan" data-slug-hash="gOgNxoy" style="height: 350px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;" data-pen-title="Sticky Demo">
  <span>Посмотреть пен <a href="https://codepen.io/lenaryan/pen/gOgNxoy">
  Sticky Demo</a> на <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

## Как это понять

Блоки с «липким» позиционированием ведут себя, как `position: relative` и `position: fixed` одновременно. Пока блок не достиг указанного расстояния от края вьюпорта, он ведёт себя, как относительно спозиционированный. Когда блок достигнет этой точки, то станет вести себя, как будто мы указали `position: fixed`. А когда он встретится с противоположным краем родителя, то снова будет вести себя, как `position: relative`.

## Как пишется

```css
.block {
  position: sticky;
  top: 15px;
}
```

Для блока, который должен быть «липко» спозиционирован, указываем `position: sticky` и позицию относительно вьюпорта с нужным количеством пикселей. В данном примере блок «прилипнет» на расстоянии 15 пикселей от верхнего края вьюпорта.

## Подсказки

💡 с помощью такого позиционирования удобно делать закреплённую шапку — если она является непосредственным наследником `body`, то, указав шапке:

```css
.header {
  position: sticky;
  top: 0;
}
```

мы получим статичную шапку при загрузке экрана, а при скролле страницы — зафиксированную сверху.

## В работе

🛠 если нужный элемент занимает всю высоту родительского блока (если он один в блоке или просто самый высокий среди соседних элементов), то `position: sticky` не сработает;

🛠 не поддерживается в IE11;

🛠 при вертикальном скролле работают только свойства `top` и `bottom`, про горизонтальном - `left` и `right`;

🛠 `position: sticky` можно указать внутри родителя с `overflow: scroll` или `overflow: auto`.

{% include "authors/lenaryan/author.njk" %}
