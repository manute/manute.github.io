---
layout: post
title: "Add content dynamically to Popover Bootstrap"
date: 2013-07-12 11:35
comments: true
categories: [TwitterBootstrap,Javascript]

keywords: javascript,twitterbootstrap,popover
description: Change dynamically the content of a popover generate also dynamically 
---

The use-case is:  
<ul>
 <li>Click in the bottom.</li>
 <li>Show Popover.</li>
 <li>Click into popover.</li>
 <li>Change num of clikcs inside popover.</li>
</ul>

To change the content, we need to access any element of the popover. The popover is created dynamically, but you can access to his properties with the function <strong>data('popover').tip()</strong> on the object popover . To change the content I made the example with the click event inside the popover.

Here is an example in <strong>jsFiddle</strong> <strong>(class css of popover not are by default of bootstrap , change for yours)</strong>

{% jsfiddle uyYkE/2/ default presentation %}

