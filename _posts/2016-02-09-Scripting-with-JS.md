---
layout: post
section-type: post
title: Scripting with JS
category: general
tags: [ 'tutorial' ]
---

Hey this is my first real post. Today at work i was writing some stuff in word. I needed to get a whole paragraph written in uppercase letters and couldn't figure out how to do it. Besides finding it out after a quick google search I then had the realization that this would be quite easy in any scripting language. I just wasn't settled on what would be the fastest and most convenient way to access it.

As I'm pretty fluent in Javascript and NodeJS i was thinking about wrapping the toUpperCase() method up and access it via Cygwin. But how to do it?

A pretty basic concept in bash is scripting. In general you can add to any .sh file a so-called shebang.
Like:
{% highlight bash %}
#!/usr/bin/env node
{% endhighlight %}


But what does this line do?
Placed a the beginning of a bash-script this tells the shell where the interpreter for the follwing script is placed.

Then I put the code doing the whole work into line two so that i now got following script:
{% highlight javascript %}
#!/usr/bin/node
console.log(process.argv[2].toUpperCase());
{% endhighlight %}

After saving it as uppercaser.sh and placing it somewhere in the PATH - i now use it with
    uppercaser "abcdef ghi"
which will output
    ABCEDF GHI

This is how you can basically do anything you could do in JS in your BASH.
In alternative to using NodeJS you could also do this with BASH alone:
{% highlight bash %}
   echo "$1" | tr '[:lower:]' '[:upper:]'
{% endhighlight %}

What are your terminal scripts which you use on a daily basis?

