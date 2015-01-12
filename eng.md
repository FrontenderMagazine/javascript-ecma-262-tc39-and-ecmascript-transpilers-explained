<figure name="fd5d" class="graf--figure">![][1]</figure>

Originally published at innoarchitech.com [here][2] on November 8, 2014.

What is JavaScript? There are many correct answers to this question, but I
think the most modern, succinct, and accurate answer is that JavaScript is the 
implementation of the ECMAScript specification.

JavaScript is similar to HTML and CSS in that they are all implementations of a
very well-defined specification. I would argue that the best way to understand 
and become an expert in something is to fully read and understand the 
specification in which that something is based. This is what motivated me to 
write this article.

ECMAScript is a standard that is facilitated and maintained by the ECMA
International association, and was initially adopted by the Ecma General 
Assembly (EGA) in June 1997. More specifically, ECMAScript is actually the ECMA–
262 standard and is entitled the ‘ECMAScript Language Specification’, which is 
published in editions. The current edition is ECMA–262 Edition 5.1, and was 
adopted by the EGA and published in June 2011. The standard is based on Brenden 
Eich’s original JavaScript version from Netscape, and Microsoft’s JScript, but 
has evolved significantly from these early technologies.

As mentioned, JavaScript is the implementation of the ECMAScript specification
. This means that whenever new editions of the specification are in a draft or 
published state, browser vendors and frameworks like Node.js should 
progressively implement the new specification’s features. This is done through 
modifications to the engines used by these browsers and frameworks to interpret 
and execute JavaScript code.

So why do we need a specification? Different browser vendors employ different
JavaScript engines, i.e., V8 for Chrome, SpiderMonkey for Firefox, and so on. 
When you write JavaScript, you expect the engine that parses and executes your 
code to do it exactly the same way in all environments. Without a standardized 
specification, these engines would be free to execute JavaScript according to 
any interpretation of how JavaScript should work, which would obviously not work
out very well.

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

In addition to these tables, \*MDN\* often provides feature compatibility
tables for desktop and mobile browsers.

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

JavaScript is an amazing, powerful, and ubiquitous programming language. To
become a true JavaScript expert, I highly recommend reading the ECMA–262 
specification on which it’s based. It’s also important to understand where the 
specification comes from, how it’s maintained, and what processes are used to 
evolve the language. Lastly, understanding what transpilers are and how they're 
used can certainly help you get ahead of the game. Who knows, maybe you or I can
be a TC39 member someday.

**About the Author**: [Alex Castrounis][3] founded InnoArchiTech. To learn more
about him and InnoArchiTech, visit[innoarchitech.com][3]. Sign up for the
InnoArchiTech[newsletter][4] for the latest content updates, and you can follow
InnoArchiTech on Twitter at[@innoarchitech][5].

 [1]: img/1*n9YZ0LPmqB6_JrqIsE3Uqw.png

 [2]: http://innoarchitech.com/javascript-ecma262-tc39-ecmascript-transpilers-explained/?utm_source=medium&utm_medium=post&utm_content=originallink&utm_campaign=republish

 [3]: http://innoarchitech.com/about/?utm_source=medium&utm_medium=post&utm_content=aboutlink&utm_campaign=republish

 [4]: http://innoarchitech.com/newsletter/?utm_source=medium&utm_medium=post&utm_content=aboutlink&utm_campaign=republish
 [5]: https://twitter.com/innoarchitech