---
layout: post
title: TOP MISTAKES/LESSER KNOWN PITFALLS
---

Top mistakes in terms of causing significantly more re-work later.  Not in a sense of "test with users before building" which is widely known and talked about.  There are larger points from my own experience I wanted to highlight

1. Not Determining the Surface First

Not determining the "surface" first.  We built capabilities but deferred on the interaction and user experience.  Eventually, bringing capabilities together under a unified experience became significantly more expensive and complicated.  In the words of "Sprint": "Get the surface right, and you can work backward to figure out the underlying systems or technology.  Focusing on the surface allows you to move fast and answer big questions before you commit to execution..."

2. Not Favoring Table Stakes Before Features

one: features depend on technical table stakes (by table stakes I mean adhering to governance, operational needs, security needs and not table stakes in a feature sense)

Examples: resiliency concerns

Not taking care of table stakes first.  This either manifested in significant user coordination because they were worried, and table stakes are foundational to the other features you build.  It compounds technical debt in the systems that often bleeds into poorer user experiences and product performance as well.

3. Not Instrumenting Features with Analytics _while_ building the feature

After release rework is both expensive, and matters in the implementation to be easier to instrument.  It also forces PMs to adhere to the "don't ship blind" principle.

4. Not defining boundaries of both people/parties and other tools

Example: developer tooling.  It starts at the language itself, and the editor used.  Strong typing is massively beneficial.  But, do we as a product group dictate languages and editors?  Answer: No.  Then, where are the product boundaries?

Along with that: if another group has to behave in a different way, like reviewing the languages, architectural standards, editors they have to be agreement from a boundary standpoint to know where the product stops and either a new product's responsibility begins, or a person's responsibility begins in terms of training/performance reviews.  Not everything can be solved with a product. (link to separate blog post)
