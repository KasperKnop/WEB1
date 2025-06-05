---
comments: true
---

# CSS Fundamentals

## Preparation :books:

In this session, we'll take our first steps into the world of CSS – Cascading Style Sheets. You'll learn how CSS helps us style and design web pages, from changing colors and fonts to adjusting alignments and spacing. Let’s make the web look good!

### CSS Basics

In the first video, we’ll explore the different ways you can apply CSS to your HTML, understand how inheritance works, and get familiar with some of the most common styling properties.

<iframe class="video" src="https://drive.google.com/file/d/1XvC8BMbY9lt2ZNJ-97nsWfANW2v4p-zW/preview" allowfullscreen></iframe>

You can read about the concepts in depth here:

[Adding CSS to our document](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Styling_basics/Getting_started#adding_css_to_our_document){:target="\_blank"} <br>
[Using common selectors](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Styling_basics/Getting_started#using_common_selectors){:target="\_blank"} <br>
[Inheritance](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_cascade/Inheritance){:target="\_blank"} <br>

### Colors

Next we’ll look at how to work with colors in CSS. We’ll cover three popular color formats: RGB, hex and HSL. You’ll also get a quick intro to hexadecimal numbers along the way.

<iframe class="video" src="https://drive.google.com/file/d/1fimNcpaDhcWL5bdxnCWXbR1ozwEkdjKD/preview" allowfullscreen></iframe>

If you want to know more, web.dev has [a good resource on colors](https://web.dev/learn/css/color){:target="\_blank"}. <br>

### The Box Model

Let's explore the CSS box model — a core concept for understanding how elements are sized and spaced on a web page. You’ll learn how content, padding, borders, and margins all fit together to shape every element on the screen.

<iframe class="video" src="https://drive.google.com/file/d/1jcLiZk18M21mjsUDfqBDMOYZrwh8Qunv/preview" allowfullscreen></iframe>

Web.dev also has [a good resource on the box model](https://web.dev/learn/css/box-model){:target="\_blank"} that you can check out.

### CSS Selectors & Specificity

Lastly, we’ll look at CSS selectors and how they let you target specific elements on your page. You’ll also learn about specificity and the cascade — the rules CSS uses to decide which styles win when there’s a conflict.

<iframe class="video" src="https://drive.google.com/file/d/1a9kIszPbCU5wx7ZjStNavVKGzGz1o3Ir/preview" allowfullscreen></iframe>

The concepts are also covered on web.dev:

[Selectors](https://web.dev/learn/css/selectors){:target="\_blank"} <br>
[The Cascade](https://web.dev/learn/css/the-cascade){:target="\_blank"} <br>
[Specificity](https://web.dev/learn/css/specificity){:target="\_blank"} <br>

## Exercises :writing_hand_tone2:

### Text Styling

### A Taste For Selectors!

To practice your CSS selector skills, try out [CSS Diner](https://flukeout.github.io/){:target="\_blank"} — a game where you have to select the right elements on a table using CSS!

### Box Model Exercise

### A Navbar

Build a horizontal navigation bar using the unordered list below. Style the bar with background color, spacing, and hover effects. Bonus points for creating a style that highlights the active page link. 

```html
<nav>
    <ul>
        <li><a href="index.html" class="active">Home</a></li>
        <li><a href="services.html">Services</a></li>
        <li><a href="about.html">About</a></li>
        <li><a href="contact.html">Contact</a></li>
    </ul>
</nav>
```

It might be worth noting that you can set the property `list-style-type` to `none` on list elements to remove their markers. Also, you can use the `display` property to set whether an element is treated as a block or inline box.

### CSS Zen Garden

### Need More Practice?
