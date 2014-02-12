---
layout: default
title: Best practices - CSS
categories: best-practices
---

# {{ page.title }}

## Create generic `class`

It's better to create some classes with few properties than duplicate code or write in html file.

In my website, some elements need to be centered. Instead of duplicate `margin: 0 auto;`, I will create a class `block` with this property.

**CSS**
{% highlight css %}
.block {
    width: 600px;
    margin: 0 auto;
}
{% endhighlight %}

**HTML**

{% highlight html %}
<div id="wrapper">
    <header>HEADER</header>
    <nav class="block">MENU<nav>
    <section class="block diaporama">DIAPORAMA</section>
    <section class="block content">CONTENU</section>
    <footer>FOOTER</footer>
</div>
{% endhighlight %}

Another good practice, it's to override this class.

**CSS**
{% highlight css %}
.block {
    width: 600px;
    margin: 0 auto;
}

.list .block {
    width: 300px;
}

{% endhighlight %}

**HTML**

{% highlight html %}
<div id="wrapper" class="list">
    <header>HEADER</header>
    <nav class="block">MENU<nav>
    <section class="block diaporama">DIAPORAMA</section>
    <section class="block content">CONTENU</section>
    <footer>FOOTER</footer>
</div>
{% endhighlight %}

One thing : When you override, try to not break the behavior of the class.

## Clearfix

Generally, I have a `clear` generic class. 

{% highlight css %}
.clear {
    clear:both;
}
{% endhighlight %}

Thanks to a great guy named [ayamflow](https://github.com/ayamflow), he redirect me to [Nicolas Gallagher's solution](http://nicolasgallagher.com/micro-clearfix-hack/).

The solution use `after` and `before` pseudo-class.

**CSS**
{% highlight css %}
.clear:before,
.clear:after {
    content: " ";
    display: table;
}

.clear:after {
    clear: both;
}

li {
    float:left;
}

{% endhighlight %}

**HTML**
{% highlight html %}
<ul class="clear">
    <li>Item #1</li>
    <li>Item #2</li>
    <li>Item #3</li>
</ul>
{% endhighlight %}

See [Nicolas Gallager's demo](http://nicolasgallagher.com/micro-clearfix-hack/demo/)

## Fix for custom fonts (Chrome)

Maybe you have notice some strange font rendering in your favorite browser. 
In Chrome browser, I notice my font a little bit bolder. The solution is to set the property `-webkit-font-smoothing`.

[MDN Font-Smooth documentation](https://developer.mozilla.org/en-US/docs/Web/CSS/font-smooth)


