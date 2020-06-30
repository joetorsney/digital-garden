---
title: "Long Code"
date: 2020-05-24T11:54:16+01:00
description: ""
---

> _Society grows great when old men plant trees whose shade they know they shall never sit in._
>  - Greek Proverb

This essay was originally going to answer "What programming language would be around in 100 years?" but what I think matters more is the idea of writing software to last an extremely long time. I want the code that generates this website to compile in five years. What about ten? Fifty? One Hundred?

## Code rot
As code ages, Henrik Warne proposes it rots in two ways[^3]. As its environment changes (what I call rusting), or as gradual decay. 

### Rusting
In three years your code might not compile, your unit tests might not pass, yet the CMS shows no changes. While it's true that there have been no changes to the source code, the environment in which the code sits is fluid. This could be changes to the compiler, changes to the dependencies, or even changes to the hardware[^1]. The code has rusted.

### Designing for Rust
- Code should use common, and simple interfaces such as stdin/stdout/stderr[^4].
- Warnings should be fixed. What is imperfect style today could cause serious problems in the future[^2].
- Use as few dependencies as possible, avoid [dependency hell](https://en.m.wikipedia.org/wiki/Dependency_hell).

### Small Maintenance
The other form of rot happens when development or maintenance is active, so it is up to date with the environment. The code decays by incremental changes, or 'small maintenance'. On their own these imperfect or sloppy fixes are insignificant, but the whole is worth more than the sum of it's parts and they are detrimental when taken together. It can result in large method bodies and loops, and misnamed methods/variable that no longer match the logic that the method performs[^3]. Since small maintenance doesn't require full knowledge of the code, the changes may be as small as possible, or just thoughtlessly tagged on to the existing design pattern when a refactor may be more appropriate. Time pressure exasperates these problems.

[^1]: Inc, Ziff Davis (1992-01-28). PC Mag. Ziff Davis, Inc. p. 286 https://books.google.co.uk/books?id=uEkrL23rU98C&pg=PT303&redir_esc=y#v=onepage&q&f=false

[^2]: https://www.gwern.net/Resilient-Haskell-Software

[^3]: https://henrikwarne.com/2017/04/28/code-rot/

[^4]: https://bytes.yingw787.com/posts/2020/01/13/50years/