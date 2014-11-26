---
layout: default
---

{% include consise-javascript/navigation.html %}

Let’s say that we want to pull out the string ‘Doe’ into an attribute that we can reference inside of the getLastName function.  To do that, we’ll have to use a special keyword called “this”:

{% highlight js %}
var John = {
  lastName: 'Doe',
  getLastName: function() {
    return this.lastName;
  }
}

John.getLastName();
=> 'Doe'
{% endhighlight %}

“this” is in the context of John, and therefore gives us access to lastName.

Context, and how "this" is assigned is similar to possessive pronouns in English.  The implementation of John.getLastName can be written in English as “Return my last name.”

"this" is not assigned a value until an object invokes the function where "this" is defined.  In our example, the object “John” is invoking invoking “getLastName”, so “this” is now assigned in the context of “John”, and could be read like “my”.

If John was re-written without using "this", we don’t have access to lastName in the function:

{% highlight js %}
var John = {
  lastName: 'Doe',
  getLastName: function() {
    return lastName;
  }
}
{% endhighlight %}

And when we try to get it from our object:

{% highlight js %}
John.getLastName();
=> ReferenceError: lastName is not defined
{% endhighlight %}

The fact that it is not defined makes sense, since we are not in the context of John, but what are we looking for lastName on, then?

{% highlight js %}
var John = {
  lastName: 'Doe',
  getLastName: function() {
    return lastName;
  }
}
{% endhighlight %}


Pitfall 2: Knowing how "this" is assigned

When "this" is not placed in front of lastName, then Javascript is going to look at the global window for a lastName property one-level deep — on the same level as "location" or "navigator".

In the chaos of the global object and key-value node chaining, functions are going to be our saviors for defining scope.
A function will reference "this" as the scope of its containing object. "this" is not assigned a value until an object invokes the function where “this” is defined.  
"this" has the value of the invoking object in most circumstances.

If we rewrote John to have multiple layers:

{% highlight js %}
var John = {
  lastName: 'Doe',
  getLastName: function() {
    return this.lastName;
  },

  anotherJohn: {
    lastName: 'anotherDoe',
    getLastName: function() {
      return this.lastName;
    }
  }
}
{% endhighlight %}

And in our console we try to access the lastNames:

{% highlight js %}
John.anotherJohn.lastName();
=> 'anotherDoe'

John.getLastName();
=> 'Doe'
{% endhighlight %}

From this we can see how functions can be used to add some explicitness and protection into object creation, and can be used to control what "this" refers to.  
Javascript does not have classes.  But by looking at functions as tools for encapsulation, we can create something that acts like a class:

{% highlight js %}
var John = function(lastName) {
  this.getLastName = function() {
    return this.lastName;
  }
}

var john = new John('Huckleberry');
=> John {getLastName: function}

john.getLastName();
=> 'Huckleberry'
{% endhighlight %}

By doing this, we can control the data by passing it in, which adds to the explicitness of what’s available in more complex objects, and helps reduce the risk of side-effects from mutation.

Let's see what this looks like in building out our RSS reader -- closures, events, and binding/maintaining scope

{% highlight js %}
{% endhighlight %}
