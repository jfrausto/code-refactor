# Homework 1: Code Refactor

_by Jesse Frausto // July 7th, 2020_

In this project, I am tasked to refactor an existing web page to make it meet user accessibility requirements. In order to simplify and restructure the source code without changing its behavior, I replace `<div>` elements with _semantic_ elements to increase accessibility simultaneously, among other changes described below. Our **user story** here regards a marketing agency and their website.

```
AS A marketing agency
I WANT a codebase that follows accessibility standards
SO THAT our own site is optimized for search engines
```

To have a code base meet accessibility standards we must meet these acceptance criteria:

```
GIVEN a webpage meets accessibility standards
WHEN I view the source code
THEN I find semantic HTML elements
WHEN I view the structure of the HTML elements
THEN I find that the elements follow a logical structure independent of styling and positioning
WHEN I view the image elements
THEN I find accessible alt attributes
WHEN I view the heading attributes
THEN they fall in sequential order
WHEN I view the title element
THEN I find a concise, descriptive title

```

## Restructuring for Accesibility

Throughout the source code you can find examples of code refactoring, such as:

- `<div class="header">` turning into the semantic `<header>` element.
- `<div class="content">` turning into the more logical `<main>` element.
- `<figure>` elements wrapping around `<img>` tags.
- `<div class ="benefits">` replaced by `<aside class="benefits">`

The CSS was altered in a way to make the styling apply in the same way before refactoring. For example, `.header` class selectors were replaced with `header` element selectors and in each of its descendant's stylings. All of this is done to increase readability for humans _and_ screen readers. Screen readers use semantic elements to 'hook' onto sections of a web page, and the code becomes easier to read for people. In addition, the semantic tags make the logical structure more apparent and easily navigable. For example, in this client's website the header and navigation bar were on the same line with `<div>` wrappers and replaced with:

```html
<header>
  <nav>
    ...
  </nav>
</header>
```

To further meet standards for heading attriubutes, I replaced heading elements in sequetial order from top to bottom. That is to say, at the `<header>` is where you would find the `<h1>` tag. In the middle of the page in each of the `<main>` and `<aside>` sections you will find the `<h2>` tag. And logically at the bottom in the `<footer>` you will find the smallest `<h3>` tag. Of course, at the top in the `<title>` element you will find a brief, descriptive website title.
Images were also refactored for accessibility. Each `<img>` tag was wrapped inside a `<figure>` element and appended an `alt` attribute describing the image.

Lastly, a `reset.css` file was implemented just before our main `style.css` stylesheet for good browser compatibility practice.
