#Automatic sub menu counters with CSS  



I really think we don't use the CSS counter functions enough.  
They don't even use it in the [CSS spec](http://www.w3.org/TR/CSS21/generate.html) to add automatic numbering to the list of links!

We can even use this CSS property to automatically count our sub menu items. 
This is really helpful because the count will automatically be updated in case we add more items dynamically (Ajax calls).

The markup is basic, no need to use spans or any other elements for the numbers:

<pre>&lt;ul>
    &lt;li>
		&lt;a href="#">link&lt;/a>
		&lt;ul>
			&lt;li>Item&lt;/li>
			&lt;li>Item&lt;/li>
			&lt;li>Item&lt;/li>
			...
		&lt;/ul>
	&lt;/li>
	...
&lt;/ul></pre>  


And then in the CSS you just have to:

<pre>/* reset the counter for every sub menu */
ul > li > ul { counter-reset: items; }

/* increment the counter */
ul > li > ul > li { counter-increment: items; }

/* Display the total number of items in the "after" pseudo-element" */
ul > li > ul:after { content: counter(items); }</pre>  
  
  
  
  
This technique is compatible with all modern browsers and IE8+.  

See how it looks [here](http://luis-almeida.github.com/menu/).