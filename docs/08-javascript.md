---
comments: true
---

# JavaScript

So far, we've focused on building responsive and user-friendly websites using HTML and CSS. However, these sites have been mostly static, offering little room for user interaction or dynamic behavior. In this session, we'll introduce JavaScript - the browser's programming language - that will allow us to manipulate data as well as update and change both HTML and CSS, to create more dynamic web pages.

## Preparation :books:

### JavaScript Basics

JavaScript shines when it interacts with HTML and CSS, but before we dive into that, we'll make sure that you understand the fundaments of the language. In the video below, we'll get hands-on with basic language features including variables, data types, conditionals, functions, arrays, objects, loops and more! You're likely already familiar with most of these concepts from Java, but keep an eye out for the key conceptual and syntactical differences!

<iframe title="JavaScript Basics" class="video" src="https://drive.google.com/file/d/1rUFAg7yBmhp8RM_zK95oluANuwDx0TiT/preview" allow="autoplay" allowfullscreen></iframe>

To get an overview of the language, take a look at W3Schools' resources:

- [JavaScript Introduction](https://www.w3schools.com/js/js_intro.asp)
- [The Script Tag](https://www.w3schools.com/js/js_whereto.asp)
- [Syntax](https://www.w3schools.com/js/js_syntax.asp)
- [Variables](https://www.w3schools.com/js/js_variables.asp)
- [Operators](https://www.w3schools.com/js/js_operators.asp)
- [Conditionals](https://www.w3schools.com/js/js_conditionals.asp)
- [Loops](https://www.w3schools.com/js/js_loops.asp)
- [Strings](https://www.w3schools.com/js/js_strings.asp)
- [Numbers](https://www.w3schools.com/js/js_numbers.asp)
- [Functions](https://www.w3schools.com/js/js_functions.asp)
- [Objects](https://www.w3schools.com/js/js_objects.asp)
- [The Date Object](https://www.w3schools.com/js/js_dates.asp)
- [The Math Object](https://www.w3schools.com/js/js_math.asp)
- [Arrays](https://www.w3schools.com/js/js_arrays.asp)

## Exercises :writing_hand_tone2:

### Hello, JavaScript!

In this session, the output of all exercises will be shown in the console of the DevTools.

Start by creating an HTML document that includes a JavaScript file, which logs the message `Hello, JavaScript` to the console.

To make your workflow easier, open the HTML file with Live Server, and undock the console from the browser window — we won't need to view the web page itself during this session.

??? note "Solution"
    ```html
    <!DOCTYPE html>
    <html>
    <head>
        <script src="script.js"></script>
    </head>
    <body></body>
    </html>
    ```
    ```js
    console.log("Hello, JavaScript")
    ```

### From Java to JavaScript

Converting code from one programming language to another is called transpiling. Since you already know Java, transpile the Java code below to JavaScript.

```js
public class Main {
    public static void main(String[] args) {
        final String APP_NAME = "FitTrack";

        String username = "Michael";
        int age = 39;
        double height = 1.90;
        boolean isPremiumUser = true;

        System.out.println("Welcome to " + APP_NAME + ", " + username);
    }
}
```

??? note "Solution"
    ```js
    const APP_NAME = "FitTrack"

    let username = "Michael"
    let age = 39
    let height = 1.90
    let isPremiumUser = true

    console.log("Welcome to " + APP_NAME + ", " + username)
    ```

### Debugging JavaScript
The code below has an error. Run the code in the browser and examine the console output. What is the error, and how can it be fixed?

```js
const userName = "Kasper"
userName = "Troels"

console.log(userName)
```

??? note "Solution"
    ```
    "Uncaught TypeError: Assignment to constant variable"
    ```
    ```js
    let userName = "Kasper"
    userName = "Troels"

    console.log(name)
    ```

### Loose & Strict Equality

Which of the comparisons below evaluate to true? Why?

```js
console.log("5" == 5)
console.log("5" === 5)
console.log(true == 1)
console.log(true === 1)
console.log(null == undefined)      
console.log({} == {})
```

??? note "Solution"
    ```js
    console.log("5" == 5) // true
    console.log("5" === 5) // false
    console.log(true == 1) // true
    console.log(true === 1) // false
    console.log(null == undefined)  // true    
    console.log({} == {}) // false
    ```

### Meow! Meow! Meow!

Write a function that prints "Meow!" to the console n times, where n is a number provided as input to the function.

??? note "Solution"
    ```js
    function meowing(n) {
        for(let i = 0; i < n ; i++) {
            console.log("Meow!")
        }
    }
    ```

### Military Time

Military time represents the current time using the 24-hour format. For example, a value of 1700 means it's 5:00 PM.
Assuming that the user correctly provides a time between 0000 - 2359, write a function that determines whether the current time falls into one of the following categories:

-   Morning: Any time before 08:00 AM
-   School: Between 08:00 AM and 04:00 PM
-   Evening: Any time after 04:00 PM

```js
console.log(timeOfDay(prompt("Input military time (0000 - 2359)")))

// Your code here
```

??? note "Solution"
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

### Scope
What is printed to the console? Why?

```js
let x = 1

function foo() {
    x = 2
    if (true) {
        let x = 3
        console.log(x)
    }
    console.log(x)
}

foo()

console.log(x)
```

??? note "Solution"
    ```js
    3
    2
    2
    ```

### A Stack Overflow

The function below doesn't work as intended. Run the code and observe the error message in the console.
Then, use [the debugger](https://developer.chrome.com/docs/devtools/javascript) to understand what happens step by step:
Set a breakpoint inside the function in the "Sources" tab of the DevTools and follow the code execution line by line.

Can you fix the function?

```js
function countdown(number) {
    console.log(number)
    countdown(number - 1)
}

countdown(5)
```

??? note "Solution"
    ```
    Uncaught RangeError: Maximum call stack size exceeded
    ```
    ```js
    function countdown(number) {
        console.log(number)
        if (number > 0)
            countdown(number - 1)
    }

    countdown(5)
    ```
    
### Modifying Arrays

Modify the array using `pop` and `push` so that it mathes the output.

```js
const backpack = ["Notebook"]

// Your code here

console.log("Backpack contains:", backpack) // → ["Pen", "Lunch Box", "Water Bottle"]
```

??? note "Solution"
    ```js
    const backpack = ["Notebook"]

    backpack.pop()
    backpack.push("Pen")
    backpack.push("Lunch Box")
    backpack.push("Water Bottle")

    console.log("Backpack contains:", backpack) // → ["Pen", "Lunch Box", "Water Bottle"]
    ```

### Looping through an Array

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

??? note "Solution"
    ```js
    function getAverage(array) {
        total = 0
        for (let value of array) {
            total += value
        }
        return total / array.length
    }
    ```

### Another Transpilation!

Transpile the Java program below to JavaScript!

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

??? note "Solution"
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

### Objectify Yourself!
Create an object literal of yourself! Give it appropriate properties like name, age and hobbies! Maybe even a method or two?

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

### Iterating Over an Object Array

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

??? note "Solution"
    ```js
    for (let i = 0; i < pokemonList.length; i++) {
        if (pokemonList[i].type === "Fire") {
            console.log(pokemonList[i].name)
        }
    }
    ```

### Handling Null

The code below simulates retrieving a user from a database by ID and sending them a message. However, there's a bug - the program crashes when trying to send a message to a user that doesn't exist.

Run the code and identify the error shown in the console. Fix the `sendMessageToUser` function to handle missing users and print a clear message if no user is found.

```js
const users = [
    { id: 1, name: "Troels" },
    { id: 2, name: "Michael" },
    { id: 3, name: "Richard" }
]

function getUserById(id) {
    for (let user of users) {
        if (user.id === id) {
            return user
        }
    }
    return null
}

function sendMessageToUser(userId, message) {
    const user = getUserById(userId)

    // Your Code here

    console.log("Sending message to "  + user.name + ": " + message)
}

sendMessageToUser(2, "Hello!")
sendMessageToUser(5, "Are you there?")
```

??? note "Solution"
    ```
    Uncaught TypeError: Cannot read properties of null
    ```
    ```js
    const users = [
        { id: 1, name: "Troels" },
        { id: 2, name: "Michael" },
        { id: 3, name: "Richard" }
    ]

    function getUserById(id) {
        for (let user of users) {
            if (user.id === id) {
                return user
            }
        }
        return null
    }

    function sendMessageToUser(userId, message) {
        const user = getUserById(userId)

        if (user === null) {
            console.log("Error: No user found with id " + userId)
            return
        }

        console.log("Sending message to " + user.name + ": " + message)
    }

    sendMessageToUser(2, "Hello!")
    sendMessageToUser(5, "Are you there?")
    ```

### Calculating Areas

Create a function called that returns the area of a given shape.

The function should have the following parameters:

- shape: a string representing the type of shape.
- a: a number representing the primary dimension (e.g. radius or width).
- b: an optional number used to supply the height of rectangles.

The function should be able to deal with the following shapes:

- Circles (π * radius * radius)
- Squares (side * side)
- Rectangles (width * height)
- If an unsupported shape is provided, return undefined.

??? note "Solution"
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

### Is It Christmas Yet?

Create a function, that calculates the amount of days until Christmas!

??? tip "Tips"
    - `new Date()` creates a Date object with the current date and time.
    - `getFullYear()` returns the year of a date.
    - `new Date(year, month, day)` lets you create a specific date. Notice that months are 0-indexed!
    - Subtracting two dates gives the difference in milliseconds.
    - Convert milliseconds to days using `1000 * 60 * 60 * 24`
    - Use `Math.ceil` to round up so today counts as a full day.
    - Don't forget to handle the case when Christmas has already passed this year!

??? note "Solution"
    ```js
    function daysUntilChristmas() {
        const today = new Date()
        const christmas = new Date(today.getFullYear(), 11, 24)

        if (today > christmas) christmas.setFullYear(today.getFullYear() + 1)

        const differenceInMs = christmas - today
        const differenceInDays = Math.ceil(differenceInMs / (1000 * 60 * 60 * 24))

        return differenceInDays
    }

    console.log("Days until Christmas: " + daysUntilChristmas())
    ```

### Vowel Counting

Create a function, that can count the [vowels](https://en.wikipedia.org/wiki/Vowel) in an english sentence. You can use the code below as a starting point. For simplicity's sake, you don't have to account for "y" and "w" being vowels.

```js
function countVowels(sentence) {
    // Your code here
}

function isVowel(char) {
    const VOWELS = ["a", "e", "i", "o", "u"]
    // Your code here
}

console.log(countVowels("Pikachu is cute")) // → 6
```

??? note "Solution"
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

??? note "Solution"
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

??? note "Solutions"
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

??? tip "Tip"
    - Use two loops to create a row: One loop for the spaces (height - currentRow) and one loop for the hashes (currentRow).

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

??? note "Solution"
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
    
### Nice Work!

Phew! You've worked through a lot of exercises - great job! Take a well-deserved break, and if you have any questions, don't hesitate to leave them in the comment section below.