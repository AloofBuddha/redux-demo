# Redux - A Step-by-Step Guide

# Contents
* [Intro](#intro)
  - [What is Redux?](#what-is-redux)
  - [A Little Philosophy](#a-little-philosophy)
  - [React + Redux vs Angular](#)
* [Redux](#redux)


# Intro

> This section is a bit of an excursion, so consider it optional. That said, it's valuable to consider the *how* and *why* of software design. The core ideas here are borrowed from the lecture [Simple Made Easy](https://www.infoq.com/presentations/Simple-Made-Easy) by Rich Hickey (the creator of Clojure) and it's well worth watching in addition to this intro. That said, if you just want to learn how to *use* `Redux, feel free to just [jump ahead!](#in-essence)

## What is Redux? 

According to it's creator Dan Abramov `Redux` is *a predictable state container for JavaScript apps*. That is an accurate, but a little terse, so we'll need to unpack that. But first - why are we even *talking about* `Redux`?

## A Little Philosophy

If you have heard of `Redux` before it was likely in the context of `React` - in fact the creator of `Redux` is one of the core team members at Facebook that created `React`! However, neither `React` nor `Redux` rely on one another - each library is an entirely independent tool that is useful on it's own. The reason for this is that `React` and `Redux` both follow what's known as the *UNIX philosophy*. 

The *UNIX philosophy* states that, instead of trying to solve a big problem all at once through 'monolithic design', we should break our problem down into manageable chunks and then *compose* these chunks together to solve the original problem! The *UNIX philosophy* encourages us to write programs that:

1) have a **Single Responsibility**. Our program solves a single, well-defined problem.

2) are **Modular** and **Composable**. Our program contains everything it needs to accomplish it's one task, but is open for composing with other tools, generally by passing the output of one tool as input to the second.

3) is ***Simple***! This isn't just a euphamism for easy - simple is the opposite of complex - i.e. our program should use some minimal, complete abstraction to solve the problem. If we find we are solving too much 'high level' of a problem, we may want to break our program down into smaller manageable pieces.

```
      inputs    ____________   output
        ------[            ]
        ------[ Monolithic ]---------
        ------[____________]


                    vs


  in1              out1 / in2               out2
 -----[ module 1 ]-------------[ module 2 ]------ ...            
```

## React + Redux vs Angular

> Warning - Polemical!

 `Angular` is a good example of the opposite of this approach - *monolithic design*. `Angular` attempts to provide a solution to the *entirety* of front-end web development, and is not a library but a framework - essentially a set of tools someone has already chosen and integrated for you. Frameworks promise an ***easy*** solution - it all just *works*, don't worry about *how*! The problem though is that, when your have some bug and it *doesn't* work, you may need to learn *how* it all works, and suddenly that hidden complexity is *your problem*!

 `React` and `Redux` on the other hand each solve a seperate problem (well) and can be composed together to solve the broader problems of front-end web development.



## In Essence

In summary - `React` and `Redux` are both small, simple tools that can work together to solve a broader problem, and this is *preferable* to all-in-one solutions like `Angular`. .

# Redux

So what is `Redux` for then? 

First - what is `React` for? `React` advertises itself as a tool for managing the view layer of your application. A front-end web app (really anything with a UI) has a *view* - i.e. the visual representation of our app. But the logic of our app doesn't live in the view, it lives in our code, and the view is likely to rely directly on data. When we talk about the 'state' of our app, we sometimes call this the *model* - i.e. the totality of data that represents the current state of your app.  

There are clearly at least two components at work here - the *view* and the *model*. In simple cases, like templating, this can be a 'one-way function'.


However, it's not as simple as simply 'binding' some given data to our view. The view may also respond to user-input. This means  may trigger an update to the *model*, triggering *further* updates to our *view*.

For example, this is how we would render a page using Nunjucks

***app.js***
```js
Movies.findAll()
  .then(function(movies) {
    res.render('index', movies);
  })
```

***index.html***
```html
<html>
  <body>
    <h1>Movies</h1>
    <ul id="movie-list">
    {% for movie in movies %}
    <li>{{ movie.title }}</li>
    {% endfor %}
    </ul>
  </html>
</body>
```

Here our model-view logic is straightforward

1) Redux as 'state manager' - counter

2) A more involved example - lists

3) The theory behind Redux

4) combineReducers - break up your logic

5) Middleware - logger

6) Redux + async 

7) integrating Redux and React

Extra?

Object.assign
Object spread syntax