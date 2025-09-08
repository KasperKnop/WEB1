---
comments: true
---

# Layout

## Preparation :books:

### Responsive Web Design

<iframe class="video" src="https://drive.google.com/file/d/1vxfyvjf9VOWt9B4lceF9-DJbGgYJ6qXo/preview" allowfullscreen></iframe>

### CSS Grid

> Video on CSS Grid

### Flexbox

> Video on Flexbox

### Media Queries

> Video on Media Queries

## Exercises :writing_hand_tone2:

### Basic Responsiveness

You have been hired to make the website for the startup "EcoBottles" more responsive. Using the provided HTML code and [the product banner](https://github.com/KasperKnop/WEB1/blob/main/resources/eco-bottle.png?raw=true){:target="\_blank"}, please address the following issues:

- **Text Width**: The text content currently extends across the entire screen on large displays. Please constrain the text to a maximum width of 1000 pixels.
- **Image Responsiveness**: The product banner image overflows its container on smaller screens, forcing horizontal scrolling. Ensure the image scales down fluidly to fit within the viewport.
- **Mobile Optimization**: The website lacks the proper viewport meta tag, which is essential for ensuring correct scaling and a good user experience on mobile devices. Please add the necessary tag to resolve this.

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

        <main class="container">
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

### Maybe Exercise With Position

### Grid Garden

Learn the basics of CSS Grid with [Grid Garden](https://cssgridgarden.com/){:target="\_blank"}!

Focus on how grid-area, grid-template, and the fr unit work and try to explain it in your own words.

### FlexBox Froggy

Practice your flexbox skills by playing [Flexbox Froggy](https://flexboxfroggy.com/){:target="\_blank"}!

Pay attention to how properties like justify-content, align-items, and flex-direction affect the placement of the frogs and try to explain in your own words what each property does.

### One More Flexbox Exercise

### Media Queries Exercise

### Collapsible NavBar

### Common Layout Patterns

<!-- ### Layout Reflections

Consider the following questions:

- When would you use Flexbox vs Grid?
- How do media queries make a site responsive? -->