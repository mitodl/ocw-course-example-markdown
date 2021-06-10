---
uid: 51a3082bb50bdc70f44fe076ffa558d6
title: Efficiency and Order of Growth
course_id: 6-00sc-introduction-to-computer-science-and-programming-spring-2011
type: course
layout: course_section
parent_title: Unit 1
menu:
  leftnav:
    identifier: 51a3082bb50bdc70f44fe076ffa558d6
    name: Efficiency and Order of Growth
    weight: 120
    parent: 975ad7bfdd9c4ffe26b6710fa718d5e6
---

« [Previous]({{< baseurl >}}/sections/unit-1/lecture-7-debugging) | [Next]({{< baseurl >}}/sections/unit-1/lecture-9-memory-and-search-methods) »

Session Overview
----------------

| ![Graph showing various logarithmic curves.](https://open-learning-course-data-production.s3.amazonaws.com/6-00sc-introduction-to-computer-science-and-programming-spring-2011/909d2baa718af8cd3fd318c827218766_ses-08.jpg) |  {{< br >}}{{< br >}} This lecture revolves around the topic of algorithmic efficiency. It introduces the random access model (RAM) of computation and "big O notation" as a way to talk about order of growth. It concludes with binary search. {{< br >}}{{< br >}}  

Session Activities
------------------

### Lecture Videos

*   [Lecture 8: Efficiency and Order of Growth]({{< baseurl >}}/sections/unit-1/lecture-8-efficiency-and-order-of-growth/lecture-8-efficiency-and-order-of-growth)

> ### About this Video
> 
> Topics covered: Efficiency, problem reduction, RAM, best case, worst case, expected case, growth, exponential growth, polynomial growth, logarithmic growth, global variables.
> 
> ### Resources
> 
> *   [Lecture code handout (PDF)]({{< baseurl >}}/sections/unit-1/lecture-8-efficiency-and-order-of-growth/mit6_00scs11_lec08)
> *   [Lecture code (PY)](https://open-learning-course-data-production.s3.amazonaws.com/6-00sc-introduction-to-computer-science-and-programming-spring-2011/79250a098254badf77f1bdc40e705736_lec08.py)
> *   [showGrowth code (PY)](https://open-learning-course-data-production.s3.amazonaws.com/6-00sc-introduction-to-computer-science-and-programming-spring-2011/f141695bb5aad941c1a9cbd3b2aaa296_showGrowth.py)

### Recitation Videos

*   [Optional Recitation: Algorithm Complexity and Class Review]({{< baseurl >}}/sections/unit-1/lecture-8-efficiency-and-order-of-growth/optional-recitation-algorithm-complexity-and-class-review)

> ### About this Video
> 
> Topics covered: Big O notation, algorithm complexity, algorithm comparison example, object-oriented programming, Person class example, defensive programming, private attributes, mutability, aliasing.
> 
> ### Resources
> 
> *   [Recitation handout (PDF)]({{< baseurl >}}/sections/unit-1/lecture-8-efficiency-and-order-of-growth/mit6_00scs11_rec04) (Courtesy of Sarina Canelake. Used with permission.)

Check Yourself
--------------

Why is efficiency important?

› _View/hide answer_

Efficiency determines how long our programs take to run; when large sets of data are being handled, it can make a huge difference (on the order of years or even millennia) whether our program is efficient or not.

What notation do we use to state complexity?

› _View/hide answer_

Big O notation.

« [Previous]({{< baseurl >}}/sections/unit-1/lecture-7-debugging) | [Next]({{< baseurl >}}/sections/unit-1/lecture-9-memory-and-search-methods) »