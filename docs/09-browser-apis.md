---
comments: true
---

# Browser APIs

Now that you know the basics of JavaScript, it's time to see how it truly comes to life in the browser. In this session, you'll learn how JavaScript interacts with the web page through the Document Object Model (DOM), how to respond to user actions with events, and how to store data directly in the browser using the Web Storage APIs. With these tools, you'll move beyond static pages and start building fully interactive web applications.

## Preparation :books:

### The Document Object Model

In this video, we'll explore the Document Object Model - the structured representation of a web page that JavaScript can interact with. You'll learn how to access elements, change their content, attributes and styles - all through DOM methods that let you manipulate the page dynamically.

<iframe title="The Document Object Model" class="video" src="https://drive.google.com/file/d/1xqBVzTNCz4Dsxw0u3hfd6kTZSikX7prk/preview" allow="autoplay" allowfullscreen></iframe>

For a written reference, check out W3Schools' resources:

- [DOM intro](https://www.w3schools.com/js/js_htmldom.asp)
- [DOM methods](https://www.w3schools.com/js/js_htmldom_methods.asp)
- [Accessing DOM elements](https://www.w3schools.com/js/js_htmldom_elements.asp)
- [Changing HTML](https://www.w3schools.com/js/js_htmldom_html.asp)
- [Changing CSS](https://www.w3schools.com/js/js_htmldom_css.asp)

### Events

In the next video, we'll explore DOM events - how JavaScript can respond to user actions and browser-triggered events on a web page. You'll learn how to detect events like clicks, key presses, and pointer movements, and how to handle them using event listeners to make your pages interactive.

<iframe title="Events" class="video" src="https://drive.google.com/file/d/1QJZbuBjlMQjoFWMNrMuz6mq1UfyFGsjP/preview" allow="autoplay" allowfullscreen></iframe>

MDN also has a good [introduction to events](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Scripting/Events), that is worth a read.

### Web Storage APIs

The Web Storage APIs let JavaScript store key/value pairs directly in the browser. This allows you to persist data across page reloads, without relying on the server. They're mostly used to store small amounts of data, allowing web pages to remember user preferences, save form inputs and track application state. In this video, we'll explore `localStorage` and `sessionStorage`, showing how to store data either permanently or just for the current session.

<iframe title="Web Storage APIs" class="video" src="https://drive.google.com/file/d/1fChy7l2hZLeKegzu0yV4XnOULb_u1sOj/preview" allow="autoplay" allowfullscreen></iframe>

If you want to learn more, MDN has [a good resource on the Web Storage APIs](https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API).

### Timing Functions

The browser-provided functions `setTimeout` and `setInterval` let you schedule code to run in the future. `setTimeout` runs a function once after a delay, while `setInterval` runs it repeatedly at a fixed interval. Watch the video below to see them in action!

<iframe title="Timing Functions" class="video" src="https://drive.google.com/file/d/1oqI_Lvy8Hs-hfUr1MLeiU2K2Nuf5HoUp/preview" allow="autoplay" allowfullscreen></iframe>

To learn more, visit MDNs resources on [setTimeout](https://developer.mozilla.org/en-US/docs/Web/API/Window/setTimeout) and [setInterval](https://developer.mozilla.org/en-US/docs/Web/API/Window/setInterval).

There are many more browser APIs to explore! If you want an overview of what you can do in the browser, take a look at this [list of web APIs from MDN](https://developer.mozilla.org/en-US/docs/Web/API).

## Exercises :writing_hand_tone2:

### Under Construction :construction:

<!-- ### Manipulating the DOM

Change the code so that the paragraph displays "Welcome!"

??? tip "Tip"
    - Find the element and change the `textContent`.

```html
<html>
    <head></head>
    <body>
        <p id="foo"></p>

        <script>
            // Your code here
        </script>

    </body>
</html>
```

??? note "Solution"
    ```js
    let paragraph = document.getElementById("foo")
    paragraph.textContent = "Welcome!"

    // OR

    let paragraph = document.querySelector("#foo")
    paragraph.textContent = "Welcome!"
    ```

### Execution Order

The website below has a bug. Figure out what is wrong and fix it! Notice that the JavaScript file is in a separate tab.

=== "index.html"
    ```html
    <html>
        <head>
            <script src="main.js"></script>
        </head>
        <body>
            <h1>Hello, World!</h1>
        </body>
    </html>
    ```
=== "main.js"
    ```js 
    const heading = document.querySelector("h1")
    heading.textContent = "Hello, JavaScript!"
    ```

??? note "Solution"
    ```html
    <html>
        <head></head>
        <body>
            <h1>Hello, World!</h1>
            <script src="main.js"></script>
        </body>
    </html>

     <!-- OR -->
    
    <html>
        <head>
            <script src="main.js" defer></script>
        </head>
        <body>
            <h1>Hello, World!</h1>
        </body>
    </html>
    ```

### Passenger Counter App

You have been hired by DSB to create a passenger counter application for train conductors. It should display the current passenger count and have a button to increment it. Since conductors may work on multiple trains during a shift, make sure the count can be reset.

??? note "Solution"
    ```html
    <html>
        <head></head>
        <body>
            <p>Passenger Count: <span>0</span></p>
            <button id="increment">+</button>
            <button id="reset">Reset</button>

            <script>
                const countElement = document.querySelector("span")
                const incrementBtn = document.querySelector("#increment")
                const resetBtn = document.querySelector("#reset")

                let count = 0
                countElement.textContent = count

                incrementBtn.addEventListener("click", () => {
                    count++
                    countElement.textContent = count
                })

                resetBtn.addEventListener("click", () => {
                    count = 0
                    countElement.textContent = count
                })
            </script>
        </body>
    </html>
    ```

### Persisting Data

Make sure that train conductors can't accidentally lose the count when refreshing the page or closing the browser tab.

??? tip "Tips"
    - `localStorage` stores the value as a string. Convert it to a number (e.g. using the `Number()` function) to make sure that you don't fall victim to unexpected type coercion!
    - You can edit and keep track of the stored data using the browsers DevTools ("Application > Storage").

??? note "Solution"
    ```html
    <html>
        <head></head>
        <body>
            <p>Passenger Count: <span>0</span></p>
            <button id="increment">+</button>
            <button id="reset">Reset</button>

            <script>
                const countElement = document.querySelector("span")
                const incrementBtn = document.querySelector("#increment")
                const resetBtn = document.querySelector("#reset")

                let storedCount = localStorage.getItem("count")
                let count

                if (storedCount != null) {
                    count = Number(storedCount)
                } else {
                    count = 0
                }

                countElement.textContent = count

                incrementBtn.addEventListener("click", () => {
                    count++
                    localStorage.setItem("count", count)
                    countElement.textContent = count
                })

                resetBtn.addEventListener("click", () => {
                    count = 0
                    localStorage.setItem("count", count)
                    countElement.textContent = count
                })
            </script>
        </body>
    </html>
    ```

### A Keyboard Keyboard!

The keyboard below is almost done, but the event handling is missing. Fix it!

??? tip "Tips"
    - 

??? note "Solution"
    ```html
    const buttons = document.querySelectorAll("button")

    document.addEventListener("keydown", event => {
        const key = event.key
        if (key < "1" || key > "9" || event.repeat) return
        playSound(key)
        buttons[key - 1].classList.add("active")
    })

    document.addEventListener("keyup", event => {
        const key = event.key
        if (key < "1" || key > "9") return
        buttons[key - 1].classList.remove("active")
    })

    for (const btn of buttons) {
        btn.addEventListener("pointerdown", event => {
            playSound(event.target.textContent)
        })
    }
    ```

### BMI Calculator

Create a simple BMI (Body Mass Index) calculator using HTML and JavaScript. The calculator should:

- Allow the user to input their weight in kilograms and height in meters.
- Display the calculated BMI when a button is clicked.
- Round the result to one decimal place.

??? tip "Tips"
    - BMI = weight(kg) / height(m)²
    - Use the `value` property to get an input field's content.
    - Consider using `Number()` to convert input values from strings to numbers.
    - `toFixed(n)` returns a number as a string with `n` number of decimal places.

??? note "Solution"
    ```html
    <html>
        <head></head>
        <body>
            <h1>BMI Calculator</h1>
            <label>Weight (kg): <input id="weight" type="number" /></label>
            <label>Height (m): <input id="height" type="number" /></label>
            <button>Calculate BMI</button>
            <p>Your BMI is: <span >-</span></p>

            <script>
                const btn = document.querySelector("button")
                const result = document.querySelector("span")
                const weightInput = document.querySelector("#weight")
                const heightInput = document.querySelector("#height")

                btn.addEventListener("click", calculateBMI)

                function calculateBMI() {
                    const weight = Number(weightInput.value)
                    const height = Number(heightInput.value)

                    if (weight > 0 && height > 0) {
                        const bmi = weight / (height * height)
                        const roundedBMI = bmi.toFixed(1)
                        result.textContent = roundedBMI
                    } else {
                        result.textContent = "Invalid input"
                    }
                }
            </script>
        </body>
    </html>
    ```

### Hide and Seek

### Image Switcher

### A Color Picker

The color picker below is almost done, but the event handling has not yet been set up. Finish it!

```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8" />
        <title>Color Picker App</title>
        <style>
            * {
                margin: 0px;
                padding: 0px;
                box-sizing: 0px;
            }

            body {
                display: flex;
                height: 100dvh;
                font-family: Arial;
                justify-content: center;
                align-items: center;
            }

            .container {
                text-align: center;
                padding: 2rem;
                border-radius: 1rem;
                background-color: rgba(255, 255, 255, 0.8);
                box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
            }

            .controls {
                margin-top: 1rem;
                display: flex;
                flex-direction: column;
                gap: 1rem;
                align-items: center;
            }
        </style>
    </head>
    <body>
        <div class="container">
            <h1>Color Picker</h1>
            <div class="controls">
                <label> R: <input type="number" value="255" /> </label>
                <label> G: <input type="number" value="255" /> </label>
                <label> B: <input type="number" value="255" /> </label>
                <button id="randomColor">Random Color</button>
            </div>
        </div>

        <script>
            const inputs = document.querySelectorAll("input")
            const randomColorBtn = document.getElementById("randomColor")

            function updateUI(r, g, b) {
                document.body.style.background = "rgb(" + r + ", " + g + ", " + b + ")"
                inputs[0].value = r
                inputs[1].value = g
                inputs[2].value = b
            }

            function clampInput(e) {
                e.target.value = Math.max(0, Math.min(e.target.value, 255))
            }

            function randomColorIntensity() {
                return Math.floor(Math.random() * 256)
            }

            // Your code here

        </script>
    </body>
</html>
```

??? tip "Tip"
    - Notice that the input fields have been stored in an array. It will probably be a good idea to loop through it when adding the event listeners!

??? note "Solution"
    ```js
    for (const input of inputs) {
        input.addEventListener("input", e => {
            clampInput(e)
            updateUI(inputs[0].value, inputs[1].value, inputs[2].value)
        })
    }

    randomColorBtn.addEventListener("click", () => {
        updateUI(randomColorIntensity(), randomColorIntensity(), randomColorIntensity())
    })
    ```

### InnerHTML

### Live Character Counter

### Mobile Navigation

A common responsive design pattern is to replace the navigation bar on smaller screens with a menu button that, when clicked, reveals a navigation drawer.

The website below follows this pattern, but the JavaScript is missing. Fix it!

Make sure you write JavaScript that:

- Activates and deactives the `nav` element.
- Toggles the menu button between `✖` when open and `☰` when closed.
- Closes the navigation drawer when scrolling occurs.

??? tip "Tips"
    - According to the media query, the menu button is only visible on screens with a maximum width of 640px.
    - The menu button does not respond to button clicks. Create a "click" eventlistener for the button.
    - You can access the collection of class attributes of an element with [the classList property](https://developer.mozilla.org/en-US/docs/Web/API/Element/classList).
    - The styles has rules for `nav` elements with an `active` class attached. Toggle the `active` class on the `nav` element when the menu button is clicked.
    - Use `classList.contains` to determine whether to set the menu button's textContent to `✖` or `☰`.
    - On the [scroll event](https://developer.mozilla.org/en-US/docs/Web/API/Document/scroll_event), remember to set the menu button's textContent to `☰`.

=== "index.html"
    ```html
    <html>
        <head>
            <meta name="viewport" content="width=device-width, initial-scale=1.0" />
            <link rel="stylesheet" href="styles.css"></link>
        </head>
        <body>
            <header>
                <button id="menu-button">☰</button>
                <nav>
                    <ul>
                        <li><a href="#home">Home</a></li>
                        <li><a href="#services">Services</a></li>
                        <li><a href="#about">About</a></li>
                        <li><a href="#contact">Contact</a></li>
                    </ul>
                </nav>
                <h1>My Site</h1>
            </header>

            <main>
                <section>
                    <h2 id="home">Home</h2>
                </section>
                <section>
                    <h2 id="services">Services</h2>
                </section>
                <section>
                    <h2 id="about">About</h2>
                </section>
                <section>
                    <h2 id="contact">Contact</h2>
                </section>
            </main>
            <script src="main.js"></script>
        </body>
    </html>
    ```
=== "styles.css"
    ```css
    :root {
        --color-primary: #2196f3;
        --color-secondary: #b0bdc9;
        --color-active: white;
        --color-links: black;
    }

    * {
        margin: 0px;
        padding: 0px;
        box-sizing: border-box;
    }

    body {
        font-family: "Segoe UI";
    }

    header {
        display: flex;
        justify-content: space-between;
        font-weight: bold;
        background: var(--color-primary);
        align-items: center;
        height: 75px;
        padding: 1rem;
        min-width: 340px;
    }

    nav ul {
        display: flex;
        list-style: none;
    }

    nav a {
        text-decoration: none;
        color: var(--color-links);
        padding: 1rem;
        display: block;
    }

    nav a:hover {
        color: var(--color-active);
    }

    #menu-button {
        display: none;
        border: none;
        background: none;
        cursor: pointer;
        font-size: 1.5rem;
    }

    section { 
        padding: 1rem;
        height: 100dvh;
        width: 100%;
    }

    @media (max-width: 640px) {
        nav ul {
            display: flex;
            top: 75px;
            position: absolute;
            left: -100%;
            flex-direction: column;
            padding-inline: 2rem;
            min-height: calc(100dvh - 75px);
            background: var(--color-primary);
            transition: left 0.5s ease;
        }

        nav.active ul {
            left: 0;
        }

        #menu-button {
            display: block;
        }
    }
    ```
??? note "Solution"
    ```js
    const menuButton = document.querySelector("#menu-button")
    const nav = document.querySelector("nav")

    menuButton.addEventListener("click", () => {
        nav.classList.toggle("active")

        if (nav.classList.contains("active")) {
            menuButton.textContent = "✖"
        } else {
            menuButton.textContent = "☰"
        }
    })

    document.addEventListener("scroll", () => {
        nav.classList.remove("active")
        menuButton.textContent = "☰"
    })
    ```

### Toggle With Loop

### Timings

### SetInterval

### A Grocery List + Persistence

### Form Validation

### Count Down

### Clock

### Small Game
 -->
