---
layout: post
title: THE IMPORTANCE OF PRIORITIZATION CRITERIA
---

>TLDR/Main Points:
> We can acheive better understanding of how to approach priortization by modeling the shared and highly optimized behaviors of sorting algorithms
> There are 3 main conceptual models from sorting algorithms that are valuable in improving our approach to prioritization
> As a PM, always know and refer back to your prioritization criteria

Prioritization is, at its most fundamental, a sorting algorithm.  A sorting algorithm needs: a list of items to sort, and a way to compare one item with another (comparator).  If the items in a list are not like one another, then the algorithm will not know how to properly order them.  "Canonicalization" is the term used to convert data that has multiple representations into a standard or "canonical" form. ie: [1, "two", "III"] -> [1, 2, 3]

In computer science, sorting algorithm efficiency, often described in Big Oh notation, is the main differentiator of value between different sorting algorithms.  So its not only about putting a list in a correct order without mutating the original elements, but optimizing the efficiency.  Sorting algorithms are a fundamental building block for many programs so fine-tuned efficiency is necessary not to compound slowness the more complicated the program becomes.

## Extracting Models from a Sorting Algorithm

Let's take a look at one of the most common sorting algorithms, [QuickSort](https://www.geeksforgeeks.org/quick-sort/).  QuickSort is known as a "Divide and Conquer" algorithm, which means it will pick a "pivot" and partition the list of options around the pivot.  Think of this as breaking the list into two parts.  A pivot, also at the end of sorting means that all items to the left of it are smaller, and all items to the right are larger.

The lists are then processed in "linear time" meaning, the larger the list, the amount of time needed to process the items increases linearly.  Basically, as the size of the list grows, processing time grows in a 1:1 manner.  QuickSort then traverses the list to the left of the pivot point until it finds an item larger than the pivot value, and to the right until it finds a value smaller than the pivot value and swaps them.  It repeats until the list is sorted.

How the pivot is chosen is a big part of how efficient the QuickSort is, and while some QuickSort implementations choose the first, or a random element, the middle-most element gives the best chance for efficient sorting.

QuickSort, and other fundamental algorithms like it give us some interesting models to apply to prioritization as a PM:

1. Canonicalization
2. Partitioning and Efficiency Estimation
3. Recurring Confirmation of Order

## Canonicalization

Canonicalization is what makes sorting possible.  Let's say that you are in charge of a delivery infrastructure product for engineers in the company you work.  You have three feature requests: one that impacts lead time, one that reduces the change fail percentage, and one that aims to impact the mean time to restore services.  We're actually a step ahead of average product management since we know the main KPI, or value, a feature request is being estimated to improve.  Which one gets prioritized first, second, then third?

Prioritization criteria is a set of long-lived values that can be applied to any feature request the PM uses to guide priortiziation discussions.  It allows the PM to take dissimilar types of requests for investment, and transforms the way we view and discuss the requests in a similar way.  It is one part focusing agent, and one part decision agent.  By doing this, PMs have the ability to shift many arguments or non-productive feature discussions towards value comparison discussions.

### Prioritization Criteria

At a high level, I use: Impact, Effort, and Urgency as the three criteria.

#### Impact

This isn't so much impact on financial metrics, like revenue, but rather impact on the company's strategic initiatives and goals.

Impact
  - Importance to Satisfaction
  - Economic Variables

#### Effort

#### Urgency: Are there some constraints that require us to prioritize this sooner rather than later?

Some questions: are we bound to an external timeline?  Marketing/press opportunities?  Is it blocking us from doing something else so we should do it first?  Is there a strategically significant team that is depending on this solution before they can move forward?

## Partitioning and Efficiency; or Creating Product Flow

Themes and Company Priorities: Initial partition

Value in prioritization as a process is efficiency to arriving at the _generally and relatively correct_ ordering.  As a PM, I don't want to spend countless hours diving down rabbit holes while the team waits for requirements to build.  Ultimately, PMs are focused on driving to value delivery and sometimes that means move-forward decisions have to be made with incomplete information.  It is context dependent, but overall efficiency matters since prioritization decisions are time-bounded, similar to TMV or Time Value of Money.  Given that priortization is an economics decision, we don't want to rush into a bad investment, not do we want to linger waiting an airtight perfect case.

And this is a difference between sorting algorithms and prioritization -- sorting algorithms must be correct, but with prioritization, it can occasionally be impossible to be correct with the information at hand.  It may be the right decision to move forward with something meaningfully valuable to make sure impact is delivered vs. waiting for absolute perfection.

## Recursion for Confirmation of Order; or regularly confirming correct priority

However, prioritization isn't a linear process, but goes through a few washing cycles as you discover more information and how the needs may impact the compay's goals from an impact to effort standpoint.

It's a circle that repeats frequently and continuously.


## Examples in Use

Operational Concerns vs. Engineer Enhancements

Round one: measure of impact
Round two: measure of cost and urgency

So, I broke down the impact by different user (importance - satisfaction), and then sequenced it based on the larger themes and timelines the company had.  Then sequenced it again with the team to factor in cost now that we have a sequencing of impact.

## Overall

1. The hero: PM goes into a room and doesn't emerge for weeks on end.  Finally returns with perfectly prioritized vision.
2. The servant: PM reactively takes orders from all interested parties.  A victim of circumstances with prioritization directly related to the volume used when requested by a stakeholder or user.
3. The guide: PM collaborates closely with colleagues, teammates, and stakeholders to drive consensus.

PMs are decision makers, but must discuss with the team.  Establishing the criteria sets the team up for a guided conversation where we determine what has to be moved to the front, or when something has to be removed from the roadmap.

Prioritization is a process the PM owns, but collaborates with colleagues and teammates around.

In the context of prioritization, the role of a PM is one that guides their colleagues and teammates in conversations to discover the priorities.

Prioritization, and many disagreements within, are because much is subjective and context dependent.

PMs do not disappear for weeks on end and come back with a fully-baked list of priorities.  PMs own guiding their team and colleagues towards a list of priorities.  Having clear criteria facilitates the discussions.
