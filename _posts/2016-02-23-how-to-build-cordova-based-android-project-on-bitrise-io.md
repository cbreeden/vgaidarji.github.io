---
layout: post
title: How to build Cordova-based Android project on bitrise.io
date: 2016-01-08 15:04:23
categories: [android, cordova, bitrise.io]		
tags: [android, cordova, bitrise.io]
---

You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. You can rebuild the site in many different ways, but the most common way is to run `jekyll serve --watch`, which launches a web server and auto-regenerates your site when a file is updated.

To add new posts, simply add a file in the `_posts` directory that follows the convention `YYYY-MM-DD-name-of-post.ext` and includes the necessary front matter. Take a look at the source for this post to get an idea about how it works.

Jekyll also offers powerful support for code snippets:

``` ruby
def print_hi(name)
  puts "Hi, #{name}"
end
print_hi('Tom')
#=> prints 'Hi, Tom' to STDOUT.
```

Check out the [Jekyll docs][jekyll] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll’s dedicated Help repository][jekyll-help].

Java already has a room at the retirement home

<!--more-->

I love Java. I really do. But Java is getting old, old enough to retire. Even though Java 8 can be considered as one of the biggest evolutions in the programming language history, Java still carries many drawbacks, limitations and problems. Most of these issues have been there from day one and will continue to exist due to the backward-compatibility nature of the language. On the other side, Dart has been created from the ground up keeping a simple idea in mind: fix the common and recurrent development problems. Dart solves many issues in the programming flow and helps developers create insanely powerful and fluent APIs. Here is a short list of some basic but modern features of the language:

No primitive types. In Dart, everything is an Object. Even bool, the Java’s boolean equivalent, is an Object. A pure object-oriented programming language should be all about Objects. Java’s primitive types in Java are just an implementation detail.

Way less verbose syntax. Creating a public constant known at compile-time can be done using the const keyword. No more public static final. public and private keywords are not part of the language. The visibility of a variable/method/class is based on its naming: everything is public by default. If the entity name starts with an underscore, it is private.

Named and factory constructors. Java requires constructors to be named according to the class name, say Rectangle(). If you create a Rectangle(int left, int top, int right, int bottom) and a Rectangle(int left, int top, int width, int height) you end up with a compile-time error because Java uses parameters to distinguish constructors. One way to solve this problem is to create a static factory method. Dart fixes this problem by allowing you to create named (and optionally factory) constructors.

Modern parameters passing: Dart supports positional and named parameters. They can also be optional and have default values.

And more: mixins, implicit interface, isolates (simple concurrency model)

Software is made by developers not lawyers

Google and Oracle have been fighting about the use of Java on Android for a long time. The Google VS Oracle trial has probably been one of the most important trials in the recent history of computing. It looks like we are currently in a era of peace between these two mammoth companies … or maybe it is just cold war. No need to say it is way too dangerous for Google to continue to rely on programming languages managed by competitors. They clearly can’t afford to continue to be vulnerable to threats of lawsuits.


[jekyll]:      http://jekyllrb.com
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-help]: https://github.com/jekyll/jekyll-help
