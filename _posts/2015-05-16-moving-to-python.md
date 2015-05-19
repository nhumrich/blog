---

layout: post
title: "Moving to Python"
quote: "A Journey to the Scripting Side"
image: /media/python3d_edit.png
video: false
comments: true
---

# Moving to Python

Currently I have been doing most of my development work in python.
Prior to Python, my main language was Java. 
This post is mostly my notes to myself of what I learned (not) to do in Python while switching from Java. 
This is not meant to be a comprehensive guide, and will mostly focus on styling.
You don't necessarily need to know Java to understand this post, but I will be making direct comparisons to Java.


* Multiple returns
* Tuples and packing
* Keyword args
* Private/protected/public
* getters setters
* classes and modules
* Dynamic typing, but not duck typing
* Interfaces
* Nameing
* Statics and cls functions
* imports
* Pep8
* comprehenshions?
* File structure

## Styling matters

Anyone who writes collaborative code in Java knows to never to mention where the curly braces go. 
Doing so will only aggrevate everyone else. No one can decide where things really should go or how things
should be formated. Most companies have actually made their own style requirements in order to prevent
any arguments from breaking out in the work place. 
Python however, does have a strict style guide. There is a common styling that every seasoned python developer follows.
In fact, there is even official documentation on python styling. This document is called [PEP8](https://www.python.org/dev/peps/pep-0008/).
Some of this post will contain things which are covered in PEP8. But for full understanding, you really should [go read it](https://www.python.org/dev/peps/pep-0008/).
Trust me, it will be worth your while. 

## Ditch the Camel; Embrace the Snake

The most drastic change from java is going to be the lack of semi-colons and curly braces everywhere.
The next will be the naming style. I now cringe when names in python code are *java-ish*.
Here is a list of naming conventions:

| Type | Style |
|------|-------|
| Classes | UpperCamelCase |
| File Names/modules | lowercase |
| functions | snake_case |
| variables | snake_case |
| Constants | ALL_CAPITALS |

**Java Example**
{% highlight java %}
public class HelloWorld {
    public static final String HELLO_GREETING = "Hello";
    public void sayHello(String userName) {
        System.out.println(HELLO_GREETING + " " + userName);

{% endhighlight %}

**Python Example**
{% highlight python %}
class HelloWorld():
    HELLO_GREETING = 'Hello'
    def say_hello(user_name):
        print(HELLO_GREETING, user_name);
        
{% endhighlight %}

## File Structure

In python you can practically use any file structure you want, but here is the most common file structure. 

**Java Example**

~~~
project/
  src/
    main/
      java/
        com/
          mycompany/
            package/
              helloworld
      test/
        com/
          ..
    resources/
      static/
build.script
~~~

**Python Example**

~~~
project/
  bin/
  static/
  projectname/
    package
      helloworld
  test/
setup.py
~~~
   
   