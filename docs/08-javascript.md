---
comments: true
---

# JavaScript

## Preparation :books:

### Foo

## Exercises :writing_hand_tone2:

### Hello, JavaScript!

In this session, the output of all exercises will be shown in the DevTools.

Start by creating an HTML document that includes an external JavaScrip file, that logs the message "Hello, JavaScript" to the console.

To make your workflow easier, open the HTML file with Live Server, and undock the console from the browser window — we won't need to view the web page itself during this session.

??? note "Example Solution"
    ```html
    <!DOCTYPE html>
    <html>
    <head>
        <script src="my-script.js"></script>
    </head>
    <body></body>
    </html>
    ```
    ```js
    console.log("Hello, JavaScript")
    ```

### Variables

### Constants

### Type Coercion

### Scope

### Debugging

### Objects

### Arrays

### Built in Objects

### Military Time

Military time represents the current time using the 24-hour format. For example, a value of 1700 means it's 5:00 PM.
Assuming that the user correctly provides a number between 0000 - 2359, write a function that determines whether the current time falls into one of the following categories:

-   Morning: Any time before 08:00 AM
-   School: Between 08:00 AM and 04:00 PM
-   Evening: Any time after 04:00 PM

```js
console.log(timeOfDay(prompt("Input military time (0000 - 2359)")))

// Your code here
```

??? note "Example Solution"
    ```js
    console.log(timeOfDay(prompt("Input military time (0000 - 2359)")))

    function timeOfDay(militaryTime) {
        if (militaryTime < 800) {
            return "Morning"
        } else if (militaryTime < 1600) {
            return "School"
        } else {
            return "Evening"
        }
    }
    ```

### Average

You're a Pokémon trainer that wants to find the average base stats of your team.
Complete the code so that it loops through all the pokémon's base stats, sums them up, and then calculates the average.

```js
let total = 0
let baseStats = [525, 395, 320, 490, 435, 600, 680]

console.log(getAverage(baseStats))

function getAverage(array) {
    // Your code here
}
```

??? note "Example Solution"
    ```js
    function getAverage(array) {
        total = 0
        for (let value of array) {
            total += value
        }
        return total / array.length
    }
    ```

### Loops & Objects

Loop through the array of Pokemon and log any fire Pokemon to the console.

```js
const pokemonList = [
    { name: "Charmander", type: "Fire" },
    { name: "Squirtle", type: "Water" },
    { name: "Pikachu", type: "Electric" },
    { name: "Vulpix", type: "Fire" },
    { name: "Growlithe", type: "Fire" },
    { name: "Geodude", type: "Rock/Ground" },
    { name: "Eevee", type: "Normal" },
    { name: "Abra", type: "Psychic" },
]
```

??? note "Example Solution"
    ```js
    for (let i = 0; i < pokemonList.length; i++) {
        if (pokemonList[i].type === "Fire") {
            console.log(pokemonList[i].name)
        }
    }
    ```

### Functions

### Calculator

### Binary Number Calculator?

### Mario Pyramid

<img style="display: block; margin: auto; border-radius: 0.5rem;" src="https://github.com/KasperKnop/WEB1/blob/main/resources/mario-reverse.gif?raw=true" alt="The Mario Pyramid!">

Recreate the famous pyramid from the Mario games using hashtags and console.log!

```js
function marioPyramid(height) {
    // your code here
}

marioPyramid(5)
/*
Expected output:
#
##
###
####
#####
*/
```

??? note "Example Solution"
    ```js
    function marioPyramid(height) {
        for (let i = 1; i <= height; i++) {
            let row = ""
            for (let j = 0; j < i; j++) {
                row += "#"
            }

            console.log(row)

        }
    }

    // OR

    function marioPyramid(height) {
        for (let line = "#"; line.length <= height; line += "#") console.log(line)
    }
    ```

### Mirror Mode!

If you have played Mario, you probably noticed that the game was mirrored in the previous exercise! This time, you should implement the real pyramid from Mario! Depending on how you have implemented the previous exercise, you might be able to solve this by adding only a few lines of code!

```js
function realMarioPyramid(height) {
    // your code here
}

realMarioPyramid(5)
/*
Expected output:
    #
   ##
  ###
 ####
#####
*/
```

??? note "Example Solution"
    ```js
    function realMarioPyramid(height) {
        for (let i = 1; i <= height; i++) {
            let row = ""
            for (let j = 0; j < height - i; j++) {
                row += " "
            }

            for (let k = 0; k < i; k++) {
                row += "#"
            }
            console.log(row)
        }
    }
    ```
