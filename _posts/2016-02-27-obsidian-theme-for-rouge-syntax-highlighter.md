---
layout: post
title: Obsidian theme for rouge syntax highlighter
date: 2016-02-27 15:04:23
comments: true
categories: [jekyll, syntax-highlighter]		
tags: [jekyll, syntax-highlighter]
---

At the time when my personal blog configuration was quite finished, I was looking at `Jekyll`'s syntax highlighter `rouge`, which uses `monokai` theme by default:

<img src="/assets/2016/02/27/monokai.png" alt="Monokai code theme" style="width: 300px;"/>

The `monokai` theme looks pretty much ok, but I got used to another amazing theme - `Obsidian`. I tried to find this theme on the Internet, and there was no "ready-to-use" Obsidian theme for `rouge`.
<!--more-->

After some research, I've got that `rouge` and `pygments` highlighters are quite the same and I can use `pygments` themes with `rouge` highlighter.
Than I've found [Son of Obsidian](https://github.com/JevyZhu/son-of-obsidian) `pygments` theme, which looks quite the same as `Obsidian`.

Having the `Son of Obsidian` theme I was able to adapt it and replace default `monokai` theme with it.

#### **How to use "Son of Obsidian" theme in `jekyll`**

* Install `rouge` highlighter, if it's not installed already:

  ```ruby
  gem install rouge
  ```

* Then, in your `_config.yml`, set Rouge as your syntax highlighter:

  ```ruby
  highlighter: rouge
  ```
* Install `pip` (the tool for installing `Python` packages):

  ```ruby
  sudo easy_install pip
  ```
* Install `pygments`

  ```ruby
  pip install pygments
  ```
* Clone [`Son of Obsidian`](https://github.com/JevyZhu/son-of-obsidian) repository and navigate to the cloned project root folder.
* Open `root` shell (setup didn't work for me as a regular user).

  ```ruby
  sudo su
  ```
* Install plugin from `root`

  ```ruby
  setup.py install
  ```
* Export theme in `css` file

  ```ruby
  pygmentize -S sonofobsidian -f html > son-of-obsidian.css
  ```
* Copy `son-of-obsidian.css` file to `${your-blog-root-directory}/css/son-of-obsidian.css`
* Open `${your-blog-root-directory}/css/main.css` file and replace default `monokai.css` theme import with our new theme

  ```css
  /* default theme */
  @import url(monokai.css);
  /* our new theme*/
  @import url(son-of-obsidian.css);
  ```
* But that's not all. Open `son-of-obsidian.css` in your favorite text editor, ideally with multi-line edit function. Add `.highlight` term at the beginning of all lines.

  ```css
  .c { color: #99AA8A } /* Comment */
  .err { color: #960050; background-color: #1e0010 } /* Error */
  .k { color: #93C763 } /* Keyword */
  .l { color: #ae81ff } /* Literal */
  ```

  ```css
  .highlight .c { color: #99AA8A } /* Comment */
  .highlight .err { color: #960050; background-color: #1e0010 } /* Error */
  .highlight .k { color: #93C763 } /* Keyword */
  .highlight .l { color: #ae81ff } /* Literal */
  ```
* Finally, we need to modify background color in our theme, otherwise code snippets will use default grey color as a background and it's definitely not what we need. Add following lines to `son-of-obsidian.css`:

  ```css
  pre.highlight,
  .highlight pre { background-color: #272822; }
  ```
* **Configurations!** Now we have an amazing dark `Son of Obsidian` theme fully configured! Source code of `son-of-obsidian.css` is available on [github](https://github.com/vgaidarji/blog.vgaidarji.me/blob/master/css/theme-son-of-obsidian.css). That's how will look basic Java "Hello World" sample:

  ```java
  class HelloWorld {
    public static void main(String[] args) {
      System.out.println("Hello World!");
    }
  }
  ```
**Looks amazing, isn't it?!**

#### **Bonus**

[Here](https://github.com/jwarby/jekyll-pygments-themes) you can find other `Jekyll` `pygments` themes, which are compatible with `rouge` highlighter and are ready-to-use.

Even more, I've found another beautiful dark theme which is called [darkly](http://sourcey.com/darkly-pygments-css-theme/).

<img src="/assets/2016/02/27/darkly.png" alt="Darkly code theme" style="width: 500px;"/>

Happy code formatting :tada:
