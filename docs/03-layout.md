---
comments: true
---

# Layout

In this session, we'll dive into CSS layouts. You’ll learn how to make web pages adapt to various screen sizes while exploring the essential layout tools: Flexbox, Grid and media queries.

## Preparation :books:

### Responsive Web Design

HTML is naturally responsive, but once you start styling your website, that flexibility can break. Fixed widths and absolute positioning may look fine on your current device, but it's important to consider how your site appears across different screen sizes. Watch the video below for an introduction to the basics of responsive design, and learn how to work _with_ the browser rather than against it!

<iframe class="video" src="https://drive.google.com/file/d/1vxfyvjf9VOWt9B4lceF9-DJbGgYJ6qXo/preview" allowfullscreen></iframe>

If you want a written overview of todays session, MDN has created [an article on responsive web design](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/CSS_layout/Responsive_Design){:target="\_blank"}, that is worth a read.

### Flexbox

Flexbox is a one-dimensional layout model that makes it easier to arrange items in rows or columns. It creates a container that can adapt to different screen sizes, letting its child elements grow, shrink, or align neatly. Watch the video below to get an overview of the problems Flexbox tries to solve and how to use it.

<iframe class="video" src="https://drive.google.com/file/d/1F444WY1-zNNrNsWjrgKNiMUogZb0ov5d/preview" allowfullscreen></iframe>

CSS-Tricks has [a comprehensive guide on Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/){:target="\_blank"}, that covers everything from basic terminology and properties to useful examples and tricks. Give it a read to explore Flexbox in depth.

### CSS Grid

CSS Grid is a powerful two-dimensional layout model that organizes content into rows and columns, giving you precise control over both horizontal and vertical alignment. Because most websites naturally follow a grid structure, CSS Grid is especially well-suited for designing the overall layout of a page. Watch the video below to get a deeper understand of how it works.

<iframe class="video" src="https://drive.google.com/file/d/1a8hC3q84ci-Ekm1bSWo9sVSR7bdONvCX/preview" allowfullscreen></iframe>

You can also read about [CSS Grid on CSS-Tricks](https://css-tricks.com/snippets/css/complete-guide-grid/){:target="\_blank"}.

### Media Queries

Flexbox and Grid are inherently responsive and often sufficient for most layouts. However, media queries let you go further by applying styles conditionally based on factors like screen size or device features. They allow you to define breakpoints - specific screen widths where the design changes - so you can fine-tune layouts beyond what Flexbox and Grid can handle on their own.

<iframe class="video" src="https://drive.google.com/file/d/1uzgq1ngyuzjfiRUXAwSISthaJx-hzcuq/preview" allowfullscreen></iframe>

If you want to learn more about media queries and the various media features, take a look at [web.dev's article on media queries](https://web.dev/learn/design/media-queries){:target="\_blank"}.

The videos in this session didn't cover [basic CSS positioning](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/CSS_layout/Positioning){:target="\_blank"}, since its use cases have become less common with the rise of Flexbox and Grid. However, positioning remains very useful in certain small scale layout scenarios (e.g. for tooltips, modal dialogs, and fixed headers). I recommend reading up on it to get an understanding of the different positioning methods, such as `relative`, `absolute` and `fixed`.

## Exercises :writing_hand_tone2:

### Basic Responsiveness

You have been hired to make the website for the startup "EcoBottles" more responsive. Using the provided HTML code and [the product banner](https://github.com/KasperKnop/WEB1/blob/main/resources/eco-bottle.png?raw=true){:target="\_blank"}, please address the following issues:

-   **Text Width**: The text content currently extends across the entire screen on large displays. Please constrain the text to a maximum width of 1000 pixels.
-   **Image Responsiveness**: The product banner image overflows its container on smaller screens, forcing horizontal scrolling. Ensure the image scales down fluidly to fit within the viewport.
-   **Mobile Optimization**: The website lacks the proper viewport meta tag, which is essential for ensuring correct scaling and a good user experience on mobile devices. Please add the necessary tag to resolve this.

```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8" />

        <title>EcoBottle - Sustainable Water Bottles</title>
        <style>
            body {
                font-family: "Open Sans";
                background-color: #f4f7fc;
            }

            header {
                text-align: center;
                color: #2f72f0;
                font-size: 2rem;
                padding: 1rem;
            }

            h2 {
                color: #2c3e50;
            }

            footer {
                text-align: center;
                font-size: 0.8rem;
                color: #777;
            }
        </style>
    </head>
    <body>
        <header>
            <h1>Welcome to EcoBottle - Sustainable Water Bottles</h1>
        </header>

        <main>
            <section>
                <h2>What is EcoBottle?</h2>
                <p>
                    EcoBottle is a new kind of startup dedicated to reducing plastic waste by offering reusable, stylish, and highly durable water bottles. Our
                    mission is simple: make it easier for people everywhere to stay hydrated while making a positive impact on the planet. Each EcoBottle is
                    made from recycled materials, BPA-free, and designed to last for years.
                </p>

                <img src="/images/ecobottle.png" alt="EcoBottle products" />

                <p>
                    Whether you're an athlete, a student, or simply someone who wants to live more sustainably, EcoBottle is designed to fit seamlessly into
                    your lifestyle. With a range of sizes, colors, and accessories, our bottles are perfect for the office, the gym, or even a hiking trip.
                    Every purchase supports global clean water initiatives, so you're not just buying a bottle-you're contributing to meaningful change.
                </p>
            </section>

            <section>
                <h2>Why Choose EcoBottle?</h2>
                <p>
                    Traditional single-use plastic bottles contribute millions of tons of waste to our oceans and landfills each year. By switching to
                    EcoBottle, you're helping cut down on that waste while enjoying a healthier, more convenient alternative. Our bottles are not only
                    environmentally friendly but also engineered for performance, keeping your drinks hot or cold for hours.
                </p>
                <p>
                    EcoBottle focuses on simplicity and accessibility. You don't need to be an eco-expert to make a difference-just refill your bottle each day.
                    Small habits like this add up to massive positive change for the environment. Plus, we've made sure our bottles are affordable and backed by
                    a lifetime warranty to give you peace of mind.
                </p>
                <p>
                    Beyond functionality, EcoBottle is also about style and self-expression. With customizable sleeves and engraved options, you can make your
                    EcoBottle truly your own. It's more than a product-it's a movement to shift how we think about everyday consumption.
                </p>
            </section>

            <section>
                <h2>Simple Steps to Get Started</h2>
                <ul>
                    <li>
                        <strong>Order your EcoBottle:</strong> Visit our online shop and choose the size and style that best fits your lifestyle. We offer free
                        shipping on all first-time orders.
                    </li>
                    <li>
                        <strong>Start using it daily:</strong> Replace disposable bottles with your EcoBottle. Refill it at home, at work, or at refill stations
                        around your city.
                    </li>
                    <li>
                        <strong>Track your impact:</strong> Use our mobile app to log how many single-use bottles you've saved from landfills and oceans. You'll
                        see your personal contribution to reducing plastic waste.
                    </li>
                    <li>
                        <strong>Customize your bottle:</strong> Add a protective sleeve, a stainless-steel straw, or even a custom engraving to make it unique.
                        Your EcoBottle can be as individual as you are.
                    </li>
                    <li>
                        <strong>Spread the word:</strong> Encourage friends, family, and coworkers to join the movement. Every EcoBottle sold supports clean
                        water projects in underserved communities worldwide.
                    </li>
                </ul>
            </section>
        </main>

        <footer>©2025 EcoBottle Inc. All rights reserved.</footer>
    </body>
</html>
```

### Flexbox Froggy

Practice your flexbox skills by playing [Flexbox Froggy](https://flexboxfroggy.com/){:target="\_blank"}!

Pay attention to how properties like justify-content, align-items, and flex-direction affect the placement of the frogs and try to explain in your own words what each property does.

### Tag Arrangement

Using the code below as a starting point, create a layout for the tags, that resembles the image below.

<img style="display: block; margin: auto; border-radius: 0.5rem;" src="https://github.com/KasperKnop/WEB1/blob/main/resources/pasta-solution-flex.png?raw=true">

```html
<html>
<head>
    <style>
        body {
            font: 1.2em / 1.5 sans-serif;
            background: #eee;
        }

        .recipe {
            background: #fff;
            border-radius: 12px;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
            padding: 1rem;
            max-width: 350px;
        }

        p {
            margin-bottom: 0px;
        }

        img {
            max-width: 100%;
            border-radius: 12px;
        }

        .recipe h2 {
            margin-top: 0;
            margin-bottom: 0.5rem;
            text-align: center;
        }

        .tags {
            list-style: none;
            padding: 0px;
            margin: 0.25rem 0.25rem 1rem 0.25rem;
        }

        .tags>li {
            background: #e4ffe0;
            color: #305a24;
            padding: 0.25rem 0.75rem;
            border-radius: 12px;
            font-size: 0.85rem;
        }

        .tags {
            /* YOUR CODE HERE */
        }
    </style>
</head>

<body>
    <div class="recipe">
            <h2>Pasta Primavera</h2>
            <ul class="tags">
                <li>Vegetarian</li>
                <li>Vegan</li>
                <li>Gluten-free</li>
                <li>Healthy</li>
                <li>Light</li>
                <li>Seasonal</li>
                <li>Italian</li>
                <li>Comfort food</li>
                <li>Quick meal</li>
                <li>Family-friendly</li>
            </ul>
            <img src="https://raw.githubusercontent.com/KasperKnop/WEB1/refs/heads/main/resources/pasta-primavera.png">
        <p>A light and fresh italian pasta dish with seasonal vegetables.</p>
    </div>
</body>
</html>
```

??? note "Example Solution"
    ```css
    tags {
        display: flex;
        flex-wrap: wrap;
        gap: 0.25rem;
    }
    ```

### Navigation Bar With Flexbox

Reimplement the navigation bar from last week using Flexbox. Try to make it look the same:

<img style="display: block; margin: auto;" src="https://github.com/KasperKnop/WEB1/blob/main/resources/navbar.png?raw=true">

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

??? note "Example Solution"
    ```html
    <html>
        <head>
            <style>
                nav {
                    font-family: sans-serif;
                    font-weight: bold;
                    background: #2196f3;
                }

                nav ul {
                    padding: 0px;
                    display: flex;
                    flex-wrap: wrap;
                    justify-content: center;
                    list-style: none;
                }

                nav a {
                    text-decoration: none;
                    color: white;
                    padding: 1rem;
                    display: block;
                }

                nav a:hover {
                    background: #1976d275;
                }

                nav a.active {
                    background: #1976d2;
                }
            </style>
        </head>
        <body>
            <nav>
                <ul>
                    <li><a href="index.html" class="active">Home</a></li>
                    <li><a href="services.html">Services</a></li>
                    <li><a href="about.html">About</a></li>
                    <li><a href="contact.html">Contact</a></li>
                </ul>
            </nav>
        </body>
    </html>
    ```

### Grid Garden

Learn the basics of CSS Grid with [Grid Garden](https://cssgridgarden.com/){:target="\_blank"}!

Focus on how grid-area, grid-template, and the fr unit work and try to explain it in your own words.

### Responsive Grids

Create a responsive grid of cards where all items keep the same size and the grid adapts to the viewport: more columns on wide screens, fewer on small screens.

Focus on the use of grid-template-columns, gap, and responsive patterns with repeat(), auto-fill/auto-fit and minmax().

Use the code below as a starting point.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width,initial-scale=1" />
    <title>Grid Exercise</title>
    <style>
        * {
            box-sizing: border-box;
        }

        body {
            font-family: Roboto, Arial;
            padding: 2rem;
            background: #f6f7fb;
        }

        .card {
            background: white;
            border-radius: 8px;
            box-shadow: 0 1px 3px rgba(0, 0, 0, 0.08);
            display: grid;
            place-items: center;
            font-size: 2rem;
            aspect-ratio: 1 / 1;
        }

        .grid {
            /* YOUR CODE HERE */
        }
    </style>
</head>
<body>
    <main>
        <section class="grid">
            <article class="card">1</article>
            <article class="card">2</article>
            <article class="card">3</article>
            <article class="card">4</article>
            <article class="card">5</article>
            <article class="card">6</article>
            <article class="card">7</article>
            <article class="card">8</article>
            <article class="card">9</article>
        </section>
    </main>
</body>
</html>
```

??? note "Example Solution"
    ```css
    .grid {
        display: grid;
        gap: 1rem;
        grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    }
    ```

### The Holy Grail

The classic layout pattern below is known as the holy grail. It has a header, footer, left sidebar, right sidebar, and main content. Any left over space is allocated for the main content. Try implementing it with Grid.

<img style="display: block; margin: auto; border-radius: 0.5rem;" src="https://github.com/KasperKnop/WEB1/blob/main/resources/holy-grail.png?raw=true">

??? note "Example Solution"
    ```html
    <!DOCTYPE html>
    <html>
    <head>
        <style>
            body {
                margin: 0;
                font-family: sans-serif;
                font-size: 4rem;
                text-align: center;
            }

            .wrapper {
                display: grid;
                grid-template: auto 1fr auto / auto 1fr auto;
                height: 100vh;
                grid-template-areas:
                    "header header header"
                    "left main right"
                    "footer footer footer";
            }

            .section {
                padding: 2rem;
            }

            header {
                grid-area: header;
                background-color: #FFEDDB;
            }

            .left-side {
                grid-area: left;
                background-color: #CEF;
            }

            main {
                grid-area: main;
                background-color: #EAFDE7;
            }

            .right-side {
                grid-area: right;
                background-color: #FFDBFF;
            }

            footer {
                grid-area: footer;
                background-color: #FFEDDB;
            }
        </style>
    </head>
    <body>
        <div class="wrapper">
            <header class="section">Header</header>
            <div class="left-side section">Left Sidebar</div>
            <main class="section">Main Content</main>
            <div class="right-side section">Right Sidebar</div>
            <footer class="section">Footer</footer>
        </div>
    </body>
    </html>
    ```

### Stacking

The customer was very satisfied with your work on arranging tags earlier. However, now they want the tags on top of the image, as illustrated below!

<img style="display: block; margin: auto; border-radius: 0.5rem;" src="https://github.com/KasperKnop/WEB1/blob/main/resources/pasta-solution-grid.png?raw=true">

You might have to add a grid container, that can hold both the image and the list of tags, and use the `z-index` property to determine which element is rendered on top.

??? note "Example Solution"
    ```html
    <html>
    <head>
        <style>
            body {
                font: 1.2em / 1.5 sans-serif;
                background: #eee;
            }

            .recipe {
                background: #fff;
                border-radius: 12px;
                box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
                padding: 1rem;
                max-width: 350px;
            }

            p {
                margin-bottom: 0px;
            }

            img {
                max-width: 100%;
                border-radius: 12px;
                grid-area: stack;
            }

            .recipe h2 {
                margin-top: 0;
                margin-bottom: 0.5rem;
                text-align: center;
            }

            .tags {
                list-style: none;
                padding: 0px;
                margin: 0.25rem 0.25rem 1rem 0.25rem;
            }

            .tags>li {
                background: #e4ffe0;
                color: #305a24;
                padding: 0.25rem 0.75rem;
                border-radius: 12px;
                font-size: 0.85rem;
            }

            .tags {
                display: flex;
                flex-wrap: wrap;
                gap: 0.25rem;
                grid-area: stack;
                align-items: center;
                align-content: start;
                z-index: 1;
            }

            #grid {
                display: grid;
                grid-template-areas: "stack"
            }
        </style>
    </head>

    <body>
        <div class="recipe">
            <div id="grid">
                <h2>Pasta Primavera</h2>
                <ul class="tags">
                    <li>Vegetarian</li>
                    <li>Vegan</li>
                    <li>Gluten-free</li>
                    <li>Healthy</li>
                    <li>Light</li>
                    <li>Seasonal</li>
                    <li>Italian</li>
                    <li>Comfort food</li>
                    <li>Quick meal</li>
                    <li>Family-friendly</li>
                </ul>
                <img src="https://raw.githubusercontent.com/KasperKnop/WEB1/refs/heads/main/resources/pasta-primavera.png">
            </div>
            <p>A light and fresh italian pasta dish with seasonal vegetables.</p>
        </div>
    </body>
    </html>
    ```

### Introducing Breakpoints

Use media queries to make sure only the appropriate header is shown. Try not to touch the HTML (you will need to find a way to select each header individually). It's worth noting that you can hide an element by setting its `display` property to `none`.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Media Queries Exercise</title>
    <style>
        /* YOUR CODE HERE */
    </style>
</head>
<body>
    <h1>Mobile</h1>
    <h1>Tablet</h1>
    <h1>Desktop</h1>
</body>
</html>
```

??? note "Example Solution"
    ```css
    h1 {
      display: none;
    }

    @media (max-width: 480px) {
      h1:nth-of-type(1) {
        display: block;
      }
    }
    
    @media (min-width: 481px) and (max-width: 1024px) {
      h1:nth-of-type(2) {
        display: block;
      }
    }
    
    @media (min-width: 1025px) {
      h1:nth-of-type(3) {
        display: block;
      }
    }
    ```

### Improving Layouts

You now have the tools necessary to improve the layout of the websites that you made previously. Pick one (Star Pizza, your personal site, or CSS Zen Garden) and focus on finding good use cases for Flexbox, Grid and media queries. Share the link in the comments when you are done.

### Nice Work!

Take some time to browse through the layouts shared in the comments. Consider whether they have applied Flexbox, Grid, and media queries appropriately. If you can assess whether the right tools are chosen for each layout, you're on the right path to mastering responsive web design!