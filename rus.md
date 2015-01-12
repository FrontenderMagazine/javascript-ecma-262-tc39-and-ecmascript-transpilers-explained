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

ECMAScript — это стандарт, который развивает и поддерживает ассоциация ECMA
International. Он был принят Генеральной Ассамблеей ECMA в июне 1997.
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

The Ecma International Technical Committee 39 (aka TC39) is a committee of very
smart people, which is associated with a group of participants that are also
very smart. They get together for committee meetings approximately every two
months that are driven by pre-defined agendas.

TC39 is tasked with maintaining and updating the aforementioned ECMAScript
specification via a consensual process. This includes the language syntax,
semantics, and libraries and complementary technologies that support the
language.

This all happens via a process defined by TC39. It all starts with a feature
sketch that’s made for an ECMAScript specification enhancement or modification,
which often comes from developer community suggestions, or TC39 participants
themselves. If deemed worthy to pursue by the committee, the sketch is promoted
to an official proposal and one or more “champions” are assigned to it.

The life of the proposal from idea to published state then follows a series of
well-defined stages. These stages are numbered zero to four, and are in this
respective order: Strawman, Proposal, Draft, Candidate, and Finished. Advancing
to the next stage in all cases requires TC39 approval. If a proposal has made it
to stage 4, then you can expect to see it included in the next officially
published edition of the ECMA–262 standard specification, and ultimately in
environments that execute JavaScript. Refer to the referenced process document
for more information.

## Current ECMAScript Compatibility

ECMAScript 6 (aka ES.Next) is on its way to becoming mainstream and widely used
. Recall that the current version of ECMAScript is 5.1, with so-called “Harmony
” encompassing the upcoming 6 and 7 versions.

While many Harmony features are already implemented in modern browsers, and in
Node.js using the “harmony” flag, there are still other features that require a
compiler/transpiler to use (discussed shortly
).

Juriy “kangax” Zaytsev, author of the *Perfection Kills* blog, has created
and maintains an excellent set of ECMAScript compatibility tables. These tables
are organized by ECMAScript feature and indicate compatibility of that feature
for a given ECMAScript compiler, desktop browser (vendor and version), server
framework (e.g., Rhino, PhantomJS, Node.js), and iOS mobile operating system.

In addition to these tables, *MDN* often provides feature compatibility
tables for desktop and mobile browsers.

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