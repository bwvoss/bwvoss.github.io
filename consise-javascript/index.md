---
layout: default
---
{% include consise-javascript/navigation.html %}

Welcome to "A Consise Introduction to Javascript".  The purpose of this tutorial is to teach you the fundamentals of good design around JavaScript.  By being aware of the pitfalls
JavaScript makes it easy to fall into, and patterns for how to avoid them, JavaScript applications can be written in a clean, maintainable way.

_TODO: list the pitfalls and an introduction for how they are solved._

Video to explain and play in the console, and a foreward about what is about to be learned

Type this in your console:

{% highlight js%}
{}
{% endhighlight %}

It’s called an object literal.  Now change it to look like this:

{% highlight js %}
{
  hello: 'world'
}
{% endhighlight %}

It is a simple key-value storage unit. Coming from a different language, you may see that this resembles a dictionary, or a hash-map.

These key-value storage units can be accessed in two ways: with dot notation, or array-like notation.

If we assigned our object literal to a variable, we can access values in one of these two ways:

{% highlight js %}
var ourObject = {
  hello: 'world'
}

ourObject.hello
=> 'world'

ourObject['hello']
=> 'world'
{% endhighlight %}

We can nest inside of an object literal, so if we went a few levels deeper, we can combine these notations to get the value of veryNested:

{% highlight js %}
var ourObject = {
  hello: {
    world: {
      veryNested: true
    }
  }
}
{% endhighlight %}

{% highlight js %}
ourObject['hello'].world['veryNested']
=> true
{% endhighlight %}

Sometimes, these properties hold functions:

{% highlight js %}
var John = {
  lastName: function() {
    return 'Doe';
  }
}
{% endhighlight %}

The property of lastName is holding the value of an anonymous function.  When we reference lastName and treat it like a function, it will execute the anonymous function it’s pointing to:

{% highlight js %}
John.lastName();
=> 'Doe'
{% endhighlight %}

In the console, type:

{% highlight js %}
window
=> Window {top: Window, window: Window, location: Location, external: Object…}
{% endhighlight %}

It represents our current browser window.  What’s crazier is that this is the global object in which every single bit of code we write will be referenced from.

By expanding it we see that we have huge amounts of functionality in a tree-like design.  We have the global node — the window.  Attached to the global node are a number more nodes, like the location object which we can use to look at and change the url, or the navigator, which we can use to find the latitude and longitude of the physical location where the browser is being opened from.  If you’ve been writing along with us, then you’ll even have a John node attached to the window, or any variable you assign if you don’t specify otherwise.

This revelation may be unsettling — anything defined can be accessed through the window object, and everything has access to — and mutate — the window object.

While the global window object is the cause of many failures, and is “one of the biggest regrets” of creator Brendan Eich in his design of the language, there are a few benefits.

It makes the language very easy to grasp from a structural level: the whole thing is essentially key-value data structure.  Because of this simplistic and ordered chaining, it also makes the window, and Javascript, very easy to play with and explore.

Up to this point, we have enough knowledge to build relatively complex programs — we know how to encapsulate class-like structures, we know the structural layout of the entire window object, and we know that we can compose these key-value data structures.

Pitfall 1: Managing namespaces on the Window

To start, create a simple directory structure, (use nested lists to describe the layout)

TODO: TAKE SCREENSHOT of folder
- app/
  - scripts/
  - styles/
  - index.html
- spec/
- testem.json

INSERT VIDEO HERE, talk about the window, the namespace function, then live code test driving it

These are the tests I drove out the solution with:
{% highlight js %}
describe("namespace", function() {
  var assertObjectAssignedToName = function(valueOfNamespace) {
    expect(valueOfNamespace).toEqual({});
  };

  it("creates an object for one name", function() {
    var mockWindow = {};

    namespace("Test", mockWindow);

    assertObjectAssignedToName(mockWindow.Test);
  });

  var resetNamespace = function(windowNamespace) {
    windowNamespace = undefined;
  };

  it("uses the real window if not overridden by a fake", function() {
    namespace("Test");

    assertObjectAssignedToName(window.Test);
    resetNamespace(window.Test);
  });

  it("creates an object for two names", function() {
    var mockWindow = {};

    namespace("Test.Name", mockWindow);

    assertObjectAssignedToName(mockWindow.Test.Name);
  });

  it("creates an object for three names", function() {
    var mockWindow = {};

    namespace("Test.Name.AnotherName", mockWindow);

    assertObjectAssignedToName(mockWindow.Test.Name.AnotherName);
  });

  it("memoizes and returns the existing namespace", function() {
    var mockWindow = {};
    namespace("Test.Name.AnotherName", mockWindow);

    mockWindow.Test.Name.AnotherName.testValue = 1;

    namespace("Test.Name.AnotherName", mockWindow);

    expect(mockWindow.Test.Name.AnotherName.testValue).toEqual(1);
  });
});
{% endhighlight %}

And the code to make the tests pass:

{% highlight js %}
window.namespace = function(string, _window) {
  var current = _window || window,
      names = string.split('.'),
      name;

  while((name = names.shift())) {
    current[name] = current[name] || {};
    current = current[name];
  }
};
{% endhighlight %}

Section on bower
- introduce bower 

After, explain closures and their ability to pass in dependencies:
- start the form view, pass in jquery and handlebars

