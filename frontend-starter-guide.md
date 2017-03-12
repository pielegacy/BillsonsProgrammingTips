# Frontend Starter Guide

## HTML
### New Page Template

HTML Pages will always have a starting template that looks the same and
so because of this many modern text editors include a shortcut to make
build this template:

- **Atom** : type `html` and then press tab
- **Visual Studio Code** : type `!` and then press tab

If you don't have that handy you can just copy this:

```html
<!--Tells the browser it's an HTML file-->
<!DOCTYPE html>
<!--The starting element, the lang attribute is optional-->
<html lang="en">
<!--The head tag contains data about the page-->
<head>
    <!--Allows for UTF-8 characters (multiple languages, symbols and emojis)-->
    <meta charset="UTF-8">
    <!--Allows for mobile viewing to be responsive-->
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <!--This is optional, just comes with the snippet-->
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <!--The title of the page, is displayed in the browser tab-->
    <title>Document</title>
</head>
<body>
    <!--The actual HTML we see-->
</body>
</html>
```
*You can remove the comments if you wish, it's purely for annotation.*

### Text Elements

The HTML markup language has a bunch of elements for showing text and doing basic formatting to the text. 
Stuff like font, text color and size can be changed using HTML but you shouldn't use them;
that's a job for CSS.

Instead, basic stuff like making heading, bold/italic/underlined and blocked text should be done
with the available HTML tags:

- **Heading Tags** (`<h1>,<h2>,<h3>,<h4>,<h5>,<h6>`)
    - Includes tags 1 through 6, heading tags are used for... Well... Headings.
    - 1 is the largest and most primary, 6 is the smallest and should be used for more subtle headings.
    - Like all the other formatting tags, the text content should be placed between the opening and closing tags
        - `<h1>This is a large heading</h1>`
- **Bold Tags** (`<b>`)
    - Makes the text within the tag bold.
        - `<b>This is bold text</h>`
- **Italic Tags** (`<i>`)
    - Makes the text italic
        - `<i>This is italic text</i>`
- **Underline Tags** (`<u>`)
    - You can guess what this does
        - `<u>This text is underlined</u>

If you need to put text in a paragaph, use the `<p>` tag and that will break off the text once the tag finishes:

```html
    <p> This is a paragraph </p>
    <p> This is another </p>
```

Note you can manually break a paragraph using a special "self closing" tag `<br/>`:

```html
    <p>
        This is a paragraph <br/>
        That was a line break
    </p>
```

### Section Elements

It is a good idea to divide your page into different sections as it allows for good styling as 
well as easier interactions. The most generic is the `<div>` which will place the contents within it in a block element. This is an example of how to use divs:

```html
<div>
    <h1>Hello I am the heading of the first div</h1>
    <b>How are we?</b>
</div>
<div>
    <h2>Well look, I am another div</h2>
</div>
```

Div elements will place a little bit of space between it and other elements and has a bunch of 
variants to make it easier for you and web browsers to understand the purpose of what the div does.

For example, something like the navigation bar has a special div tag called a `<nav>`. It's optional to use this but it does help you and browsers know where the navigation bar is.

The navigation div is often placed in another kind of div called a `<header>`, this can contain
the site logo and other major information which is often at the top of the page.

All these special divs are optional to use but it is probably smart to work with them, here are some examples:

- `<header>`
    - Usually put at the top of the body
    - Contains the `<nav>` div and the logo of the site and such
- `<footer>`
    - Usually at the bottom of the body
    - Contains stuff like the copyright information and lesser information
- `<nav>`
    - Contains the navigation elements for the page
- `<section>`
    - An identical way of saying `<div>`
    - Literally nothing different, just looks nicer for some people
- `<article>`
    - Often used to identify a div that contains a lot of text
- `<aside>`
    - Used to define a div that contains side content

There are others but these are always the most useful ones.

### Hyperlinks

A a hyperlink element is just that, a link to another page. Hyperlinks are defined with
the `<a>` tag and are often used like so:

```html
    <a href="anotherpage.html">Some text to click</a>
```

The href attribute is what we use to tell the browser where the link points to. It can be to
another site, or not even an html file:

```html
    <!--Use the site's address to go to another site-->
    <a href="http://google.com">Go to google</a>
    <!--Use the name of another file in the websites folder to go to that file-->
    <a href="coolpicture.jpeg">Wanna see an image</a>
    <!--If the file is in a subfolder of the site, use the folder format like so-->
    <a href="FolderName/file.html">Go to a sub folder's file</a>
```

### Lists

Lists are just that, a list. They come in two variants:

- **The Ordered List** `<ol>`
    - Includes the number of the element automatically
    - `<ol>...</ol>`
- **The Unordered List** `<ul>`
    - Includes dashes rather than numbers
    - `<ul>..</ul>`

To add items to these lists we just encompass them with `<li>` tags:

```html
    <ol>
        <li>I am the first element</li>
        <li>I am the second</li>
    </ol>
```

Yes you can have lists within lists:

```html
    <ol>
        <li>
            <ul>
                <li>Hello</li>
                <li>Bye</li>
            </ul>
        </li>
        <li>
            <h2>That was fun</h2>
        </li>
    </ol>
```

## CSS

### Template
