---
comments: true
---

# JavaScript

## Preparation :books:

### Foo

## Exercises :writing_hand_tone2:

### Variables

### Constants

### Type Coercion

### Scope

### Debugging

### Objects

### Arrays

### Built in Objects

### Loops

Pyramide?

### Loops

Loop through the array of Pokemon and log any fire Pokemon to the console.

### Average

I have an array of grades and want to find the average of the grades. Your task is to complete the code so that it sums up all the grades in a loop and calculates the average.

```js
let total = 0
let grades = [12, 7, 4, -3, 4, 10, 4]

console.log(getAverage(grades))

function getAverage(array) {
    // Your code here
}
```

### Functions

### Military Time

MilitaryTime represents the current time using the 24-hour format. For example, a value of 1700 means it's 5:00 PM.
Assuming that the user correctly provides a number between 0000 - 2359, write a function that determines whether the current time falls into one of the following categories:

- Morning: Any time before 08:00 AM
- School: Between 08:00 AM and 04:00 PM
- Evening: Any time after 04:00 PM

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

### Calculator

### Binary Number Calculator?

### Mario Pyramid

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

<img style="display: block; margin: auto; border-radius: 0.5rem;" src="https://github.com/KasperKnop/WEB1/blob/main/resources/mario.gif?raw=true" alt="The Mario Pyramid!">

??? note "Example Solution"
    ```js
    function marioPyramid(height) {
        for (let i = 1; i <= height; i++) {
            let row = ''
            for (let j = 0; j < i; j++) {
                row += '#'
            }
            console.log(row)
        }
    }

    // OR

    function marioPyramid(height) {
        for (let line = "#"; line.length <= height; line += "#")
            console.log(line)
    }
    ```

### Mirror Mode!

If you have played Mario, you have probably noticed that the game was mirrored in the previous exercise! This time, you should implement the real pyramid from Mario! Depending on how you have implemented the previous exercise, you might be able to solve this by adding only a few lines of code!

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
