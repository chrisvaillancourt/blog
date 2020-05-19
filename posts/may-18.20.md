---
title: 100 Days of Code - Day 6
description: Day 6!
date: 2020-05-12
tags: 
  - 100DaysOfCode
layout: layouts/post.njk
---

### Day 5: May 16, 2020

#### Today's Progress

Today I scratched the surface of monads in [Functional-Light JavaScript](https://frontendmasters.com/courses/functional-javascript-v3).

#### Thoughts

Yesterday was the first day I failed to code and tweet my progress. I still coded but need to work on staying consistent, even if the progress is slow and steady.

I really like the core principles of functional programming and I'm excited to use them more in my day-to-day. Monads are still relatively abstract so I'm hoping to see examples of when they are a good option to use. 

#### Work examples

##### Monads

Monads are a functional programming data structure. In formal terms, a monad is a pattern for pairing data with a set of predictable behaviors that let it interact with other data+ behavior pairings (monads).

Monads utility comes from being able to work with a specific data value in a manner that has predictable behavior.

A basic monad example is the `Just` monad:

```js
function Just(val){
  return { map, chain, ap }; // three core methods on all monads

  // makes another monad (like a regular array map function)
  // makes the same kind of monad -- like array maps make arrays
  function map(fn){
    return Just( fn( val ) );
  }
  // aka: bind, flatMap
  // like mapping a monad, getting a monad, and then
  // flattening the value from the monad.
  function chain(fn){
    return fn( val );
  }
  // implies our value has to be a function in order to use this
  function ap(anotherMonad){
    return anotherMonad.map( val );
  }
}
```