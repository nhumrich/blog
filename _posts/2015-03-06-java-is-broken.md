---

layout: post
title: "Java is Broken"
#quote: "And I have proof"
#image: /media/2014-01-22-thinny-2/cover.jpg
video: false
comments: true
---

# Java is broken

I was doing some browsing on StackOverflow today when I ran across [this question.](http://stackoverflow.com/questions/28908849/unicode-escaped-comments-in-python) In case you cant see it, I will include the relavent pieces.

## The Code
Run the following code. (It wont do anything dangerous I promise).

{% highlight java %}
public static void main(String[] args) {
    print("Hello");

    /*
     * \u002A\u002F\u0070\u0072\u0069\u006E\u0074\u0028\u0022\u0043\u0072\u0075\u0065\u006C\u0022\u0029\u003B\u002F\u002A
     */
    print("World");
}

private static void print(String s){
    System.out.print(s + " ");
}

{% endhighlight %}

## The Result
In case you are too lazy, or just dont trust me, here is the output of the above code:

~~~
Hello Cruel World
~~~

Confused? All you have to know is the random stuff inside the block comment is really just unicode version of:

~~~
*/print("Cruel");/*
~~~

## Conclusion
Java parses unicode inside a comment as literal characters and compiles it all together. 
This means you could add some pretty nasty code inside of comments, and no one would ever realize its there.


