---
comments: true
---

# Under Construction :construction:

<!-- # Fetching Data

## Preparation :books:

### Fetch & JSON



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
    const container = document.querySelector("#messageContainer")

    fetch("message.txt")
        .then(response => response.text())
        .then(text => container.textContent = text)
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
    ```

??? note "Solution"
    ```js
    const container = document.querySelector("#navContainer")

    fetch("nav.html")
        .then(response => response.text())
        .then(result => {
            container.innerHTML = result
        })
    ```

### Highlighting The Active Destination

### Error Handling

Always check that your `fetch` request succeeds by inspecting `response.ok` or using a `try/catch` block to handle errors gracefully.

### Parson JSON Strings

### Fetching JSON Simple

### Lock Your Screen!

Have your friends ever left their laptop unlocked? Now is your chance to teach them an important lesson!

<img style="display: block; margin: auto; border-radius: 0.5rem; width: 80%;" src="https://github.com/KasperKnop/WEB1/blob/main/resources/lock-screen.png?raw=true" alt="Lock Your Screen!">

The website below can be used as a funny reminder when your friends forget to lock their screen. However, the JavaScript is incomplete and the images are missing - finish it!

- [Download the images](https://github.com/KasperKnop/WEB1/raw/refs/heads/main/resources/lock-your-screen-images.zip) and place the `img` folder in your project root.
- When the page is loaded, display a random image from `images.json` with its appropriate title and alt-text.
- Consider hosting the project on GitHub pages so that it is ready to be used :smiling_imp: 

Feel free to enhance the page - add new images, features, or any creative touches - and share your updated version with everyone in the comments below! :smile:

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

### Fetching JSON Advanced

### Fetching JSON Web Server

### Tjek lines -->