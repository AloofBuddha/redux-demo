# Redux - Step-by-Step

## Intro

### What is `Redux`? 

[asd](/#)

According to it's creator 
> *`Redux` is a predictable state container for JavaScript apps* 

That is an accurate definition, but a little terse, so we'll need to unpack it ourselves. But first - why are we even *talking about* `Redux`?

### A Little Philosophy

> This section is a bit of an excursion, so consider it optional. That said, it's valuable sometimes to consider the 'how' and 'why' of software design!

If you have heard of `Redux` before it was likely in the context of `React` - in fact the creator of `Redux` is one of the core team members at Facebook that created `React`! However, neither `React` nor `Redux` rely on one another - each library is an entirely independent tool that is useful on it's own. The reason for this is that `React` and `Redux` both follow what's known as the *UNIX philosophy*. The *UNIX philosophy* states that, instead of trying to solve a big problem through 'monolithic design', we should break our problem down into pieces - creating concise, clear, modular and (most of all) ***simple*** programs - and then *compose* these pieces together. 

> ***Warning - Polemic!***

`Angular` is a good example of the opposite of this approach - *monolithic design*. `Angular` attempts to provide a solution to the *entirety* of front-end web development, and is not a library but a framework - essentially a set of tools someone has already chosen and integrated for you - 

and promises an ***easy*** solution - it all just *works*, don't worry about *how*! This turns out to be an astoundingly bad idea however. Programmers need to understand their code intimately in order to reason about performance or track down a bug. Frameworks / monolithic design / 'easy' solution tend to get you started a lot faster, but at the price of hiding the complex bits. The problem is that, when your have a bug you can't understand, and your stack trace points you to `angular.min.js : line 45221` suddenly some piece of that complexity is necessary to move forward!


1) Redux as 'state manager' - counter

2) A more involved example - lists

3) The theory behind Redux

4) combineReducers - break up your logic

5) Middleware - logger

6) Redux + async 

7) integrating Redux and React