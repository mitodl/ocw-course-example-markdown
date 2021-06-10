---
uid: 82f33672223de8357b0e01944b79495e
title: 2.9 Coloring & Connectivity
course_id: 6-042j-mathematics-for-computer-science-spring-2015
type: course
layout: course_section
parent_title: 2.9 Coloring & Connectivity
---

*   [<Graph Coloring I]({{< baseurl >}}/sections/structures/tp7-3/vertical-c79a8bf5b197)
*   [2.9.1Coloring: Video]({{< baseurl >}}/sections/structures/tp7-3)
*   [2.9.2Chromatic Number]({{< baseurl >}}/sections/structures/tp7-3/vertical-312af3a98ad1)
*   [2.9.3Connectivity: Video]({{< baseurl >}}/sections/structures/tp7-3/vertical-857c6f8a582c)
*   [2.9.4k-Connectivity: Video]({{< baseurl >}}/sections/structures/tp7-3/vertical-a730aa2d96d6)
*   [2.9.5k-Connected \[optional\]]({{< baseurl >}}/sections/structures/tp7-3/vertical-7dbbc5839c46)
*   [2.9.6Graph Coloring I]({{< baseurl >}}/sections/structures/tp7-3/vertical-c79a8bf5b197)
*   [2.9.7Graph Coloring II]({{< baseurl >}}/sections/structures/tp7-3/vertical-5c29d46d85ff)
*   [2.9.8Connected Components in Integers]({{< baseurl >}}/sections/structures/tp7-3/vertical-fef93eac28bc)
*   [\>Connected Components in Integers]({{< baseurl >}}/sections/structures/tp7-3/vertical-fef93eac28bc)

Graph Coloring II
-----------------

  

What is the chromatic number of an acyclic graph?

Exercise 1

&nbsp;Text Response&nbsp; Answer:2

By definition, an acyclic graph contains no cycles (and in particular, no cycles of odd length). Therefore it is bipartite. This means 2 colors are _sufficient_. Moreover, if the graph has at least one edge, 2 colors are also _necessary_. Therefore, the chromatic number of any acyclic graph is 2.

Note that the answer assumes the non-trivial case, where the graph contains at least one edge. In the trivial case where the graph contains no edges, it only has disjoint vertices and its chromatic number is 1.

CheckShow Answer

*   [BackGraph Coloring I]({{< baseurl >}}/sections/structures/tp7-3/vertical-c79a8bf5b197)
*   [ContinueConnected Components in Integers]({{< baseurl >}}/sections/structures/tp7-3/vertical-fef93eac28bc)