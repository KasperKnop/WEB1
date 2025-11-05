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

### Selecting List Items

Create an interactive list, where one element can be selected. Follow these rules:

- When a user clicks on a list item, it should become "active" by adding the active class to the element.
- Only one item should be active at a time.
- Clicking a new item should remove the active class from the previously selected one.
- If the active item is clicked, it should no longer be active.

Use the code below as a starting point.

```html
<html>
    <head>
        <title>An Interactive List</title>
    </head>
    <body>
        <ul>
            <li>Apples</li>
            <li>Bananas</li>
            <li>Cherries</li>
            <li>Dates</li>
        </ul>

        <style>
            li {
                cursor: pointer;
                padding: 0.5rem;
            }

            .active {
                background-color: #cce5ff;
                font-weight: bold;
            }
        </style>

        <script>
            // Your code here
        </script>
    </body>
</html>
```

??? tip "Tips"
    - Use document.querySelectorAll to select all list items.
    - Loop through the items and add a click event listener to each.
    - Use classList.add() and classList.remove() to manage the active class.
    - You can use document.querySelector(".active") to find the currently active item.
    - You can check what element invoked the click event with `event.target`.

??? note "Solution"
    ```html
    <html>
        <head>
            <title>Selecting List Items</title>
        </head>
        <body>
            <ul>
                <li>Apples</li>
                <li>Bananas</li>
                <li>Cherries</li>
                <li>Dates</li>
            </ul>

            <style>
                li {
                    cursor: pointer;
                    padding: 0.5rem;
                }

                .active {
                    background-color: #cce5ff;
                    font-weight: bold;
                }
            </style>

            <script>
                const items = document.querySelectorAll("li")

                for (const item of items) {
                    item.addEventListener("click", () => {
                        const current = document.querySelector(".active")
                        if (current) {
                            current.classList.remove("active")
                            if (current === event.target) return
                        }

                        item.classList.add("active")
                    })
                }
            </script>
        </body>
    </html>
    ```

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


### A Keyboard Keyboard!

The keyboard below is almost done, but the event handling is missing. Make it possible to use the keyboard with both the numbers on the keyboard and the mouse, and make sure to provide visual feedback that the key is pressed!

??? tip "Tips"
    - The `keydown` and `keyup` will be useful here.
    - Make sure that you are only responding to the keypresses 1-9.
    - You are going to work with arrays - both for the sounds and for the buttons. How does the array of buttons map to the key that was pressed? How does the `textContent` of the button map to the array of sounds?
    - The styles already has the visual feedback set up in the `active` class. You just need to use it!
    - To avoid triggering the same event repeatedly while a key is held down, you can use the `event.repeat` property.
    - Use the `pointerdown` event to respond immediately when the user presses, without waiting for them to lift their finger.

```html
<html>
    <head>
        <meta name="viewport" content="width=device-width, initial-scale=1.0" />
        <title>Keyboard Keyboard!</title>
        <style>
            body {
                color: #485042;
                display: flex;
                height: 100dvh;
                flex-direction: column;
                margin: 0;
                font-family: "Segoe UI";
                background-color: #aec2a0;
                justify-content: center;
                align-items: center;
            }

            #keyboard {
                display: flex;
                flex-wrap: wrap;
                justify-content: center;
                gap: 1rem;
                padding: 2rem;
                background: #dfdfdf;
                border-radius: 1rem;
                box-shadow: 0 4px 20px rgba(0, 0, 0, 0.3);
                margin: 1rem;
            }

            button {
                padding: 2rem;
                font-size: 2rem;
                border: none;
                border-radius: 8px;
                background-color: #fff;
                color: #485042;
                cursor: pointer;
                box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
                width: 100px;
                height: 100px;
                outline: none;
            }

            h1 {
                font-size: 6rem;
                text-align: center;
            }

            p {
                margin: 0.5rem;
            }

            #psst {
                font-size: 1.2rem;
                margin-top: 5rem;
                font-style: italic;
                text-align: center;
            }

            button:active,
            .active {
                box-shadow: none;
                border: 2px solid #dfdfdf;
            }
        </style>
    </head>
    <body>
        <h1>Keyboard Keyboard!</h1>
        <div id="keyboard">
            <button>1</button>
            <button>2</button>
            <button>3</button>
            <button>4</button>
            <button>5</button>
            <button>6</button>
            <button>7</button>
            <button>8</button>
            <button>9</button>
        </div>
        <div id="psst">
            ...Psst!:
            <p>2-3-4-2-6-6-5</p>
            <p>1-2-3-1-5-5-4-3-2</p>
            <p>2-2-4-2-4-5-3-2-1-1-5-4</p>
            <p>2-3-4-2-6-6-5</p>
            <p>1-2-3-1-8-3-4-3-2</p>
            <p>2-3-4-2-4-5-3-2-1-1-5-4</p>
        </div>
    </body>
</html>
<script>
    const sounds = [
        new Audio("https://github.com/KasperKnop/WEB1/raw/refs/heads/main/resources/sounds/c4.mp3"),
        new Audio("https://github.com/KasperKnop/WEB1/raw/refs/heads/main/resources/sounds/d4.mp3"),
        new Audio("https://github.com/KasperKnop/WEB1/raw/refs/heads/main/resources/sounds/e4.mp3"),
        new Audio("https://github.com/KasperKnop/WEB1/raw/refs/heads/main/resources/sounds/f4.mp3"),
        new Audio("https://github.com/KasperKnop/WEB1/raw/refs/heads/main/resources/sounds/g4.mp3"),
        new Audio("https://github.com/KasperKnop/WEB1/raw/refs/heads/main/resources/sounds/a4.mp3"),
        new Audio("https://github.com/KasperKnop/WEB1/raw/refs/heads/main/resources/sounds/b4.mp3"),
        new Audio("https://github.com/KasperKnop/WEB1/raw/refs/heads/main/resources/sounds/c5.mp3"),
        new Audio("https://github.com/KasperKnop/WEB1/raw/refs/heads/main/resources/sounds/d5.mp3"),
    ]

    function playSound(i) {
        if (sounds[i]) {
            sounds[i].currentTime = 0
            sounds[i].play()
        }
    }

    // Your code here
    
</script>
```

??? note "Solution"
    ```html
    const buttons = document.querySelectorAll("button")

    document.addEventListener("keydown", event => {
        const key = event.key
        if (key < "1" || key > "9" || event.repeat) return
        playSound(key - 1)
        buttons[key - 1].classList.add("active")
    })

    document.addEventListener("keyup", event => {
        const key = event.key
        if (key < "1" || key > "9") return
        buttons[key - 1].classList.remove("active")
    })

    for (const btn of buttons) {
        btn.addEventListener("pointerdown", event => {
            playSound(event.target.textContent - 1)
        })
    }
    ```

### Timings

### SetInterval

### A Grocery List + Persistence

### Form Validation

### Count Down

### Clock

### Small Game -->

