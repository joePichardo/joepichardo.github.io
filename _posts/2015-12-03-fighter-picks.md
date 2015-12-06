---
title:  "Pick your fighters!"
date:   2015-11-30 23:39:44 -0700
permalink: pick-fighters
---

In this post I am restructuring a javascript program I built which provides a combination of picks a user can have. The program involves the fantasy sport website [Kountermove.com](http://www.kountermove.com/), where users can choose five fighters they think will score big points in a number of ways and put their team against other players. The website targets the MMA and Boxing audience and, I recommend checking the site out if you frequently watch UFC, Bellator, Glory Kickboxing, etc. 

At the start of the program combinations grew exponentially if you mix and match 24-30 fighters (variables), depending on the fight card. We have to lower this number in a few different ways to make the output usable for users, but first lets look at the equations and variables we need to use. 

Notes: 

n = the number of things we have to choose from 

r = we choose a subset from the previous collection, so we pick a certain number of items from "n". 

! = factorial , 3! = 3x2x1 

Example, there are 10 candies to choose from ("n"), our parents tell us only to get three("r"). What are the different equations?

Permutation Equation, where there is no repitition(so none of this 3,3,3), but order matters. What is order? When an order does matter, combinations like [1,2,3] [3,2,1] and [1,3,2] can occur. Now the equation. 

P(n,r) = n! / (n-r)!

We don't want the same combinations of fighters in different order, so this isn't the equation we are looking for. 

******************

There is also a Combination Equation that is similar, where there is no repition and order doesn't matter! We only get [1,2,3] instead of the extra fluff of [1,3,2] [3,2,1] [2,1,3]. Now our output is decreased quite a bit with this next formula.  

C(n,r) = n! / [r!(n-r)!]

Sources used to understand the math a little bit more. 

[Mathisfun.com]( https://www.mathsisfun.com/combinatorics/combinations-permutations.html )

Code source. 

[GeeksForGeeks.org]( http://www.geeksforgeeks.org/print-all-possible-combinations-of-r-elements-in-a-given-array-of-size-n/ )

Now on to explain the code, it get's a little complicated for non-technical readers out there. If you follow the geeksforgeeks.org link there are examples of both Java and C++. I switched the statements so they can render in javascript. A few restrictions that I added was to make variables have certain prices, with the ability to have a combination set of 5, and from those 5 the prices can equal, but not go over a total price, the "Salary Cap". This restriction narrows down the output into lower numbers. 

You can see the script that I used to in the developer tools in your browser. I made an array of objects that included all fighters on a specific card. Used for loops to add the radio buttons with their labels to two different divs. Made a function to view which buttons are have been checked and add them to an array. From that array, the program determines the different combinations that are possible.  

A note for users: 

Program is to help choose your picks so you don't have to point and click multiple times on the Kountermove website. Helps handle high cost fighters into your picks. Pick more than 5 fighters to accomplish an output to your picks. Also, the more you pick, the more combinations will be made in the output. I suggest doing 7 to 8 choices. 

{% include fighterPicks.html %}
