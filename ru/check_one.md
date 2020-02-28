---
$title: Создайте свою страницу AMP HTML
$order: 1
description: Использовать HTTPS: при создании страниц и контента AMP вам следует строго рассмотреть использование протокола HTTPS (по сравнению с HTTP). Хотя HTTPS не требуется для самого документа AMP или ...
author: pbakaus
contributors:
- bpaduch
---

Следующая разметка - достойная отправная точка или шаблон. Скопируйте его и сохраните в файл с расширением .html.

[исходный код: html] <! doctype html>

        <meta charset="utf-8">     <script async="" src="https://cdn.ampproject.org/v0.js"></script>     <title>Hello, AMPs</title>     <link rel="canonical" href="%7B%7Bdoc.url%7D%7D">     <meta name="viewport" content="width=device-width,minimum-scale=1,initial-scale=1">     <script type="application/ld+json">       {         "@context": "http://schema.org",         "@type": "NewsArticle",         "headline": "Open-source framework for publishing content",         "datePublished": "2015-10-07T12:02:41Z",         "image": [           "logo.jpg"         ]       }     </script>     <style amp-boilerplate="">body{-webkit-animation:-amp-start 8s steps(1,end) 0s 1 normal both;-moz-animation:-amp-start 8s steps(1,end) 0s 1 normal both;-ms-animation:-amp-start 8s steps(1,end) 0s 1 normal both;animation:-amp-start 8s steps(1,end) 0s 1 normal both}@-webkit-keyframes -amp-start{from{visibility:hidden}to{visibility:visible}}@-moz-keyframes -amp-start{from{visibility:hidden}to{visibility:visible}}@-ms-keyframes -amp-start{from{visibility:hidden}to{visibility:visible}}@-o-keyframes -amp-start{from{visibility:hidden}to{visibility:visible}}@keyframes -amp-start{from{visibility:hidden}to{visibility:visible}}</style><noscript><style amp-boilerplate="">body{-webkit-animation:none;-moz-animation:none;-ms-animation:none;animation:none}</style></noscript>           <h1>Welcome to the mobile web</h1>     [/sourcecode]

Пока что содержание в теле довольно простое. Но в заголовке страницы много дополнительного кода, который может быть неочевидным. Давайте деконструируем необходимую наценку.

Использовать HTTPS: при создании страниц и контента AMP вам следует строго рассмотреть использование протокола HTTPS (по сравнению с HTTP). Хотя HTTPS не требуется для самого документа AMP или для изображений и шрифтов, существует множество функций AMP, для которых требуется HTTPS (например, видео, кадры и т. Д.). Чтобы ваши AMP-страницы в полной мере использовали все функции AMP, используйте протокол HTTPS. Вы можете узнать больше о HTTPS в разделе [«Почему HTTPS имеет значение»](https://developers.google.com/web/fundamentals/security/encrypt-in-transit/why-https) .

[tip type = "tip"] Используйте [генератор AMP Boilerplate Generator,](/boilerplate) чтобы быстро приступить к созданию новых страниц AMP. [/чаевые]

## Требуется наценка

Документы AMP HTML ДОЛЖНЫ:

правило | Описание
--- | ---
Начните с `<!doctype html>` doctype. | Стандарт для HTML.
Содержит тег `<html ⚡>` верхнего уровня <br> ( `<html amp>` принимается). | Определяет страницу как содержимое AMP.
Содержат теги `<head>` и `<body>` . | Необязательно в HTML, но не в AMP.
Содержат `<meta charset="utf-8">` как первый дочерний элемент их `<head>` . | Определяет кодировку для страницы.
Содержат `<script async src="https://cdn.ampproject.org/v0.js"></script>` внутри тега `<head>` . Рекомендуется включать скрипт как можно раньше в `<head>` . | Включает и загружает библиотеку AMP JS.
Содержат `<link rel="canonical" href="$SOME_URL">` внутри их `<head>` . | Указывает на обычную HTML-версию документа AMP HTML или на себя, если такой HTML-версии не существует. Узнайте больше в разделе « [Сделайте свою страницу доступной для обнаружения»](../../../../documentation/guides-and-tutorials/optimize-measure/discovery.md) .
Содержат `<meta name="viewport" content="width=device-width,minimum-scale=1">` внутри тега `<head>` . Также рекомендуется включить `initial-scale=1` . | Определяет отзывчивый видовой экран. Узнайте больше на [странице Создание отзывчивых страниц AMP](../../../../documentation/guides-and-tutorials/develop/style_and_layout/responsive_design.md) .
Содержат [шаблонный код AMP](../../../../documentation/guides-and-tutorials/learn/spec/amp-boilerplate.md) в `<head>` . | Шаблон CSS для первоначального скрытия содержимого до загрузки AMP JS.

## Необязательные метаданные

В дополнение к голым требованиям, наш образец также включает в себя определение Schema.org в заголовке, которое не является строгим требованием для AMP, но это требование для распространения вашего контента в определенных местах (например, в Google Поиск топ истории карусели).

[tip type = "read-on"] Посетите эти ресурсы, чтобы узнать больше:

- [Начало работы с AMP в Поиске Google](https://developers.google.com/amp/docs) - научитесь готовить страницы AMP для Поиска в Google.
- [Образцы метаданных](https://github.com/ampproject/amphtml/tree/master/examples/metadata-examples) - узнайте больше обо всех метаданных, которые вам понадобятся в других местах (например, в Twitter). [/чаевые]

<hr>

Хорошие новости! Это все, что нам нужно для создания нашей первой страницы AMP, но, конечно, в теле пока что не так много всего происходит. В следующем разделе мы рассмотрим, как добавить основы, такие как изображения, пользовательские элементы AMP, как оформить страницу и разработать адаптивный макет.
