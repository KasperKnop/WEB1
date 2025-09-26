---
comments: true
---

# Forms

So far, we have only created web pages, that the user can look at. In this session, we'll explore how to create more interactive pages, using HTML forms, that allow the user to provide input. We will explore how that input can be sent to a web server and how to make forms user friendly.

## Preparation :books:

### HTML Form Basics

In the video below you will get an introduction to HTML forms. You’ll learn to create forms with different input types, understand how they send data to a server and how to validate the forms client-side using e.g regular expressions.

<iframe class="video" src="https://drive.google.com/file/d/1h0eAhQGs--q3hvPPCmGE_IYpDhRsd43b/preview" allow="autoplay" allowfullscreen></iframe>

If you want to take a deep dive into HTML forms, MDN has a [web forms module](https://developer.mozilla.org/en-US/docs/Learn_web_development/Extensions/Forms){:target="\_blank"} that provides a comprehensive coverage of the topic. The "Your first form" section covers the basics.

If you want to learn more about regular expressions, you can read this [article from MDN on regular expressions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_expressions){:target="\_blank"}. They also have a good [regex cheet sheet](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_expressions/Cheatsheet){:target="\_blank"}.

### Styling Forms

User feedback in forms can be greatly improved by styling input fields with CSS pseudo-classes such as `:valid` and `:invalid`. These allow the browser's built-in form validation to be visually communicated to the user without using JavaScript. For example, an input field outline can turn green when the entered data meets the requirements, and red when it does not, helping users immediately recognize and correct mistakes. This kind of instant visual feedback enhances usability, reduces errors, and makes forms feel more interactive and user-friendly. Watch this [short video on styling valid and invalid forms](https://www.youtube.com/watch?v=awNYtIAu6pI){:target="\_blank"} by Kevin Powell, to get some tips on how to do this. His [video on form styling essentials](https://www.youtube.com/watch?v=nuDpLN2dazU){:target="\_blank"} is also worth watching, if you want extra tips on styling and creating form layouts.

## Exercises :writing_hand_tone2:

### Your Own Search Engine!

Use an HTML form to create your own web search, that initiates an HTTP GET request to a real search engine of your choice (Google, Bing, DuckDuckGo, Yahoo...). The form should have a input field with placeholder text and a search button for submitting the form. Make sure that the input field is automatically focused and that it is requied to fill in.

??? note "Example Solution"
    ```html
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
            <title>Googol</title>
        </head>
        <body>
            <h1>Googol</h1>
            <form action="https://www.google.com/search">
                <input name="q" placeholder="Enter search terms" required autofocus />
                <button>Search</button>
            </form>
        </body>
    </html>
    ```

### A Login Screen

Create a form for logging in to a user account. The form should:
- Contain an email input and a password input.
- Include a “Remember me” checkbox (you don't have to make it persist the form data).
- Have a button for submitting the form data.
- Provide a `<label>` for each input.
- Group inputs inside a `<fieldset>` with a `<legend>`.
- Use the proper HTTP method.

You do not have to style the HTML, but since input elements are inline elements, it might be a good idea to organize them into `<div>`, so that they stack vertically.

??? note "Example Solution"
    ```html
    <!DOCTYPE html>
    <html lang="en">
        <head>
            <meta charset="UTF-8" />
            <meta name="viewport" content="width=device-width, initial-scale=1.0" />
            <title>Login Form</title>
        </head>
        <body>
            <div>
                <form action="/login" method="post">
                    <fieldset>
                        <legend>Login</legend>
                        <div>
                            <label for="email">Email</label>
                            <input type="email" placeholder="Enter email" required autofocus id="email">
                        <div>
                            <label for="password">Password</label>
                            <input type="password" placeholder="Enter password" required id="password">
                        </div>
                        <div>
                            <input type="checkbox" id="remember-me">
                            <label for="remember-me">Remember me</label>
                        </div>
                        <button>Log in</button>
                    </fieldset>
                </form>
            </div>
        </body>
    </html>
    ```

### :construction: More exercises under construction :construction:

<!-- ### Survey Form

form validation - phone? password restriction
### Styling Forms

### A Payment Form?

### Modals? -->

### Comment Box