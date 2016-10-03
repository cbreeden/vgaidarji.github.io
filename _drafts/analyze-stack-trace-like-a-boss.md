---
layout: post
title: Analyze Stack Trace like a boss!
date: 2016-09-28 15:25:00
comments: true
categories: [android, android-studio]
tags: [android, android-studio]
---

In this post we'll talk about amazing feature `Analyze Stack Trace` available in
[AndroidStudio IDE](https://developer.android.com/studio/index.html).

A stack trace is generated whenever our app crashes because of an error or an exception.
Developing a 100% stable Android application is near to impossible.
Application might not crash on our real device or emulator,
but there's a big chance that it will crash on other devices (e.g. Samsung).

Due to that fact analyzing stack traces is an essential part of Android developer work.

<!--more-->

We receive crashes via crash-reporting tools like [HockeyApp](https://hockeyapp.net)
 or [Crashlytics](https://fabric.io/kits/android/crashlytics) or any other.
It's a normal process and happens after every release.

![Crashes in HockeyApp](/assets/2016/09/28/crashes-in-hockeyapp.png)

Is important to react to crashes quickly, analyze/fix them and publish new application version with hot-fixes.
Though analyzing crashes or exceptions by having a stack trace in a crash-reporting tool might take too much time.

Most of the stacktraces contain information in which class and at which line of code exception was thrown.
![Crash - generate OOM](/assets/2016/09/28/crash-generate-oom.png)

We can navigate to specific line of code in IDE using `go to line`:
![Go to line](/assets/2016/09/28/go-to-line.png)

This will allow us to find out what happened and why exception was thrown and make a fix if needed.

But [sometimes](http://stackoverflow.com/questions/34785907/app-crashes-on-start-caused-by-npe-in-android-content-context-getstring) is really hard to understand what caused an exception at specific line of code.
And switching between browser with crash log and IDE isn't convenient :disappointed:

#### **Analyze Stack Trace to the rescue!**

AndroidStudio, which is based on [Intellij Idea](https://www.jetbrains.com/idea/), has an amazing feature called `Analyze Stack Trace`:

![Analyze Stack Trace](/assets/2016/09/28/analyze-stack-trace-feature.png)

Analyze Stack Trace dialog has one important configuration:
*`Automatically detect and analyze thread dumps copied to the clipboard outside of IntelliJ IDEA`*.

![Analyze Stack Trace dialog](/assets/2016/09/28/analyze-stack-trace-dialog.png)

When we come back from external application (like HockeyApp page with crash logs), the copied stack trace will be automatically detected and opened:

![Crash - generate OOM in IDE](/assets/2016/09/28/crash-generate-oom-in-ide.png)

Now we can easily navigate as we normally do when crash occurs on emulator or connected device :open_mouth:

#### **Conclusion**

AndroidStudio provides huge amount of commands/tools which simplify the developer life.
Knowing majority of them adds +100 to speed:

**TODO** *add gif "pressing on custom shortcut with title 'Create an application for me' will generate finished application".*
