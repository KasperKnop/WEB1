---
comments: true
---

# Web Design

In this session, we will explore web design from a developer's perspective. While software engineers are not necessarily expected to become designers, a basic understanding of user experience (UX) and user interface (UI) design - including the ability to get into the mindset of the user - is essential for anyone involved in creating an interactive software product like a website. Moreover, front-end developers are often required to make design decisions in projects without dedicated designers.

## Preparation :books:

### Web Design Overview

In the video below, we will explore the core principles of user experience (UX) and user interface (UI) design, showing how thoughtful design decisions - like creating prototypes and planning layouts - can improve the way users interact with a website. You will also see how structured approaches, such as design systems and heuristic evaluation, help ensure consistency, clarity, and a better overall user experience.

<iframe title="Web Design Overview" class="video" src="https://drive.google.com/file/d/1WM2ab5K9deLL7LG3eDqNw6BofzIFb7un/preview" allow="autoplay" allowfullscreen></iframe>

Still unsure about what UX is and why it matters? Watch this short video on [the ROI of user experience](https://www.youtube.com/watch?v=O94kYyzqvTc){:target="\_blank"}.

If you want to learn more about usability testing - and maybe conduct one yourself - read this [article on usability testing 101](https://www.nngroup.com/articles/usability-testing-101/){:target="\_blank"}. You can also learn more about heuristic evaluation, by taking a look at this [article on 10 usability heuristics for user interface design](https://www.nngroup.com/articles/ten-usability-heuristics/){:target="\_blank"} by Jakob Nielsen, who also coined the term in the 90s.

If you are want more concrete graphical tips on designing your UI, you can take a look at this [article on safe visual design rules](https://anthonyhobday.com/sideprojects/saferules/){:target="\_blank"} and this [article on 16 little UI design tips that make a big impact](https://www.adhamdannaway.com/blog/ui-design/ui-design-tips){:target="\_blank"}.

### Accessibility

Accessibility is a fundamental part of user experience in web development because it ensures that all users, including those with disabilities, can effectively interact with your website. In the video below, we will introduce the fundamentals of web accessibility. You will learn how proper focus management, semantic HTML, ARIA attributes, meaningful link and image text, and thoughtful color and contrast choices all contribute to an inclusive web experience. We will also cover practical testing methods, including using developer tools to simulate visual impairments, running accessibility audits with Lighthouse, and understanding how screen readers interact with web content.

<iframe title="Accessibilty" class="video" src="https://drive.google.com/file/d/14OBv5ikiTgFslMAIMl5jfjjfJ12RnSi6/preview" allow="autoplay" allowfullscreen></iframe>

If you want to learn more, W3 Schools has created [a comprehensive tutorial on accessibility](https://www.w3schools.com/accessibility/index.php){:target="\_blank"}. This [article on how to review for accessibility](https://web.dev/articles/how-to-review) also gives a good brief overview.

## Exercises :writing_hand_tone2:

### Accessibility Audits

Perform accessibility audits (using Lighthouse in Chrome DevTools) on multiple websites of your choice. Identify good accessibility practices (passed audits) as well as areas for improvement.

Share the website with the lowest accessibility score in the comments and describe at least one thing that it could improve.

??? note "Example Solution"
    [Pokemon.com](https://www.pokemon.com){:target="\_blank"} - Score: 59 <br>
    Images either do not have an alt attribute or the text is redundant (automatically generated).

### Screen Reader & Keyboard

<img style="display: block; margin: auto; border-radius: 0.5rem;" src="https://github.com/KasperKnop/WEB1/blob/main/resources/via-trips.png?raw=true" alt="A preview of the VIA trips website">

You are about to experience temporary vision loss! Install a screen reader (e.g. [NVDA](https://assistivlabs.com/assistive-tech/screen-readers/nvda){:target="\_blank"}), and try to book a trip on [VIA Trips](https://kasperknop.github.io/via-trips/){:target="\_blank"}. The website is blurred and does not allow for mouse input. You can toggle the blur on and off by pressing "b" on the keyboard if you need a little help :wink:

Afterwards, try interacting with a website of your choice using only the keyboard. Then do it without looking, using a screen reader. Reflect on the main pain points of navigating, understanding and interacting with the content.

### Semantics

Update the markup below to use appropriate semantic HTML.

```html
<div class="header">
    <h1>My Website</h1>
</div>

<div class="navigation"><a href="#">Home</a> | <a href="#">About</a> | <a href="#">Contact</a></div>

<div class="main">
    <h2>Welcome</h2>
    This is a simple website for working with semantic HTML.
    <br /><br />
    <div class="button">Click Me</div>
    <div class="button">Another Button</div>
</div>

<div class="footer">
    <p>&copy; 2025 My Website</p>
</div>
```

??? note "Solution"
    ``` html
    <header>
    <h1>My Website</h1>
    </header>

    <nav>
        <a href="#">Home</a> | <a href="#">About</a> | <a href="#">Contact</a>
    </nav>

    <main>
        <h2>Welcome</h2>
        <p>This is a simple website for working with semantic HTML.</p>
        <button>Click Me</button>
        <button>Another Button</button>
    </main>

    <footer>
        <p>&copy; 2025 My Website</p>
    </footer>
    ```

### ARIA

The search form below needs better accessibility for screen readers.

-   Mark the search form as a distinct landmark so that screen readers can identify and navigate to it (you can read about the [search landmark on MDN](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Reference/Roles/search_role)).
-   Provide an appropriate label for the search input without adding a visible text label in the DOM.

```html
<form>
    <input type="search" name="search" />
</form>
```

??? note "Solution"
    ``` html
    <form role="search">
    <input
        type="search"
        name="search"
        aria-label="Search for your favorite content on our site" />
    </form>
    ```

### Descriptive Links

Turn the links in the paragraph below into good, accessible links.

```html
<p>
  To explore our cooking resources, check out our recipe collection 
  (<a href="/recipes">click here</a>), cooking tips 
  (<a href="/tips">click here</a>), and ingredient guides
  (<a href="/ingredients.pdf">learn more</a>)
</p>
```

??? note "Example Solution"
    ``` html
    <p>
        To explore our cooking resources, check out our 
        <a href="/recipes">recipe collection</a>, 
        <a href="/tips">cooking tips</a>, and 
        <a href="/ingredients.pdf">ingredient guides (PDF)</a>.
    </p>
    ```

### Enhancing Link Accessibility

You have been given a list of links, but their styling is quite poor. They are hard to identify as links, and there is no clear visual feedback indicating their state - e.g. focused, active, or already visited.

Assume that the existing CSS rules for the `a` selector cannot be modified. Modify the styles to provide a better user experience.

```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8" />
        <meta name="viewport" content="width=device-width, initial-scale=1.0" />
        <title>Styling Links</title>
        <style>
            a {
                text-decoration: none;
                color: #666666;
                outline: none;
            }

            /* Your code here */
            
        </style>
    </head>
    <body>
        <ul>
            <li><a href="">Animals</a></li>
            <li><a href="">Computers</a></li>
            <li><a href="">Diversity and inclusion</a></li>
            <li><a href="">Food</a></li>
            <li><a href="">Medicine</a></li>
            <li><a href="">Music</a></li>
        </ul>
    </body>
</html>
```

??? note "Example Solution"
    ``` css
    li a {
        text-decoration: underline;
        color: #00f;
    }

    a:visited {
        color: purple;
    }

    a:hover {
        color: orange;
    }

    a:focus {
        outline: auto black;
    }

    a:active {
        color: red;
    }
    ```

### Reaching 100 in Lighthouse

<img style="display: block; margin: auto; border-radius: 0.5rem;" src="https://github.com/KasperKnop/WEB1/blob/main/resources/100-accessibility.png?raw=true" alt="From 61 to 100 accessibility">

The [funion website (.zip)](https://github.com/KasperKnop/WEB1/raw/refs/heads/main/resources/the-funion.zip) has accessibility issues. Fix them without touching the CSS!

Try taking a look at the website first, to see if you can identify any issues yourself. After that, use Lighthouse to uncover more issues. You can also reference this checklist:

- The tab order causes the user to skip around a lot. Remove incorrect use of tabindex and change the tab order to the following:
    1. Navigation link
    2. Search
    3. Content links
    4. Footer
- Make sure proper semantic landmarks are used.
- Ensure that each landmark has a unique label when multiple landmarks of the same type are present on the page.
- Make sure images have proper descriptions.
- Make the link text more descriptive.
- Make sure all input fields are labeled.
- Give the document a title.
- Tell the browser the language of the website.

Can you get all the way to an accessibility score of 100?

??? note "Solution"
    ``` html
    <!DOCTYPE html>
    <html lang="en">
        <head>
            <meta charset="utf-8" />
            <link rel="stylesheet" href="styles.css" />
            <title>The Funion</title>
        </head>

        <body>
            <header>
                <div class="container">
                    <h1 class="logo">The Funion</h1>
                    <nav class="menu" aria-label="Main Navigation">
                        <ul>
                            <li><a href="#">Politics</a></li>
                            <li><a href="#">Business</a></li>
                            <li><a href="#">Entertainment</a></li>
                            <li><a href="#">Sports</a></li>
                            <li class="pull-right">
                                <a href="#" class="btn-search"><img src="./images/search.svg" alt="" />Search</a>
                            </li>
                        </ul>
                    </nav>
                </div>
            </header>

            <main class="container">
                <h2>Top story</h2>
                <article class="main-story">
                    <img class="float-right" src="./images/cat.jpg" alt="A cat staring menacingly off into space" />
                    <div class="info">
                        <h3 class="headline"><a href="#">Study shows 9 out of 10 cats quietly judging their owners as they sleep</a></h3>
                            GRAND RAPIDS, MI—Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna
                            aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure
                            dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident,
                            sunt in culpa qui officia deserunt mollit anim id est laborum.
                        </p>
                    </div>
                </article>
                <div class="side-by-side">
                    <div class="column">
                        <div class="tier-header">
                            <h2>In the news</h2>
                        </div>
                        <article>
                            <h3 class="headline">
                                <a href="#">Bee wonders if maybe everyone else is a drone and he's the only one who has it "figured out."</a>
                            </h3>
                            <img src="./images/bee.jpg" alt="A bee on top of a flower" />
                        </article>
                    </div>
                    <div class="column">
                        <article>
                            <img src="./images/telephone.jpg" alt="A red, London telephone booth" />
                            <div class="info">
                                <h3 class="headline"><a href="#">Telephone booths. How is this still a thing?</a></h3>
                                <p>
                                    LONDON—Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna
                                    aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute
                                    irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat
                                    non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
                                </p>
                            </div>
                        </article>
                    </div>
                </div>
                <div class="three-col">
                    <div class="tier-header">
                        <h2>Recommended</h2>
                    </div>
                    <div class="columns">
                        <article>
                            <img src="./images/dog.jpg" alt="A dog at a desk looks up at a laptop and mouse"/>
                            <div class="info">
                                <h3 class="headline"><a href="#">Turn man's best friend into man's best personal assistant.</a></h3>
                            </div>
                        </article>
                        <article>
                            <img src="./images/coffee.jpg" alt="A cup of coffee on a table"/>
                            <div class="info">
                                <h3 class="headline">
                                    <a href="#">San Franciscans are losing their minds over this third wave, artisanal, fair trade, handcrafted, locavore coffee.</a>
                                </h3>
                            </div>
                        </article>
                        <article>
                            <img src="./images/football.jpg" alt="A football player hands the ball off to another player" />
                            <div class="info">
                                <h3 class="headline"><a href="#">Sportsball team scores a touchpoint to win the big race.</a></h3>
                            </div>
                        </article>
                    </div>
                    <footer class="footer">
                        <div class="container">
                            <h3>Like the Funion? Consider joining our newsletter!</h3>
                            <input type="text" aria-label="Provide email for newsletter"/>
                            <button>Sign Up</button>
                            <nav>
                                <ul>
                                    <li><a href="#">Contact</a></li>
                                    <li><a href="#">Jobs</a></li>
                                    <li><a href="#">Legal</a></li>
                                </ul>
                            </nav>
                        </div>
                    </footer>   
                </div>
            </main>
        </body>
    </html>
    ```

### Skip Link

A score of 100 in accessibility does not equal perfect accessibility. There is still plenty of things, that Lighthouse does not take into consideration.

Let's improve the accessibility of the funion website further by providing a skip link to the user. It should take the user to the main landmark.

??? note "Example Solution"
    ``` html
    <header>
        <a href="#main-content" class="skip-link">Skip to the main content</a>
        <!--...-->
        <main id="main-content" class="container">
            <h2>Top story</h2>
            <!--...-->
        </main>
        <!--...-->
    </header>
    ```
    ```css
    .skip-link {
        position: absolute;
        top: -100px;
        background: #00f;
        color: #fff;
        padding: 8px;
        z-index: 100;
        }

    .skip-link:focus {
        top: 0;
    }
    ```

### Constrast Ratio

Testing the contrast ratio of text on your website is important. While tools like Lighthouse usually perform this check automatically, the browser cannot always determine the ratio accurately when backgrounds include transparency, images, or other complex effects.

<img style="display: block; margin: auto; border-radius: 0.5rem;" src="https://github.com/KasperKnop/WEB1/blob/main/resources/contrast-ratio.png?raw=true" alt="The contrast ratio feature in the DevTools color picker">

Visit [historian of the future](https://www.historianofthefuturex.com/), and check the contrast ratio of the text manually using the color picker in the DevTools.

### Usability Assessment

Using either an usability test or a heuristic evaluation, access the usabilty of a website.

Conducting a usability test requires careful preparation to get meaningful results. Start by familiarizing yourself with the website: explore its features, content, and navigation so you understand how it is intended to be used. Next, define clear tasks for the user that reflect real-world goals, such as finding information, completing a form, or making a purchase.

During the test, observe how users interact with the site, noting any difficulties, confusion, or errors. Avoid guiding the user; instead, let them attempt tasks on their own and ask follow-up questions to understand their thought process. You can even encourage them to think out loud. After the session, analyze your observations to identify usability problems and potential improvements.

A heuristic evaluation, on the other hand, is a quick way to uncover many usability problems without involving users. In this method, you review the website against established usability principles, such as Nielsen's 10 heuristics, to identify potential issues. This approach allows you to systematically check for problems like unclear navigation, inconsistent design, lack of feedback, and accessibility barriers.

Pick a website to evaluate. It can be one that drives you crazy when you use it, or one from the list below.

- [Userinyerface](https://userinyerface.com/)
- [Mit VIA](https://mit.via.dk/)
- [Awesome Store](https://www.tpgarcdemo.com/)

Feel free to share your findings in the comments :slight_smile:

### Prototyping & Wireframing

Still have some time? You'll soon be creating wireframes for your websites before moving on to implementation. This is a great opportunity to explore wireframing tools like [Balsamiq](https://balsamiq.com/), or the more advanced and widely used [Figma](https://www.figma.com/), which also allows you to create high-fidelity prototypes.

### Nice Work!

Take a few minutes to browse the Lighthouse audits and usability assessments shared by your classmates. Leave a comment if something catches your attention :slight_smile: