# Разъяснения насчёт JavaScript, ECMA–262, TC39 и транскомпиляторов ECMAScript

## Введение

Что такое JavaScript? На этот вопрос есть множество верных ответов, но я думаю,
что самым современным, кратким и точным ответом будет такой: JavaScript — это
реализация спецификации ECMAScript.

JavaScript схож с HTML и CSS тем, что все они — реализации очень хорошо
определённых спецификаций. Держу пари, что лучший способ понять что-то и стать
в этой области экспертом — полностью прочесть и понять спецификацию, на
которой это что-то основывается. Именно это побудило меня написать эту статью.

## Так что же такое, ECMAScript?

ECMAScript — это стандарт, который развивает и поддерживает ассоциация Ecma
International. Он был принят Генеральной Ассамблеей Ecma в июне 1997.
А если точнее, ECMAScript — это стандарт ECMA-262, который называется
«Спецификация языка ECMAScript», и у которого было несколько редакций.
На настоящий момент актуальна редакция 5.1, она была принята
Генеральной Ассамблеей и опубликована в июне 2011. Стандарт создавался на основе
оригинальной версии JavaScript Брендана Айха из Netscape и интерпретатора
JScript от Microsoft, но с тех пор значительно развился.

Как уже упоминалось, JavaScript — это реализация спецификации ECMAScript.
Это означает, что по мере того, как у спецификации появляются новые черновики
или опубликованные редакции, разработчики браузеров и фреймворков вроде Node.js
должны последовательно внедрять новые фичи. Для этого вносятся изменения в
движки, которые эти браузеры и фреймворки используют для интерпретирования и
выполнения кода на JavaScript.

Зачем нужна спецификация? В различных браузерах используются различные движки
JavaScript, например, V8 в Chrome, SpiderMonkey в Firefox, и так далее.
Когда вы пишете на JavaScript, вы ожидаете, что все движки во всех окружениях
будут разбирать и выполнять ваш код абсолютно одинаково. Без стандартизованной
спецификации любой из этих движков был бы волен исполнять JavaScript как ему
вздумается, а это, очевидно, не очень хорошо.

## Откуда взялась cпецификация ECMA-262?

Ecma International Technical Committee 39 (он же TC39) — комитет очень умных
людей, он связан с группой участников, которые в свою очередь тоже очень
умны. Они собираются вместе на встречах комитета приблизительно каждые два
месяца и обсужают заранее подготовленные списки вопросов.

Задачей TC39 является поддержка и обновление упомянутой ранее спецификации
ECMAScript, после обсуждения и всеобщего согласия. Сюда относятся синтаксис
языка, семантика, библиотеки и сопутствующие технологии, на которых основывается
язык.

Этот процесс определён TC39. Всё начинается с наброска функционала, расширяющего
или изменяющего спецификацию. Такие наброски часто исходят из предложений
сообществ разработчиков, или же от самих участников TC39. Если предложение
оказывается стоящим, набросок получает статус официального предложения, и
за него становятся отвественными один или несколько «чемпионов».

Затем на своём пути от идеи до публикации предложение проходит ряд определённых
стадий. Эти стадии пронумерованы от нуля до четырёх: Чучело, Предложение,
Черновик, Кандидат и Завершено. Переход на любую следующую стадию требует
одобрения TC39. Если предложение добралось до стадии 4, можно ожидать, что его
включат в следующую официально опубликованную редакцию спецификации стандарта
ECMA-262, и в итоге оно появится в окружении, которое выполняет JavaScript.
Больше об этом процессе вы можете узнать на сайте Ecma.

## Совместимность с текущей редакцией ECMAScript

ECMAScript 6 (он же ES.Next) уже джижется по направлению к повсеместному
применению. Напомню, текущая версия ECMAScript — 5.1, а так называемая
«Harmony» включает в себя возможности из предстоящих 6 и 7 версий.

Хотя множество возможностей, которые предоставляет Harmony, уже есть в
современных браузерах и Node.js с флагом `--harmony`, есть другие фичи, которые
требуют компилятора/транскомпилятора (мы вернёмся к этой теме).

Юрий «kagnax» Зайцев, автор блога *Perfection Kills*, создал и поддерживает
отличный набор сводных таблиц по совместимости ECMAScript. При помощи этих
таблиц можно выбрать фичу ECMAScript и узнать, насколько с ней совместимы
компиляторы, десктопный браузеры (разных версий), серверные фреймворки (Rhino,
PhantomJS, Node.js) и операционная система iOS.

В дополнение тем таблицам, на *MDN* часто можно найти таблицы совестимости для
десктопных и мобильных браузеров.

## Can I Use Upcoming ECMAScript Features Now?

Yes you can. Some of these features are already implemented in certain browsers
and Node, but many require the use of a third-party ECMAScript transpiler. These
transpiler’s are sometimes also referred to as a compiler. Technically there is
a difference between a transpiler and a traditional compiler.

Regarding ECMAScript transpilers, the input language is an upcoming version of
the language specification (e.g., EC 6), which is then compiled to a prior, more
stable and widely compatible version of the same specification (e.g., EC 5.1).
For the remainder of this article we will simply refer to them as transpilers.

There are plenty of resources online about writing Harmony code today, and
specific transpilers, including what they can be used for. Refer to the list at
the end of this article for some resources worth checking out.

## Should I Use Upcoming ECMAScript Features Now?

The answer really depends on if you’re talking about learning and playing
around with upcoming language features, or actually employing a transpiler and/
or these features in production.

In the latter case, I would say it really depends, the most important
considerations being what stage in the process the feature proposal is in, and
how widely supported it is in JavaScript execution environments. If it’s already
supported across all environments that your code will run, then it’s probably a
safe bet to go for it, and you wouldn't even need a transpiler in this case.

The more mature and advanced in the process the feature is, the more likely it
is to remain the same in the final published specification. Many of these
features however (EC7, strawman, etc.), are still in early stages of the process
and may be changed or removed from the final specification. In these cases, it
may not be a good idea to use features that may not be in the final
specification, or are subject to major changes before publication.

In the former case, I think it’s a great idea to use a transpiler to get
ahead of the game. People often talk about keeping their skills up to date on
the latest technologies, and for good reason given how fast these things change.
Learning upcoming ECMAScript features takes this to a whole new level, in that
you're not learning something retroactively and reactively, but before it’s
officially released. This is a much more proactive approach to professional
development, and opportunities like this are few and far between.

Remember that these features are being added to the language for reasons
approved by the smart TC39 participants, which includes improving things like
language quality, abstraction, usability, etc. Learning these features in
advance will allow you to be up and running without delay once these new changes
are officially published and widely supported. You can also position yourself as
a JavaScript expert in your organization, who is able to identify new language
features that can offer code and product improvements.

## Summary

JavaScript is an amazing, powerful, and ubiquitous programming language. To
become a true JavaScript expert, I highly recommend reading the ECMA–262
specification on which it’s based. It’s also important to understand where the
specification comes from, how it’s maintained, and what processes are used to
evolve the language. Lastly, understanding what transpilers are and how they're
used can certainly help you get ahead of the game. Who knows, maybe you or I can
be a TC39 member someday.

**About the Author**: [Alex Castrounis][innoarchitech] founded InnoArchiTech. To learn more
about him and InnoArchiTech, visit[innoarchitech.com][innoarchitech]. Sign up for the
InnoArchiTech [newsletter][newsletter] for the latest content updates, and you can follow
InnoArchiTech on Twitter at[@innoarchitech][twitter].

 [innoarchitech]: http://innoarchitech.com/about/?utm_source=medium&utm_medium=post&utm_content=aboutlink&utm_campaign=republish
 [newsletter]: http://innoarchitech.com/newsletter/?utm_source=medium&utm_medium=post&utm_content=aboutlink&utm_campaign=republish
 [twitter]: https://twitter.com/innoarchitech