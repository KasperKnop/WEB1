---
comments: true
---

# Forms

## Preparation :books:

### Foo

## Exercises :writing_hand_tone2:

### Your Own Search Engine!

Use an HTML form to create your own web search, that initiates an HTTP GET request to a real search engine of your choice (Google, Bing, DuckDuckGo, Yahoo...). The form should have a required input field with placeholder text and a search button for submitting the form.

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
                <input name="q" placeholder="Enter search terms" required />
                <button>Search</button>
            </form>
        </body>
    </html>
    ```

### Login Form

Labels
Fieldset/legend
Account email and password input
Remember me checkbox (only for display - should not work)

### Survey Form

### Styling Forms

### A Payment Form?

### Modals?

### Comment Box

form validation - phone? password restriction