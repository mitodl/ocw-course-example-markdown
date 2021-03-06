---
uid: c7f4e874e827c2ec07cb6c920e3e1ee3
title: OOP and Inheritance
course_id: 6-00sc-introduction-to-computer-science-and-programming-spring-2011
type: course
layout: course_section
parent_title: Unit 2
menu:
  leftnav:
    identifier: c7f4e874e827c2ec07cb6c920e3e1ee3
    name: OOP and Inheritance
    weight: 170
    parent: ddc5db7a5c64e3bda565b36f4ed76287
---

« [Previous]({{< baseurl >}}/sections/unit-2/lecture-10-hashing-and-classes) | [Next]({{< baseurl >}}/sections/unit-2/lecture-12-introduction-to-simulation-and-random-walks) »

Session Overview
----------------

| ![Photograph of ink droplets mixing in water.](https://open-learning-course-data-production.s3.amazonaws.com/6-00sc-introduction-to-computer-science-and-programming-spring-2011/c482305b06dc39b2b789d387bd1245a0_ses-11.jpg) |  {{< br >}}{{< br >}} In this lecture, we learn about object-oriented programming (OOP) and how classes are used to implement new types of objects in Python. As part of that discussion we introduce inheritance. {{< br >}}{{< br >}} _Image courtesy of The Ridg on Flickr._ {{< br >}}{{< br >}}  

Session Activities
------------------

### Lecture Videos

*   [Lecture 11: OOP and Inheritance]({{< baseurl >}}/sections/unit-2/lecture-11-oop-and-inheritance/lecture-11-oop-and-inheritance)

> ### About this Video
> 
> Topics covered: Object-oriented programming (OOP), abstract data types, specifications, subclasses, inheritance.
> 
> ### Resources
> 
> *   [Lecture code handout (PDF)]({{< baseurl >}}/sections/unit-2/lecture-11-oop-and-inheritance/mit6_00scs11_lec11)
> *   [Lecture code (PY)](https://open-learning-course-data-production.s3.amazonaws.com/6-00sc-introduction-to-computer-science-and-programming-spring-2011/0a04963bd0302d2d8a4e60dd2b9ba40e_lec11.py)

### Recitation Videos

*   [Recitation 5: Quiz 1 Answers and Object-Oriented Programming]({{< baseurl >}}/sections/unit-2/lecture-11-oop-and-inheritance/recitation-5-quiz-1-answers-and-object-oriented-programming)

> ### About this Video
> 
> Topics covered: Double recursion, big O notation, binary function, run times, object-oriented programming, classes, encapsulation, methods, class hierarchy, subclasses, inheritance, polymorphism, accessor and mutator functions, Person example, underbar methods, self parameter.

Check Yourself
--------------

What is an instance?

› _View/hide answer_

Instances are the actual objects built in accordance with the qualities of the class.

What is an abstract data type?

› _View/hide answer_

A set of objects and the operations on those objects.

What is encapsulation?

› _View/hide answer_

Encapsulation means that names (of variables and methods) are stored in locations that then have to be accessed, called namespaces.

What is data hiding?

› _View/hide answer_

Data hiding makes data invisible to users of the object, requiring it to be accessed only via the object's methods.

What functions can subclasses use?

› _View/hide answer_

Subclasses can use all the functions of their superclass. They can also use any functions that are defined within the subclass; however, if the subclass uses the same name for a function which has also been used in the superclass, it will only use the subclass definition of that function.

« [Previous]({{< baseurl >}}/sections/unit-2/lecture-10-hashing-and-classes) | [Next]({{< baseurl >}}/sections/unit-2/lecture-12-introduction-to-simulation-and-random-walks) »