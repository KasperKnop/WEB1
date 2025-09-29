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
- Include a “Remember me” checkbox (it should not persist the form data).
- Have a button for submitting the form data.
- Provide a `<label>` for each input.
- Group inputs inside a `<fieldset>` with a `<legend>`.
- Use the proper HTTP method.

You do not have to style the HTML, but since input elements are inline elements, it might be a good idea to organize them with `<div>` or use `<br>`, so that they stack vertically.

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

### A Callback Form

The company you work for wants a web form for customers to schedule a call with them. The form should collect the following information:

- Full name
- Phone number (required, danish numbers only)
- Preferred date
- Preferred time window (morning, midday, noon or evening)

Styling is not a priority.

??? note "Example Solution"
    ```html
    <!DOCTYPE html>
    <html lang="en">
        <head>
            <meta charset="UTF-8" />
            <title>Have Us Call You</title>
        </head>
        <body>
            <form action="/schedule-call" method="post">
                <h2>Have Us Call You</h2>
                <div>
                    <label for="name">Full name</label>
                    <input id="name" name="name" autofocus />
                </div>

                <div>
                    <label for="phone-number">Phone number*</label>
                    <input placeholder="+45" size="3" disabled/>
                    <input type="tel" name="phone-number" id="phone-number" pattern="\d{8}|\d{2} \d{2} \d{2} \d{2}" required/>
                </div>

                <div>
                    <label for="date">Preferred date</label>
                    <input id="date" name="date" type="date" />
                </div>

                <div>
                    <label for="timeWindow">Preferred time window</label>
                    <select id="timeWindow" name="timeWindow">
                        <option value="">No preference</option>
                        <option value="morning">Morning (08:00-12:00)</option>
                        <option value="midday">Midday (12:00-16:00)</option>
                        <option value="afternoon">Afternoon (16:00-20:00)</option>
                        <option value="evening">Evening (20:00-22:00)</option>
                    </select>
                </div>
                <button>Request a Call</button>
            </form>
        </body>
    </html>
    ```

### Real-Time Validation

The account creation form below is lacking real time feedback for validating the users input. It only validates the input when the user clicks the "Create Account" button. Style the input (using the css color variables) so that the user immediatly can see if the input is valid or invalid.

```html
    <!DOCTYPE html>
    <html lang="en">
        <head>
            <meta charset="UTF-8" />
            <meta name="viewport" content="width=device-width, initial-scale=1.0" />
            <title>Create Account</title>
            <style>
                :root {
                    --primary: hsl(211, 100%, 50%);
                    --valid: hsl(143, 100%, 26%);
                    --invalid: hsl(348, 55%, 49%);
                }

                * {
                    box-sizing: border-box;
                }

                input, button {
                    font: inherit;
                }

                body {
                    display: flex;
                    justify-content: center;
                    align-items: center;
                    min-height: 100vh;
                    margin: 0px;
                    background: #f0f2f5;
                    font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
                }

                form {
                    background: #fff;
                    padding: 40px;
                    border-radius: 18px;
                    box-shadow: 0 8px 20px rgba(0, 0, 0, 0.1);
                }

                h2 {
                    text-align: center;
                    margin-bottom: 40px;
                    color: #555;
                }

                label {
                    display: block;
                    margin-bottom: 6px;
                    color: #555;
                    font-weight: 500;
                }

                input {
                    width: 100%;
                    padding: 12px 15px;
                    margin-bottom: 20px;
                    border: 0px solid;
                    border-radius: 8px;
                    font-size: 16px;
                    outline: 3px solid rgba(0, 123, 255, 0.2);
                }

                button {
                    width: 100%;
                    padding: 12px;
                    background-color: var(--primary);
                    color: white;
                    border: none;
                    border-radius: 8px;
                    font-size: 16px;
                    font-weight: 600;
                    cursor: pointer;
                }
            </style>
        </head>
        <body>
            <form action="/submit" method="post">
                <h2>Create an Account</h2>

                <label for="name">Full Name</label>
                <input type="text" id="name" name="name" placeholder="John Doe" required minlength="2" maxlength="50" />

                <label for="email">Email</label>
                <input type="email" id="email" name="email" placeholder="example@mail.com" required />

                <label for="password">Password</label>
                <input type="password" id="password" name="password" placeholder="Enter password" required minlength="6" />

                <button>Create Account</button>
            </form>
        </body>
    </html>
```

??? note "Example Solution"
    ```html
    <!DOCTYPE html>
    <html lang="en">
        <head>
            <meta charset="UTF-8" />
            <meta name="viewport" content="width=device-width, initial-scale=1.0" />
            <title>Create Account</title>
            <style>
                :root {
                    --primary: hsl(211, 100%, 50%);
                    --valid: hsl(143, 100%, 26%);
                    --invalid: hsl(348, 55%, 49%);
                }

                * {
                    box-sizing: border-box;
                }

                input,
                button {
                    font: inherit;
                }

                body {
                    display: flex;
                    justify-content: center;
                    align-items: center;
                    min-height: 100vh;
                    margin: 0px;
                    background: #f0f2f5;
                    font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
                }

                form {
                    background: #fff;
                    padding: 40px;
                    border-radius: 18px;
                    box-shadow: 0 8px 20px rgba(0, 0, 0, 0.1);
                }

                h2 {
                    text-align: center;
                    margin-bottom: 40px;
                    color: #555;
                }

                label {
                    display: block;
                    margin-bottom: 6px;
                    color: #555;
                    font-weight: 500;
                }

                input {
                    width: 100%;
                    padding: 12px 15px;
                    margin-bottom: 20px;
                    border: 0px solid;
                    border-radius: 8px;
                    font-size: 16px;
                    outline: 3px solid rgba(0, 123, 255, 0.2);
                }

                button {
                    width: 100%;
                    padding: 12px;
                    background-color: var(--primary);
                    color: white;
                    border: none;
                    border-radius: 8px;
                    font-size: 16px;
                    font-weight: 600;
                    cursor: pointer;
                }

                input:not(:placeholder-shown):invalid {
                    outline-color: var(--invalid);
                }

                input:not(:placeholder-shown):valid {
                    outline-color: var(--valid);
                }

                input:focus:invalid {
                    outline-color: var(--primary);
                }
            </style>
        </head>
        <body>
            <form action="/submit" method="post">
                <h2>Create an Account</h2>

                <label for="name">Full Name</label>
                <input type="text" id="name" name="name" placeholder="John Doe" required minlength="2" maxlength="50" />

                <label for="email">Email</label>
                <input type="email" id="email" name="email" placeholder="example@mail.com" required />

                <label for="password">Password</label>
                <input type="password" id="password" name="password" placeholder="Enter password" required minlength="6" />

                <button>Create Account</button>
            </form>
        </body>
    </html>
    ```

### A Payment Form

Create a payment form for credit cards. It should contain at least the cardholders name, the card number, expiry date and security code. It should utilize proper validation with immediate feedback, and a custom layout that arranges the input in a user friendly manner. For inspiration, see the image below.

<img style="display: block; margin: auto; border-radius: 0.5rem;" src="https://github.com/KasperKnop/WEB1/blob/main/resources/payment-details.png?raw=true">

??? note "Example Solution"
    ```html
    <!DOCTYPE html>
    <html lang="en">
        <head>
            <meta charset="UTF-8" />
            <title>Payment Form</title>
            <style>
                :root {
                    --primary: #007bff;
                    --secondary: #0056b3;
                    --valid: #4caf50;
                    --invalid: #f44336;
                    --border: #ccc;
                    --bg: #eeeded;
                    --card-bg: #f9f9f9;
                    --text: hsl(0, 0%, 24%);
                }

                * {
                    box-sizing: border-box;
                    margin: 0;
                }

                body {
                    font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
                    font-size: 1.125rem;
                    line-height: 1.6;
                    color: var(--text);
                    background: var(--bg);
                    padding-block-start: 10vb;
                }

                input,
                button,
                select {
                    border: 1px solid var(--border);
                    border-radius: 8px;
                    padding: 0.5rem;
                    outline: 1px solid transparent;
                }

                #card-details {
                    display: grid;
                    grid-column-gap: 0.8rem;
                    grid-template-columns: max-content 1fr;
                }

                #card-details > div:nth-child(2) {
                    grid-row: 2/3;
                    grid-column: 1/2;
                }

                h2 {
                    text-align: center;
                    margin-bottom: 1rem;
                }

                button {
                    background: var(--primary);
                    color: var(--bg);
                    cursor: pointer;
                }

                button:hover {
                    background: var(--secondary);
                }

                label {
                    text-transform: uppercase;
                    font-size: 0.75rem;
                }

                form {
                    display: grid;
                    padding: 2rem;
                    border-radius: 12px;
                    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
                    max-width: 350px;
                    gap: 1.5rem;
                    margin: auto;
                    background: var(--card-bg);
                }

                .form-group {
                    display: grid;
                }

                #cvv {
                    max-width: 6ch;
                }

                input:not(:placeholder-shown):invalid {
                    outline-color: var(--invalid);
                }

                input:not(:placeholder-shown):valid,
                select:not(:placeholder-shown):valid {
                    outline-color: var(--valid);
                }

                input:focus:invalid {
                    outline-color: var(--primary);
                }

                select:focus {
                    outline-color: var(--primary);
                }
            </style>
        </head>
        <body>
            <form action="/payment" method="post">
                <h2>Payment Details</h2>

                <div class="form-group">
                    <label for="name">Cardholder Name</label>
                    <input type="text" id="name" name="name" required placeholder="John Doe" />
                </div>

                <div class="form-group">
                    <label for="card">Card Number</label>
                    <input type="text" id="card" name="card" pattern="\d{16}|\d{4} \d{4} \d{4} \d{4}" placeholder="1234 5678 9012 3456" required />
                </div>

                <div id="card-details">
                    <label for="expiry-month">Expiry Date</label>
                    <div id="expiry">
                        <select id="expiry-month" name="expiry-month" required>
                            <option value="">--</option>
                            <option value="1">01</option>
                            <option value="2">02</option>
                            <option value="3">03</option>
                            <option value="4">04</option>
                            <option value="5">05</option>
                            <option value="6">06</option>
                            <option value="7">07</option>
                            <option value="8">08</option>
                            <option value="9">09</option>
                            <option value="10">10</option>
                            <option value="11">11</option>
                            <option value="12">12</option>
                        </select>
                        <span>/</span>
                        <select id="expiry-year" name="expiry-year" required>
                            <option value="">----</option>
                            <option value="2025">2025</option>
                            <option value="2026">2026</option>
                            <option value="2027">2027</option>
                            <option value="2028">2028</option>
                            <option value="2029">2029</option>
                            <option value="2030">2030</option>
                            <option value="2031">2031</option>
                            <option value="2032">2032</option>
                            <option value="2033">2033</option>
                            <option value="2034">2034</option>
                            <option value="2035">2035</option>
                            <option value="2036">2036</option>
                            <option value="2037">2037</option>
                            <option value="2038">2038</option>
                            <option value="2039">2039</option>
                            <option value="2040">2040</option>
                            <option value="2041">2041</option>
                            <option value="2042">2042</option>
                            <option value="2043">2043</option>
                            <option value="2044">2044</option>
                            <option value="2045">2045</option>
                            <option value="2046">2046</option>
                            <option value="2047">2047</option>
                            <option value="2048">2048</option>
                            <option value="2049">2049</option>
                            <option value="2050">2050</option>
                        </select>
                    </div>
                    <label for="cvv">CVV</label>
                    <input id="cvv" name="cvv" required pattern="\d{3}" placeholder="123" />
                </div>
                <button>Pay Now</button>
            </form>
        </body>
    </html>
    ```

### Your Own Survey

Use what you have learned to create and style your own survey. You decice what the survey is for, but you must include as many form controls as possible: Range sliders, radio buttons, color pickers, file pickers, date/time pickers, drop-downs, multi-line text fields...

When you are done, publish the survey and share it in the comment section below.

### Nice Work!

Take a few minutes to browse the forms created by your classmates. Leave a comment if something catches your attention :slight_smile:
 