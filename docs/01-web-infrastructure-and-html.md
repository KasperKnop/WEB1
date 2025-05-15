---
comments: true
---

# Web Infrastructure & HTML

## Preparation

### Web Infrastructure

> Video about web infrastructure

[How does the Internet work?](https://developer.mozilla.org/en-US/docs/Learn_web_development/Howto/Web_mechanics/How_does_the_Internet_work){:target="\_blank"} <br>
[How the web works](https://developer.mozilla.org/en-US/docs/Learn_web_development/Getting_started/Web_standards/How_the_web_works){:target="\_blank"} <br>

### Environment Setup

> Video about setting up VS Code

[Download VS Code](https://code.visualstudio.com/){:target="\_blank"}

### HTML Basics

> Video about HTML Basics

[Basic HTML Syntax](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Structuring_content/Basic_HTML_syntax){:target="\_blank"} <br>
[Web page metadata](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Structuring_content/Webpage_metadata){:target="\_blank"} <br>
[Headings and paragraphs](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Structuring_content/Headings_and_paragraphs){:target="\_blank"} <br>
[Emphasis and importance](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Structuring_content/Emphasis_and_importance){:target="\_blank"} <br>
[Lists](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Structuring_content/Lists){:target="\_blank"} <br>
[Creating links](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Structuring_content/Creating_links){:target="\_blank"} <br>
[HTML images](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Structuring_content/HTML_images){:target="\_blank"} <br>
[HTML table basics](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Structuring_content/HTML_table_basics){:target="\_blank"} <br>

### Semantic HTML

> Video about Semantic HTML

[Structuring documents](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Structuring_content/Structuring_documents){:target="\_blank"} <br>

---

## Exercises

### The Journey of a Web Request

What happens behind the scenes when you visit a website? Create a visual map of the web's underlying infrastructure — and share it with your peers!

1. Think about what’s involved when your browser loads a website. Some key elements might include: The browser, DNS, HTTP, routers, HTML...
2. Create a diagram of the interaction between the elements - either on pen and paper or using a drawing program such as [excalidraw](https://excalidraw.com/){:target="\_blank"}.
3. Upload an image of the diagram to [imgur](https://imgur.com/upload){:target="\_blank"}, and share it in the comment section below. The comments accepts some HTML, so you can use an `<img>` element to display it (don't forget to add the image extension to the URL!). You can use the preview tab to make sure that the image is working before posting it.

### Star Pizza

Congratulations - you are now the restaurant owner of Star Pizza!

1. Use the text below as a starting point for your website. Start by adding markup to it.
2. Add a catchy title to the website in the `<head>` element.
3. Add more items to the menu (e.g. pasta, beverages)
4. Organize menu items into groups with headlines (Pizzas, Pasta, and Beverages).
5. Use these [pizza images](https://github.com/KasperKnop/WEB1/raw/refs/heads/main/resources/star-pizza-images.zip) to create an appetizing menu for Star Pizza.
6. Use Paint or another picture editing tool to resize the images of pasta dishes and beverages and add these to this menu page.
7. Make image links for all images. Clicking on one should open a new window with a large version of the item clicked.

```
Star Pizza

At Star Pizza we use only quality ingredients and prepare the food
under hygienic conditions.

Dear Customer!
We can deliver food for your lunch break if your order at least 2 hours
before delivery.

Free delivery every day when buying for at least kr. 110,-.

Pizzas

1. Margarita (Tomato, Cheese)
2. Hawaii (Tomato, Cheese, Ham, Pineapple)
3. Milano (Tomato, cheese, Ham, Mushrooms)
4. Mamma Mia(Tomato, cheese, Ham, Pepperoni, Onions)
5. Pepperoni (Tomato, Cheese, Pepperoni, Pineapple)

Special offers
* Buy 2 family or 4 standard pizzas and get one 1½ liter Cola FREE.
* Buy 2 pizzas and get one serving of tzatziki FREE on pick-up.

Opening hours
Monday, Tuesday     15.00 - 22.00
Wednesday           15.00 - 22.00
Thursday, Friday    15.00 - 22.00
Saturday, Sunday    13.00 - 22.00
```

### An Early April's Fools!

Getting comfortable with your browser’s developer tools is an essential skill for any web developer. It lets you inspect, debug, and experiment with a websites code directly in the browser.

Use your browser’s developer tools to temporarily edit a real website and make it look like something unbelievable has happened!

1. Visit a real website — a news site, Wikipedia article, product page, etc. (Choose something with a lot of text and structure you can play with.)
2. Open your browser’s developer tools (Right-click > Inspect or press F12)
3. Modify the text, headlines, or images directly in the browser to create a fake but convincing piece of news.
4. Take a screenshot, [upload it to imgur](https://imgur.com/upload){:target="\_blank"}, and share it in the comment section below.

### Introduce Yourself!

Create your own personal website that the class can visit to get to know you!

Requirements:

-   A minimum of 3 HTML pages:
    -   index.html: Your homepage with an introduction and picture (optional).
    -   about.html: More details about who you are.
    -   interests.html: Hobbies, interests, or things you’re passionate about.
-   A shared navigation bar (on all pages) that lets users click between your pages.
-   Use of semantic HTML elements where appropriate (`<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<footer>`, etc.)
-   A table to organize information. It could be your weekly schedule, your favorite movies/games/books or something else entirely.
-   A footer with contact information and links to your social accounts. It is okay to put in fake data here if you want privacy.

### Hosting Your Site

A website without hosting is like a concert with no audience - let’s get your website online so the world can see it!

1. Create an account on [GitHub](https://github.com/signup){:target="\_blank"}.
2. In VS Code, click on the Source Control tab and select "Publish to Github" to publish a public repository.
3. Click the "Open on Github" popup.
4. On Github, go to "Settings" > "Pages". Go to "Branch", click on "None", select "main" and click "Save".
5. Wait a minute and refresh the page. The URL to your website should now appear at the top of the page.
6. Share the URL in the comment section below (again, HTML is supported, so you can use the `<a>` (anchor) element)!

As an alternative to Github Pages, you can use [Netlify Drop](https://app.netlify.com/drop){:target="\_blank"} - just drag and drop your project files, and your site will be live in seconds! It's free to use, though you'll need an account to keep your site password free and online permanently.

### Nice Work!

Take a few minutes to browse the images and personal websites your classmates have made. Click around, get to know them, and see how everyone approached the exercises in their own way. Leave a comment on a post if it caught your attention :slight_smile:

Remember that you can use your browser’s developer tools to inspect the source code and learn from the websites you are visiting!

---
