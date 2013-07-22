---
layout: post
title: Functional Lists in Groovy
date: 2013-07-11 11:13
comments: true
categories: [Groovy, Functional]

keywords: groovy,list,functional
description: Examples groovy of functional lists from other languages 
---


Lately I'm reading books on functional programming languages ​​like  <strong>Clojure</strong> and <strong>Erlang.</strong>
There is a book for Erlang that covers all aspect of the language <strong><a href="http://pragprog.com/book/jaerlang/programming-erlang" target="_blank">Programming Erlang</a></strong>.
There is also one book(in spanish) very good for Erlang and is free from <strong><a href="http://bosqueviejo" target="_blank">bosqueviejo</a></strong>. And for Clojure there are many like <strong><a href="http://www.joyofclojure.com/" target="_blank">The Joy of Clojure</a></strong> or <strong><a href="https://leanpub.com/fp-oo" target="_blank">Functional Programming for the Object-Oriented Programmer</a></strong>.
</br>

What I've learned in these books is to think of another way to abstract problems and break them into reusable functions (also aspects such as concurrency, immutability and recursion).
</br>

Groovy has much functional style , in fact , the <strong><a href="http://groovy.codehaus.org/Closures">closures</a>  </strong> for me is a clear example:

{% gist 5311752 %}

</br>

The functions that I will show below, I will add them to the class <strong><a href="http://groovy.codehaus.org/groovy-jdk/java/util/List.html">List</a></strong> dynamically by the metaclass. I think it's better example that only show the functions , because then can reuse the functions in other parts of project.

</br>
For example, I will mimic the function <strong>map/2 from Erlang</strong> and I will add to the Groovy List class.
<h2><strong>Map</strong></h2>

Is a function that takes a function F  and list L as arguments and returns the new list that is obtained by applying F to each of the elements in L.

{% gist 5327266 %}

I've done a bit tricky, because in reality the "map" function does not apply on a list already created, but I did so to show how to add a method to the List class dynamically. But I made ​​it more functional as possible, without modifying the original list and returning a new list( it is not inmutable, in Groovy to make a List inmutable call -> <strong><a href="http://groovy.codehaus.org/groovy-jdk/java/util/List.html#asImmutable()">asInmutable()</a></strong> )

Be careful with add methods by metaClass , because if a method already exists with the same name it will be overwritten.

Let's do another example, I'll imitate the function <strong><a href="http://underscorejs.org/#pluck"> pluck of Underscore.js </a></strong>.
<h2><strong>Pluck</strong></h2>
This function is the common use-case for map : extracting a list of property values.

{% gist 5318651 %}

As we see it is very easy to add functions to the Groovy List class, that are useful and / or we use a lot. In addition to obtain clean code, we can combine them to make still more powerful.

Note: If you use <strong><a href="http://grails.org/">Grails</a></strong> these functions can be added dynamically with the Bootstrap.groovy ; so these functions can be used in all the classes of the project.