---
layout: post
title: Tabless programming in AndroidStudio
date: 2016-03-11 15:04:23
comments: true
categories: [android, android-studio]		
tags: [android, android-studio]
---

Not long ago I realized that I'm not using all the tabs I open in IDE.
All these open tabs just annoy me, when I'm switching between classes.

<img src="/assets/2016/03/11/lots-of-tabs.png" alt="Lots of tabs" style="width: 100%;"/>

Even if I work on a screen with big resolution and 7-10 tabs fit on screen - I'm not using all of them. Even more, I need only 1-2-3 classes open at particular time.

All the IDE's, I've used before (`VisualStudio`, `Eclipse`, `Intellij IDEA`), were using tabs by default. But if I'm not using all these tabs, can I leave without them? The answer is **YES**. So obvious :smile:.

<!--more-->

#### **The life without tabs**

One day, I came across a [Intellij Idea tips & tricks](
https://www.youtube.com/watch?v=eq3KiAH4IBI&ebc=ANyPxKpwBcDaktxU9dHLjYiXj-z5rNwHmTwJhPRbO2a8C7aV0IJq9CYYV5RA0zuveV587p3OnT9vWCqjbCttKjuQc1u4u3h3uw) video. That was the crucial moment for me when I said to myself - **NO MORE TABS**. In this video I've learned everything I need to switch to tabless programming and a lot of other useful shortcuts which saved me a lot of time in future.

The first thing I had to do is to "switch off tabs in IDE" by selecting `Placement -> None`:

<img src="/assets/2016/03/11/switch-off-tabs.png" alt="Switch of tabs"/>

After switching off tabs you will always search for tabs at the top, even you don't need them.
*Habbits, habbits...*

Having only 1 active file at the moment, reduces dramatically the time you use mouse. Which is also super cool.

If I need to switch to another class/file, I'm just using `"Search everywhere"` functionality (**Shift + Shift**):

<img src="/assets/2016/03/11/search-everywhere.png" alt="Search everywhere"/>

or from `"Recent files"` window (**Cmd + E**)

<img src="/assets/2016/03/11/recent-files.png" alt="Recent files"/>

Combination of `"Recent files"` and `"Search everywhere"` makes tabs usage totally redundant. Even more, I can navigate to any file, any screen, any action, any *stuff* using this amazing IDE tools.

#### **Split windows**

When the time comes to write tests (before code or after - no difference) I'm splitting windows horizontally. This way I can see source class and test class. It's super convenient way of writing tests - I have original method and test for this method on screen. Actually, it's all what I need to have on screen when I'm writing a test.

Let's say I have a class which isn't covered by unit tests.

* Firstly, I split windows using action `"Split Horizontally"`, which can be found from `"Find action"` menu (**Cmd + 3**):

  <img src="/assets/2016/03/11/split-windows-horizontally.png" alt="Split windows horizontally"/>
* Then, I open real class in first window and test class in second window:

    <img src="/assets/2016/03/11/real-and-test-classes.png" alt="Real and test classes"/>
    With `"Go to next splitter"` I can switch between splitted windows very quickly (**Alt + Tab**).
* No more actions here, that's all :wink:

It was very unusual first days to live without tabs, but I got used in a few days. Now I can't find the case when I need to return back to tabs.

Say **NO** to tabs! :triumph:
