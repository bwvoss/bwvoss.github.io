---
layout: post
title: BREAKABLE TOYS: STARTING A PRODUCT
---

As a TPM, I adopted the practice of [building breakable toys](https://www.oreilly.com/library/view/apprenticeship-patterns/9780596806842/ch05s03.html).  This is an important concept when I was learning to be a better software engineer, and the model holds as a product manager as well.

## Here are the big benefits

- Prevents burnout.  One of the core models in breakable toys is _passion_.  Instead of technical product management being a career, its also something that I should love to do.  When I was programming full time and felt deflated, breakable toys would often bring enthusiasm back into the craft.

- It takes some pressure off.  This thing has no expectation of succeeding, right?  This lowers the resistance to taking action and helps me take risks exploring interesting, yet unlikely to succeed product ideas.

Even if its for a resume, showing products you have established and how gives the employer a fantastic litmus for your abilities.

## So how do I generate ideas for breakable toys?

- As described above, choosing a technology, or idea that you are passionate about is a must-have.  I couldn't imagine building a breakable toy I don't have passion for.

- It should be something you personally would find interesting or useful to use.  In typical product managment, we start "outside-in" by understanding the needs or benefits a specific group of people need solved and in that group of needs there are some important yet undersatisfied opportunities.  I take the same approach, but I just do some personal exploration vs. market research and talking with lots of people.

## Let's start one now!

Recently, I've been diving deep into Kafka.  It is a technology I want to get better at.  I know it at a high level, I can articulate why its useful, but a breakable toy using Kafka (or hosted versions of it like AWS MSK Kafka)

Here is a general need that I've had many times that I think would be interesting to explore: defining, then tracking the metrics for a technical product.  As a TPM, there are some common behaviors I have around measurement: choosing metrics (backstop and per release/sprint), confirming correctness, configuring/plumbing between assertion and collection.

## Starting with the customer: Me

So we start with the user -- me.  What needs or benefits do I need to accomplish?

- defining the "right" metrics.  One challenge I have had is knowing what the right data would be and why.  Leading vs. lagging indicators and vanity metrics are two pitfalls.  Obviously just tracking data isn't sufficient here for the goal of developing a technical product with maximum efficiency.  Are there common metrics to any product that we can reduce the time to establish in a greenfield fashion? (opens up the idea of 3rd party libraries/creators)

> Need: Reduce the usage of "less effective" metrics or not using best practices in decision making (eg: linter?  Ansible interface?)

- There are a number of self-similar patterns between product development and software development that I think would be interesting to explore how closely product definition practice can be to software development practices:

1. Both use the model of establishing measurable assertions to build to, and when the metrics/assertions pass, then success has been demonstrated.  Examples: TDD with tests at different levels for different purposes, runtimes, etc

2. Both rely on fast, iterative trial-and-error.  Examples: A/B testing, lean product development practices, trunk-based development

> Need: Reduce the overhead between setting the measurable expectations for product success and the software written to accomplish it.  I want this to enable engineers to behave more like technical product managers and that means CLI toolsets and configuration files with minimal web GUI interactions.

- Making it simple to connect code changes with expected metric changes in the product would be great.  That has always been something I've appreciated about TDD in coding changes -- I establish the expected outcomes, then focus on speed and feedback for correctness.  Product development has similar constraints that I'd like to adhere to -- small, frequent releases, wrapped in expectations, then determining actions based on the feedback from it.  Seeing history of all tests would also be interesting to see how the product has evolved, or my behavior around experimental development has evolved through time.

> Need: Simplify linking technical metrics to economic variables.  eg: incident response, lead time, trunk-based development, etc.  I want to see which development practices are most impactful to the economic impact the product is here to provide.

- Root cause analysis from a product standpoint.  Let's say that you have a few releases in quick succession, and then a latency backstop gets breached.  Which release caused it?  Or to bring it closer to a product metric, let's say you have identified certain actions that are commonly associated with "frustration" and they spike after a few days of development.  The time, and layering, between multiple releases makes root cause analysis more difficult.

> Need: Reduce the time it takes to associate software changes with product changes

This is an assertion framework vs. a visualization product.

## Importance to Satisfaction

## Kano Model: what will be the unique value I want to prioritize?

TODO:

Kano Model grid vs. competitors to show where your unique value angle would be

-  list the benefts in a more specific way
-  put them on a grid then give them opportunity scores
-  final section: brainstorm an MVP based on those needs with 1-2 releases in mind of what to test and iterate on

<table>
  <thead>
    <tr>
      <th>Beneft</th>
      <th>Description</th>
      <th>Priority</th>
    </tr>
  </thead>
  <tfoot>
    <tr>
      <td>Totals</td>
      <td>21</td>
      <td>23</td>
    </tr>
  </tfoot>
  <tbody>
    <tr>
      <td>Alice</td>
      <td>10</td>
      <td>11</td>
    </tr>
    <tr>
      <td>Bob</td>
      <td>4</td>
      <td>3</td>
    </tr>
    <tr>
      <td>Charlie</td>
      <td>7</td>
      <td>9</td>
    </tr>
  </tbody>
</table>

## Brainstorming the MVP

