---
comments: true
---

# Forms

... Lorem

## Preparation :books:

### HTML Form Basics

<iframe class="video" src="https://drive.google.com/file/d/1h0eAhQGs--q3hvPPCmGE_IYpDhRsd43b/preview" allowfullscreen></iframe>

### Styling Forms

Lorem...

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

### Survey Form


### Styling Forms

### A Payment Form?

### Modals?

### Comment Box

form validation - phone? password restriction