---
comments: true
---

# Under Construction :construction:
<!-- 
# Fetching Data

## Preparation :books:

### Fetch & JSON



## Exercises :writing_hand_tone2:

### Fetching text

### Fetching HTML

### Parson JSON Strings

### Fetching JSON Simple

### Lock Your Screen!

=== "index.html"
    ```html
    <html>
        <head>
            <title>Lock Your Screen</title>
            <script src="script.js" defer></script>
            <link rel="stylesheet" href="styles.css"></link>
        </head>
        <body>
            <h1></h1>
            <img />
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

            heading.textContent = randomImage.fullcaption
            img.src = randomImage.src
            img.alt = randomImage.alt
        })
    ```

### Fetching JSON Advanced

### Fetching JSON Web Server

### Reuse HTML -->