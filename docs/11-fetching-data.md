---
comments: true
---

# Fetching Data

As the final topic of the course, we'll explore how to retrieve data from web servers and dive into JSON - the most widely used format for exchanging data between servers and web applications.

## Preparation :books:

### JSON

> Video coming soon...

### Fetch

> Video coming soon...

## Exercises :writing_hand_tone2:

### Hello, Fetch!

Create a new folder with the two files below (`index.html` & `message.txt`).

Write the `solution.js` script, that loads in the content of the text file and shows it in the paragraph.

??? tip "Tips"
    - For security reasons, browsers block `fetch` from reading local files directly from your hard drive. To load files with `fetch`, you need to serve them via a local or remote web server (e.g., using Live Server).
    - Use the `fetch` function with the URL of the resource you want to load.
    - When you call `fetch`, the browser doesn't get the result right away. Instead, you use `.then(...)` and pass a function that tells the browser what to do when the result arrives.
    - The function you pass into `.then(...)` recieves a response object. To get the actual text from that object, call `response.text()`. This function also works in the background. 
    - JavaScript allows you to chain background tasks using `.then(...)`. Each `.then(...)` handles the result of the previous step. E.g.: 
        ```
        fetch("your-url")
            .then(response => response.text())
            .then(text => ...)
        ```

=== "index.html"
    ```html
    <html>
        <head>
            <title>Hello Fetch!</title>
            <script src="solution.js" defer></script> <!-- Write this script! -->
        </head>
        <body>
            <h1>Load Text from a File</h1>
            <p id="messageContainer"></p>
        </body>
    </html>
    ```
=== "message.txt"
    ```txt
    Hello, Fetch!
    ```

??? note "Solution"
    ```js
    fetch("message.txt")
        .then(response => response.text())
        .then(text => {
            const container = document.querySelector("#messageContainer")
            container.textContent = text
        })
    ```

### Reusing HTML

Last time you created a NavBar, you had to write the same HTML on every page. That meant that whenever you wanted to make a change to the NavBar, you had to update it on multiple pages - which isn't very efficient. There are a few ways to solve this. A simple approach is to store the HTML for the NavBar in a separate file and fetch it wherever it's needed. Try that using the code below.

??? tip "Tip"
    - The `text` method of a `Response` object reads the entire body as a plain string, regardless of whether the content is plain text, HTML, or any other text-based format.

=== "index.html"
    ```html
    <html>
        <head>
            <title>Reusing HTML!</title>
            <script src="solution.js" defer></script> <!-- Write this script! -->
            <link rel="stylesheet" href="styles.css"/>
        </head>
        <body>
        <div id="navContainer"></div>
        </body>
    </html>
    ```
=== "nav.html"
    ```html
    <nav>
        <ul>
            <li><a href="index.html">Home</a></li>
            <li><a href="services.html">Services</a></li>
            <li><a href="about.html">About</a></li>
            <li><a href="contact.html">Contact</a></li>
        </ul>
    </nav>
    ```
=== "styles.css"
    ```css
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
    ```

??? note "Solution"
    ```js
    fetch("nav.html")
        .then(response => response.text())
        .then(html => {
            const container = document.querySelector("#navContainer")
            container.innerHTML = html
        })
    ```

### Highlighting The Active Page

<img style="display: block; margin: auto;" src="https://github.com/KasperKnop/WEB1/blob/main/resources/navbar.png?raw=true" alt="Highlighting The Active Page">

When we reused the same NavBar HTML across multiple pages, all links look the same. To improve the user experience, it's common to highlight the link that corresponds to the current page.

Modify the NavBar so that the link for the current page has the `active` class applied.

??? tip "Tips"
    - You can use `window.location.pathname.split("/").pop() || "index.html"` to get the current page.
    - You will have to loop through all of the links in the NavBar and check if the `href` attribute matches the current page. Add the `active` class to the link if it does.

??? note "Solution"
    ```js
    fetch("nav.html")
        .then(response => response.text())
        .then(html => {
            const container = document.querySelector("#navContainer")
            container.innerHTML = html

            const currentPage = window.location.pathname.split("/").pop() || "index.html"

            const links = container.querySelectorAll("nav a")

            for (const link of links) {
                if (link.getAttribute("href") === currentPage)
                    link.classList.add("active")
            }
        })
    ```

### Hello, JSON!

The code below contains a JSON string that describes a user. Parse it into an object and display the user's name and age on the webpage.

??? tip "Tip"
    - A JSON string is just text. To turn it into a real JavaScript object that you can work with, use the `JSON.parse` method.

```html
<html>
    <head>
        <title>Hello JSON!</title>
    </head>
    <body>
        <h1>User Info</h1>
        <p id="name"></p>
        <p id="age"></p>

        <script>
            const jsonString = '{"name":"Baby Yoda","age":50}'
            // Your code here
        </script>
    </body>
</html>
```

??? note "Solution"
    ```js
    const nameElement = document.querySelector("#name")
    const ageElement = document.querySelector("#age")

    const user = JSON.parse(jsonString)

    nameElement.textContent = user.name
    ageElement.textContent = user.age
    ```

### Lock Your Screen!

Have your friends ever left their laptop unlocked? Now is your chance to teach them an important lesson!

<img style="display: block; margin: auto; border-radius: 0.5rem; width: 80%;" src="https://github.com/KasperKnop/WEB1/blob/main/resources/lock-screen.png?raw=true" alt="Lock Your Screen!">

The website below can be used as a funny reminder when your friends forget to lock their screen. However, the JavaScript is incomplete and the images are missing - finish it!

- [Download the images](https://github.com/KasperKnop/WEB1/raw/refs/heads/main/resources/lock-your-screen-images.zip) and place the `img` folder in your project root.
- When the page is loaded, display a random image from `images.json` with its appropriate title and alt-text.
- Consider hosting the project on GitHub pages so that it is ready to be used :smiling_imp: 

Feel free to enhance the page - add new images, features, or any creative touches - and share your updated version with everyone in the comments below! :smile:

??? tip "Tips"
    - You could use `response.text()` and then parse the result with `JSON.parse()`, but the response object already provides a convenient `json` method that both reads the text and parses it into a JavaScript object.
    - When the JSON has been parsed, it is just a JavaScript object. Remember that you can access its properties using dot (`.`) notation.

=== "index.html"
    ```html
    <html>
        <head>
            <title>Lock Your Screen</title>
            <script src="script.js" defer></script>
            <link rel="stylesheet" href="styles.css"/>
        </head>
        <body>
            <h1></h1>
            <img>
            <p>Oopsie! Your screen's been wide open for <span id="timer">0</span> seconds and counting...</p>
        </body>
    </html>
    ```
=== "styles.css"
    ```css
    body {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        height: 100dvh;
        font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
        text-align: center;
        margin: 0px;
        color: white;
        background: black;
    }

    img {
        max-width: 50%;
    }

    h1 {
        font-size: 3rem;
    }

    p {
        font-size: 1.5rem;
    }
    ```
=== "images.json"
    ```json
    [
        { "src": "img/mister-t.jpg", "alt": "Mister T", "title": "Lock your screen, fool." },
        { "src": "img/elon-musk.jpg", "alt": "Elon Musk", "title": "Bro, even Tesla doors lock themselves." },
        { "src": "img/gordon.jpg", "alt": "Gordon Ramsay" , "title": "Are you an idiot sandwich??"},
        { "src": "img/zoidberg.png", "alt": "Zoidberg", "title": "Who else but Zoidberg would forget to lock their screen?" },
        { "src": "img/darth-vader.jpg", "alt": "Darth Vader", "title": "Darth Vader finds your lack of lock disturbing." },
        { "src": "img/son-i-am-disappoint.jpg", "alt": "Son I am disappoint", "title": "You no lock screen? Son I am disappoint." },
        { "src": "img/disappointed-cat.png", "alt": "Disappointed cat", "title": "Disappointed cat is disappointed you left your screen unlocked." },
        { "src": "img/yoda.jpg", "alt": "Yoda in combat", "title": "Lock your screen you must." },
        { "src": "img/orbweaver.jpg", "alt": "Orb Weaver in web", "title": "Lock your screen before you get tangled up" },
        { "src": "img/skunk.jpg", "alt": "Skunk in grass", "title": "It stinks that you didn't lock your screen." },
        { "src": "img/y-u-no.jpg", "alt": "Y U NO", "title": "Y U NO LOCK YOUR SCREEN" },
        { "src": "img/one-does-not-simply.jpg", "alt": "One does not simply", "title": "One does not simply leave your screen unlocked." },
        { "src": "img/greta.jpg", "alt": "Greta", "title": "How dare you leave your screen unlocked." },
        {
            "src": "img/southpark-ski-instructor.jpg",
            "alt": "Thumper the ski instructor",
            "title": "If you forget to lock your screen, you're gonna have a bad time!"
        },
        { "src": "img/bernie-sanders.jpg", "alt": "Bernie Sanders", "title": "Bernie Sanders is disappointed that you didn't lock your screen." },
        { "src": "img/disappointed_dog.jpg", "alt": "Disappointed dog", "title": "Doggo is sad that you forgot to lock your screen." },
        {
            "src": "img/golum.jpg",
            "alt": "Golum",
            "title": "Gollum is disappointed that you forgot to put your precious lock on the screen, my precious!"
        }
    ]
    ```
=== "script.js"
    ```js 
    const img = document.querySelector("img")
    const heading = document.querySelector("h1")
    const timer = document.querySelector("#timer")

    let start = Date.now()
    setInterval(() => timer.textContent = Math.floor((Date.now() - start) / 1000), 1000)

    function getRandomElement(array) {
        return array[Math.floor(Math.random() * array.length)]
    }

    // Your code here
    ```

??? note "Solution"
    ```js
    fetch("images.json")
        .then(response => response.json())
        .then(images => {
            const randomImage = getRandomElement(images)

            heading.textContent = randomImage.title
            img.src = randomImage.src
            img.alt = randomImage.alt
        })
    ```

### Your Favorite Show!

<img style="display: block; margin: auto; border-radius: 0.5rem; width: 80%;" src="https://github.com/KasperKnop/WEB1/blob/main/resources/breaking-bad.png?raw=true" alt="Your Favorite Show!">

Create a `tvshow.json` with the information of your favorite TV show! The JSON should include:

- Title (string)
- Number of seasons (number)
- Genre (array of strings)
- Main characters (array of objects with name, age and role)
- Whether the show is still running (boolean)

??? tip "Tip"
    - JSON is a strict subset of JavaScript object syntax: all property names and strings must be double-quoted, there can be no trailing commas, and you can only store strings, numbers, booleans, null and object and array literals.

??? note "Example solution"
    ```json
    {
        "title": "Breaking Bad",
        "seasons": 5,
        "genres": ["Crime", "Drama", "Thriller"],
        "mainCharacters": [
            { "name": "Walter White", "age": 50, "role": "Chemistry teacher / Meth kingpin" },
            { "name": "Jesse Pinkman", "age": 25, "role": "Meth cook / Partner" },
            { "name": "Skyler White", "age": 40, "role": "Walter's wife" },
            { "name": "Hank Schrader", "age": 43, "role": "DEA agent" }
        ],
        "isRunning": false
    }
    ```

### Meet the Cast!

Use the code below together with the `tvshow.json` file you just created to display the main characters of your favorite show in an unordered list.

??? tip "Tips"
    - Remember that you can use the `for...of` loop to to go through each item in an array
    - You can use `innerHTML` to insert HTML directly into a container, or you can create elements manually with `document.createElement` and append them with `append`.

```html
<html>
    <head>
        <title>TV Show Characters</title>
    </head>
    <body>
        <h1>Main Characters</h1>
        <ul id="characterList"></ul>
        <script>
            // Your code here
        </script>
    </body>
</html>
```

??? note "Solution"
    ```js
    fetch("tvshow.json")
        .then(response => response.json())
        .then(tvshow => {
            const listElement = document.querySelector("#characterList")

            for (const character of tvshow.mainCharacters) {
                listElement.innerHTML += "<li>" + character.name + "</li>"
            }
        })

    // OR

    fetch("tvshow.json")
        .then(response => response.json())
        .then(tvshow => {
            const listElement = document.querySelector("#characterList")

            for (const character of tvshow.mainCharacters) {
                const li = document.createElement("li")
                li.textContent = character.name
                listElement.append(li)
            }
        })
    ```

### Network Errors

When you send a real request to a server, a lot of things can go wrong. The user might lose their internet connection, the server might be unavailable, or the request might fail for other network-related reasons. In these situations, it’s important to let the user know what happened.

Use the `catch` method to notify the user about the network error in the example below.

```html
<html>
    <head>
        <title>Handling Network Errors</title>
    </head>
    <body>
        <p></p>
        <script>
            const paragraph = document.querySelector("p")
            fetch("https://this-domain-does-not-exist.xyz/data.json") // Simulating a server not responding
                .then(response => response.json())
                .then(result => (paragraph.textContent = result))
                // Your code here
        </script>
    </body>
</html>
```

??? note "Solution"
    ```js
    fetch("https://this-domain-does-not-exist.xyz/data.json")
    .then(response => response.json())
    .then(result => (paragraph.textContent = result))
    .catch(error => {
        paragraph.textContent = "Something went wrong while contacting the server."
    })
    ```

### Fetching Data From The Internet

<img style="display: block; margin: auto; border-radius: 0.5rem; width: 80%;" src="https://github.com/KasperKnop/WEB1/blob/main/resources/dog.png?raw=true" alt="Fetching Data From The Internet">

Create a website with a button that, when clicked, displays a random dog image from the [Dog API](https://dog.ceo/dog-api/). Make sure that network errors are handled. Use the code below as a starting point.

??? tip "Tip"
    - When working with a web API, take the time to read the documentation. Make sure you understand the available endpoints and the structure of the data you will receive.

```html
<html>
    <head>
        <title>Random Dog Viewer</title>
    </head>
    <body>
        <h1>Random Dog Viewer</h1>
        <button>Get Dog</button>
        <p id="errorMessage"></p>
        <img alt="Random dog" />

        <script>
            const btn = document.querySelector("button")
            const img = document.querySelector("img")
            const errorElement = document.querySelector("#errorMessage")

            // Your code here
        </script>
    </body>
</html>
```

??? note "Solution"
    ```js
    btn.addEventListener("click", () => {
        fetch("https://dog.ceo/api/breeds/image/random")
            .then(response => response.json())
            .then(data => {
                img.src = data.message
            })
            .catch(error => {
                errorElement.textContent = "Sorry! Could not fetch a dog image."
            })
    })
    ```

### HTTP Errors

The `catch` method only handles network errors automatically. If the server responds, it is not considered a network error - even if the response indicates a problem, such as the requested data not being found. These errors must be handled manually by checking the status of the request in the `response` object.

The code below asks for some data that the server cannot find. Update the code to handle this error appropriately.

??? tip "Tips"
    - Check `response.ok` to see if the server responded successfully. If it's false, throw a new error to be handled in the `.catch()` block.
    - You can also read the HTTP status code from `response.status`. HTTP status codes in the `200–299` range are considered `OK`. The “Not Found” error in this example corresponds to HTTP status code `404`.

```html
<html>
    <head>
        <title>Random Dog Viewer</title>
    </head>
    <body>
        <h1>Random Dog Viewer</h1>
        <button>Get Dog</button>
        <p id="errorMessage"></p>
        <img alt="Random dog" />
        <script>
            const btn = document.querySelector("button")
            const img = document.querySelector("img")
            const errorElement = document.querySelector("#errorMessage")

            btn.addEventListener("click", () => {
                fetch("https://dog.ceo/api/breeds/video/random") // The API does not contain videos!
                    .then(response => {
                        // Your code here
                        return response.json()
                    })
                    .then(data => {
                        img.src = data.message
                    })
                    .catch(error => {
                        errorElement.textContent = "Sorry! Could not fetch a dog image."
                    })
            })
        </script>
    </body>
</html>
```

??? note "Solution"
    ```js
    if (!response.ok) throw new Error("HTTP error " + response.status)
    ```

### Serializing an Object to JSON

The code below simulates a real POST request for submitting a comment to a server. The server expects the data to be sent as a JSON string in the request body. Convert the `comment` object into a JSON string before sending it.

??? tip "Tip"
    - While `JSON.parse` converts a JSON string into a JavaScript object, `JSON.stringify` does the reverse - it converts a JavaScript object into a JSON string.

```html
<html>
    <head>
        <title>Hello JSON!</title>
    </head>
    <body>
        <script>
            const comment = {
                username: "Max",
                text: "WEB1 is awesome!!",
                date: new Date().toISOString(),
            }

            const jsonString = // Your code here

            fetch("https://example.com/comments", {
                method: "POST",
                headers: { "Content-Type": "application/json" },
                body: jsonString,
            })
        </script>
    </body>
</html>
```

??? note "Solution"
    ```js
    const jsonString = JSON.stringify(comment)
    ```

### A Weather API

<img style="display: block; margin: auto; border-radius: 0.5rem; width: 80%;" src="https://github.com/KasperKnop/WEB1/blob/main/resources/weather-app.png?raw=true" alt="Fetching Data From The Internet">

As a last open-ended exercise, use the [Open-Meteo Weather API](https://open-meteo.com/) to create your own weather application! Feel free to share it in the comments below :smile:

??? tip "Tip"
    - The documentation for this API can feel a bit overwhelming. Focus on retrieving some simple data first!
    - Notice that the `API URL` is automatically generated as you configure the request in [the Open-Meteo documentation](https://open-meteo.com/en/docs).
    - Start by logging the parsed object to the console. This gives you a neat, collapsible view of all the properties you received.
    - As an example request, this fetches the current temperature for horsens: `https://api.open-meteo.com/v1/forecast?latitude=55.8607&longitude=9.8503&current=temperature_2m`.

??? note "Example Solution"
    ```html
    <html>
        <head>
            <meta charset="UTF-8" />
            <title>Horsens Weather</title>
            <style>
                body {
                    display: flex;
                    font-family: "Segoe UI", sans-serif;
                    background: linear-gradient(to bottom, #87ceeb, #f0f8ff);
                    justify-content: center;
                    align-items: center;
                    height: 100dvh;
                    margin: 0;
                }

                .weather-card {
                    background-color: rgba(255, 255, 255, 0.9);
                    padding: 2rem 3rem;
                    border-radius: 1rem;
                    box-shadow: 0 4px 15px rgba(0, 0, 0, 0.2);
                    text-align: center;
                }

                h1 {
                    margin-bottom: 1rem;
                    font-size: 2rem;
                    color: #333;
                }

                p {
                    font-size: 1.5rem;
                    margin: 0.5rem;
                    color: #555;
                }
            </style>
        </head>
        <body>
            <div class="weather-card">
                <h1>Horsens Weather</h1>
                <p>Temperature: <span id="temperature">--</span> °C</p>
                <p>Wind: <span id="windspeed">--</span> km/h</p>
            </div>

            <script>
                const temperatureElement = document.querySelector("#temperature")
                const windSpeedElement = document.querySelector("#windspeed")

                fetch("https://api.open-meteo.com/v1/forecast?latitude=55.8607&longitude=9.8503&current=temperature_2m,wind_speed_10m")
                    .then(response => {
                        if (!response.ok) throw new Error("HTTP error " + response.status)
                        return response.json()
                    })
                    .then(data => {
                        console.log(data)
                        temperatureElement.textContent = data.current.temperature_2m
                        windSpeedElement.textContent = data.current.wind_speed_10m
                    })
                    .catch(error => {
                        temperatureEl.textContent = "Could not fetch weather data."
                        console.error(error)
                    })
            </script>
        </body>
    </html>
    ```

### Nice Work!

You have now completed __ALL EXERCISES IN THE COURSE__! Congratulations. :partying_face: Take a moment to celebrate and feel free to comment on any of the lock screen and weather applications below :smile: