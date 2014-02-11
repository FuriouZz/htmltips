---
layout: default
title: Best practices - HTML
categories: best-practices
---

# {{ page.title }}

## Advices

* Use HTML5 tags : `<header>` `<footer>` `<section>` `<article>` `<nav>` `<audio>` `<video>`
* Use `class` is better than `ìd` for generic & repetitive content
* Use [HTML5Shiv](https://github.com/aFarkas/html5shiv) for old browsers

## Reuse `tags`

Sometimes, we are looking for a lot of stranges class name for identify a specific `tag`. I prefer to specify a `tag` thanks to its tag container. The `tag container indicate what type of content it will display.

{% highlight html %}
<header>
    <h1>Title</h1>
    <h2>Subtitle</h2>
</header>

<nav>
    <h3>Menu</h3>
    <ul>
        <li><h4>Menu Item #1</h4></li>
        <li><h4>Menu Item #2</h4></li>
        <li><h4>Menu Item #3</h4></li>
    </ul>
</nav>
{% endhighlight %}

I take example of titles. Generally we use `<h1>` `<h2>` until `<h6>`.
A title in the header has not the same styles of a title in a menu. But we can't use all heading tags for each title of a page.

{% highlight html %}
<header>
    <h1>Title</h1>
    <h2>Subtitle</h2>
</header>

<nav>
    <h1>Menu</h1>
    <ul>
        <li><h2>Menu Item #1</h2></li>
        <li><h2>Menu Item #2</h2></li>
        <li><h2>Menu Item #3</h2></li>
    </ul>
</nav>
{% endhighlight %}

## Reuse `class`

Sometime, I don't know how to name `class`. I see some site with lots of `class` without any sense and unreadable. It's like `tags` reuse your `class`.

**HTML**

{% highlight html %}
    <nav>
        <div class="header"></div>
        <ul class="content">
            <li>Menu Item #1</li>
            <li>Menu Item #2</li>
            <li>Menu Item #3</li>
        </ul>
        <div class="footer"></div>
    </nav>
    
    <article>
        <div class="header"></div>
        <div class="content"></div>
        <div class="footer"></div>
    </article>
{% endhighlight %}

**CSS**

{% highlight css %}
    nav .header  { /* my css */ }
    nav .content { /* my css */ }
    nav .footer  { /* my css */ }

    article .header  { /* my css */ }
    article .content { /* my css */ }
    article .footer  { /* my css */ }  
{% endhighlight %}
