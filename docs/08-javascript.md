---
comments: true
---

# JavaScript

## Preparation :books:

Working on it! :construction: Should be ready no later than Tuesday :relaxed:

<!-- ## Exercises :writing_hand_tone2:

### Hello, JavaScript!

In this session, the output of all exercises will be shown in the console of the DevTools.

Start by creating an HTML document that includes a JavaScrip file, which logs the message "Hello, JavaScript" to the console.

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

### Variables & Constants

Start lidt simpelt...

### Equality

### Type Coercion

### User Input Null

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

### Meow! Meow! Meow!

Write a function that prints "Meow!" to the console n times, where n is a number provided as input to the function.

??? note "Example Solution"
    ```js
    function meowing(n) {
        for(let i = 0; i < n ; i++) {
            console.log("Meow!")
        }
    }
    ```

### Scope

### Debugging

Take a look at the code snippet below. Something isn’t working as expected.

What is wrong with the code below? Use the DevTools to diagnose the code by identifying error messages, and correct the code by debugging it in the browser.

### Arrays
Push pop

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

### Objects
Create an object of yourself! Give it appropriate properties like name, age and hobbies! Maybe even a method or two?

??? note "Example Solution"
    ```js
    let me = {
        name: "Kasper",
        age: 37,
        hobbies: ["Programming", "Game Development", "Gaming", "Pokémon", "Board Games"],
        isMarried: true,
        sing() {
            console.log("LA LA LA LA!")
        },
        ding() {
            this.age++
        },
    }
    ```

### Iterating Over Objects

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

### Calculating Areas

Create a function called that returns the area of a given shape.

The function should have the following parameters:

- shape: a string representing the type of shape
- a: a number representing the primary dimension (e.g. radius or width).
- b: an optional number used to supply the height of rectangles.

The function should be able to deal with the following shapes:
- Circles (π * radius * radius)
- Squares (side * side)
- Rectangles (width * height)
- If an unsupported shape is provided, return undefined.

??? note "Example Solution"
    ```js
    function calculateArea(shape, a, b) {
        switch (shape.toLowerCase()) {
            case "circle":
                return Math.PI * a * a;
            case "square":
                return a * a;
            case "rectangle":
                if (typeof b === "undefined") return undefined;
                return a * b;
            default:
                return undefined;
        }
    }
    
    console.log(calculateArea("circle", 3));        // → 28.274333882308138
    console.log(calculateArea("square", 4));        // → 16
    console.log(calculateArea("rectangle", 5, 10)); // → 50
    console.log(calculateArea("triangle", 5));      // → undefined
    ```

### When's Your Birthday?

Create a JavaScript program, that logs how many days there is to your birthday!

### JAVAScript?

You already know how to write Java. Convert the Java code below to JavaScript!

```Java
import java.util.ArrayList;
import java.util.Arrays;

public class Main {

    public static void main(String[] args) {
        String studentName = "Troels";
        ArrayList<Integer> grades = new ArrayList<>(Arrays.asList(85, 90, 78, 92, 88));
        calculateGrade(studentName, grades);
    }

    public static void calculateGrade(String name, ArrayList<Integer> grades) {
        int sum = 0;
        for (int i = 0; i < grades.size(); i++) {
            sum += grades.get(i);
        }

        double average = sum / (double) grades.size();

        if (average >= 90) {
            System.out.println(name + " has an A average.");
        } else if (average >= 80) {
            System.out.println(name + " has a B average.");
        } else {
            System.out.println(name + " needs improvement.");
        }
    }
}
```

??? note "Example Solution"
    ```js
    let studentName = "Troels"
    let grades = [85, 90, 78, 92, 88]
    calculateGrade(studentName, grades)

    function calculateGrade(name, grades) {
        let sum = 0
        for (let i = 0; i < grades.length; i++) {
            sum += grades[i]
        }

        let average = sum / grades.length

        if (average >= 90) {
            console.log(name + " has an A average.")
        } else if (average >= 80) {
            console.log(name + " has a B average.")
        } else {
            console.log(name + " needs improvement.")
        }
    }
    ```

### Vowel Counting

Create a function, that can count the [vowels](https://en.wikipedia.org/wiki/Vowel) in an english sentence. You can use the code below as a starting point. For simplicity's sake, you don't have to account for "y" and "w" being vowels.

```javascript
function countVowels(sentence) {
    // Your code here
}

function isVowel(char) {
    const VOWELS = ["a", "e", "i", "o", "u"]
    // Your code here
}

console.log(countVowels("Pikachu is cute")) // → 6
```

??? note "Example Solution"
    ```js
    function countVowels(sentence) {
        let numberOfVowels = 0
        for (let char of sentence.toLowerCase()) {
            if (isVowel(char)) {
                numberOfVowels++
            }
        }
        return numberOfVowels;
    }

    function isVowel(char) {
        const VOWELS = ["a", "e", "i", "o", "u"]
        for (let vowel of VOWELS) {
            if (vowel == char) return true
        }
        return false
    }

    console.log(countVowels("Hi, how are you?")) // → 6
    ```

### Random Number Generator

Create a function that returns a random number between a min (included) and a max (excluded) value.

??? tip "Tips"
    - The [Math.random()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/random) static method returns a floating-point, pseudo-random number that's greater than or equal to 0 and less than 1.
    - The [Math.floor()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math/floor) static method returns the largest integer less than or equal to a given number.
    - The expression below evaluates to a number between 1 and 10.
    ```js
    Math.floor(Math.random() * 10) + 1
    ```
    - If you want a number between e.g. 5 and 10, you're really asking for a number in a range of 5 (10 - 5) possible values: 5, 6, 7, 8, or 9. So we first generate a random number between 0 and 5, and then shift it up by adding the min value (5 in this case).

??? note "Example Solution"
    ```js
    function randomNumber(min, max) {
        return Math.floor(Math.random() * (max - min)) + min;
    }
    ```

### The Mario Pyramid

<img style="display: block; margin: auto; border-radius: 0.5rem;" src="https://github.com/KasperKnop/WEB1/blob/main/resources/mario-reverse.gif?raw=true" alt="The Mario Pyramid!">

Recreate the famous half pyramid from the Mario games using hashtags and `console.log`!

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
    
### Nice Work! -->