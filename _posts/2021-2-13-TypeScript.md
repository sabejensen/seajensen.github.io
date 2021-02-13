---
layout: post
title: Typescript
---

Typescript adds types to Javascript. In practice, it forces your code to be cleaner based on what it allows. When you declare variables, it forces you to declare what type that variable is (boolean, string, number, etc). Though it can seem like a nuisance at times, it can be helpful and occasionally quite useful. Anecdotally in my own project, there was at least one time when it helped me remember to perform a toString and dodge an error, just because it forces you to consider the type of the variable you're working with. 

Compilers will take code and put it into one file that the machine can read. It's a way of streamlining and simplifying your output. A transpiler will output your code in a way that is universally readable, for instance converting Typescript into Javascript in the event that a browser can't understand Typescript.