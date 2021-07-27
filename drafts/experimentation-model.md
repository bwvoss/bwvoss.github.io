---
layout: post
title: THE MODEL OF EXPERIMENTATION IN PRODUCT AND ENGINEERING
---

In any scientific experiement, in order to be valid, it must have a clear and trusted set of controls.  The purpose of a control is to ensure that when the results of an experiment are reviewed, it will be as clear as possible what variables actually had an impact.  Without controls, it would be impossible to accurately interpret experimental results.

What this means is that experiements are the most efficient and accurate when done in highly focused approaches, and in many ways that means testing _one thing at a time_.

I love when I see self-similarity among disciplines.  In software engineering, we also make changes to complex systems, and if something goes wrong, it can be difficult to debug due to the lack of controls.  Every software change may not have the right discipline to be considered an experiement, but it goes through a very similar model.

This also applies to testing.  Unit tests vs. high level tests as an example -- one reason lower-level tests are often preferred is because it will give a more accurate answer as to what the problem is during the development process.  In scientific terms, the controls are tighter, so the experiments happen in more rapid succession.

Or trunk based development vs. PRs.  With a larger batch, there are more variables that will impact consistency, making it take longer and often inheriting more errors from the process.  Trunk based development is the smallest, lightest weight way to develop, and enforces small chunks of working software to be quickly merged into master.  The experimentation from this is built into the deployment process itself, bringing the experiment of correctness closer to the goal of deployment and limiting the variables needed to control.

We can take similar cues in product: rolling a very small feature out in order to limit the variables under impact and letting it continue rolling out so long as the metrics show correctly.  Product and technology are linked here to devliver small quanta of value in a highly controlled way.

Every feature, or release goes through A/B testing, just like every piece of software written to support it does (though A/B is the test suite and the other automated constraints).
