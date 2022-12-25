---
title: "В GitHub добавили поддержку диаграмм Mermaid"
share: true
categories:
  - posts
tags:
  - github
  - mermaid
---

В GitHub [появилась](https://github.blog/2022-02-14-include-diagrams-markdown-files-mermaid/) возможность добавлять в md-файлы динамические диаграммы с помощью генератора [Mermaid](https://github.com/mermaid-js/mermaid#readme). До этого диаграммы вставлялись в виде изображений или «рисовались» с помощью символов из ASCII-таблицы. Теперь же полноценную поддержку схем добавили в синтаксис разметки Markdown.

![github.blog](https://github.blog/wp-content/uploads/2022/02/mvp2.png?resize=1200%2C630 "mermaid")

Mermaid — инструмент для построения диаграмм и графиков, основанный на JavaScript. С его помощью можно динамически создавать блок-схемы, UML-диаграммы, графики коммитов и диаграммы Ганта. Команда GitHub объединилась с разработчиками из CommonMark и добавила нативную поддержку синтаксиса Mermaid на платформу. 

Каждый раз, когда в md-файле встречается блок кода, отмеченный как mermaid, система создает новый фрейм iframe, берет необработанный код из блока, передает его в Mermaid.js и превращает код в диаграмму. Все это происходит локально в браузере пользователя.

Следующий блок кода срендерится в полноценную диаграмму, содержимое которой можно будет динамически менять:

```
sequenceDiagram
Alice->>John: Hello John, how are you?
loop Healthcheck
    John->>John: Fight against hypochondria
end
Note right of John: Rational thoughts!
John-->>Alice: Great!
John->>Bob: How about you?
Bob-->>John: Jolly good!
```

<pre class="mermaid">
sequenceDiagram
Alice->>John: Hello John, how are you?
loop Healthcheck
    John->>John: Fight against hypochondria
end
Note right of John: Rational thoughts!
John-->>Alice: Great!
John->>Bob: How about you?
Bob-->>John: Jolly good!
</pre>

Заключение диаграммы в тег iframe позволяет правильно срендерить страницу и не нарушить содержимое файла, а асинхронный ренедеринг упрощает вывод нескольких диаграмм одновременно.
