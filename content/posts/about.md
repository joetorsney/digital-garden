---
title: "About this website"
date: 2020-05-22T18:18:54+01:00
description: ""
---

# Purpose
This site is a Digital Garden. What is that? A Google search might leave you thinking this is an agriculture project. A digital garden is a space for non-performative blogging, and for the growth and development of thoughts. You can think of navigating this site as following a path through a real garden, some paths leading to a beautifully arranged arboretum of thoughts, others leading to a barren flowerbed overgrown with weeds. That is, the structure of this site is intended to emerge organically, some pieces are high quality, coherent, and well researched, and others are shamelessly rubbish. Some thoughts will grow, some will die, some are WIP. This is an experiment with the hypothesis that my writing and thinking will improve. Above all, it should be fun - it's a kind of hobby and a release from the other stresses of real life.

If you're still confused (and I take the blame for that), [here](https://www.gwern.net/index) [are](https://jborichevskiy.com/about/) [some](https://azlen.me/) [examples](https://blog.noahtren.com/%F0%9F%92%AC/3acea2e1-0387-4c7d-83f4-12974323f8e6/).

## Networked thought
TODO: The importance of linking pieces of writing on this site.

## Collaborative thought
TODO: The importance of feedback, and building knowledge as a community.

# Design
The design of this site is deliberately minimal, with a focus on the content. It is heavily inspired by [the design philosophy of gwern.net](https://www.gwern.net/About#design). 

# Implementation
I had many internal debates as to what framework to use for this site. I had begun development using [Gridsome](https://gridsome.org/), considered [Hakyll](https://jaspervdj.be/hakyll), then considered building my own static site generator in Go, before settling with [Hugo](https://gohugo.io/). During this process, I developed several key ideas concerned with implementation.

## Independent Content
TODO

## Independent Code
I intend for the content on this site to stay with me for decades. (TODO: write more on ['long content'](https://www.gwern.net/About#long-content)). I still want the code for this site to compile in ten years. [Aprrently that's quite a big ask]({{< ref "/posts/long-code.md" >}}). This is what drew me to Hakyll over Gridsome, my gut feeling being that a Haskell program is somehow 'more formal' than a JS program[^1]. I also identified that the number of dependencies is indicative of how long a program will last or, at least, the amount of maintenance required to make it last[^2]. [Gridsome has 80 dependencies listed on NPM](https://www.npmjs.com/package/gridsome), each of which will have their own dependencies (and Hugo probably has less? idk. TODO). This motivation lead me to pick Hugo over Gridsome, and over Hakyll because my Haskell is very rusty. 

This is not to shit on Gridsome or JS but for this site it makes more sense to exclude them for site generation. JS is unavoidable, and necessary to implement footnotes and annotations a la [gwern.net](https://www.gwern.net/index).

Of course, using pre-made Hugo templates increases the number of dependencies. It is for this reason that I have created my own Hugo template and decided to do all the css myself[^3]. 

# The Future
## Todos and Ideas
### 1. Implement footnotes and annotations a la [gwern.net](https://www.gwern.net/index).
### 2. Implement bi-directional links between posts. 
If post A links to post B, B should 'know about it'. More specifically, at the bottom of each post there should be a list of posts that link to this one. 

I like the idea of having a 'recently connected' list on the homepage displaying pieces that were recently linked to each other, [like Gordon Brander has.](http://gordonbrander.com/pattern/)
### 3. [Implement a change-log for posts using the github history.](https://gohugo.io/maintenance/)

### 4. Implement an edit page feature that creates a new pull request on github for that post
[Like James Wright has](https://www.jameswright.xyz/post/deploy-hugo-academic-using-githubio)

[^1]: I think this idea is easier to see (feel?) with smaller programs because the static typing becomes almost the only thing that matters towards the 'formalness'. For example, consider the following programs that simple assign a constant: `x::Int; x = 10` and `const x = 10;`  Also, I'm skipping over the huge difference in the implementation of these languages (compiled vs interpreted), their paradigms (functional vs. object-oriented), and their vastly different use cases. My idea is quite fuzzy, but I hope you get what I'm trying to say.

[^2]: A kind of powerset murphys law? "When there's more stuff that can go wrong, more stuff will go wrong."

[^3]: Even if this wasn't primarily to reduce dependencies, bootstrap is massively overkill for something like this. My experience with bootstrap is that it makes styling a site far too convoluted and confuses beginner programmers. It's better to learn how the vanilla css technologies, like flex and columns, work first. 