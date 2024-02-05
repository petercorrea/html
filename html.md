# HTML Cheat Sheet

## Basic Document Structure

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document Title</title>
</head>
<body>
```

## Essential Tags

`<html>`: Root element of an HTML page.

`<head>`: Contains meta-information about the document.

`<title>`: Specifies the title of the document.

`<body>`: Contains the content of an HTML document.

`<header>`, `<footer>`, `<nav>`, `<section>`, `<article>`, `<aside>`: Structural elements.

`<h1>` to `<h6>`: Heading tags.

`<p>`: Paragraph tag.

`<a href="URL">`: Anchor/link tag.

`<img src="image.jpg" alt="description">`: Image tag.

`<ul>`, `<ol>`, `<li>`: Unordered and ordered lists.

`<table>`: Defines a table.

`<tr>`: Table row.

`<th>`: Table header.

`<td>`: Table cell.

`<form>`: Creates a form for user input.

`<input>`, `<textarea>`, `<button>`, `<select>`, `<option>`: Form elements.

`<div>`: Division/container tag.

`<span>`: Inline container tag.

## Attributes

id: Specifies a unique id for an element.
class: Specifies one or more classnames for an element.
style: Specifies an inline CSS style for an element.
src: Specifies the source URL for media elements like <img>, <audio>, and <video>.
href: Specifies the URL of a link.
alt: Specifies an alternate text for an image, if the image cannot be displayed.
title: Specifies extra information about an element (displayed as a tooltip).

## Comments

`<!-- This is a comment -->`

## Character Entities

Non-breaking space: `&nbsp;`

Less than: `&lt;`

Greater than: `&gt;`

Ampersand: `&amp;`

Quotes: `&quot;`, `&apos;`

## Doctypes

A declaration that precedes the HTML document itself and helps to ensure that the HTML code is interpreted and rendered correctly by browsers. The doctype declaration is required in all HTML documents to tell the browser which version of HTML to use when rendering the page.

HTML5: `<!DOCTYPE html>`

## Forms and Input

```html
<form action="submit.php" method="post">
  <label for="email">Email:</label>
  <input type="email" id="email" name="email" required>
  <label for="birthday">Birthday:</label>
  <input type="date" id="birthday" name="birthday">
  <input type="submit" value="Submit">
</form>
```

## Media

```html
<img src="image.jpg" alt="An image description">
<video src="movie.mp4" controls></video>
<audio src="audio.mp3" controls></audio>
```

## Responsive Images

Serve different images based on screen size and resolution.

```html
<picture>
  <source media="(min-width: 650px)" srcset="large.jpg">
  <source media="(min-width: 465px)" srcset="medium.jpg">
  <img src="small.jpg" alt="Description">
</picture>
```

## Language Attribute

Specify the language of your document using the lang attribute for better SEO and accessibility.

```html
<html lang="en">
```

## Semantics and Accessibility

Use semantic tags (`<header>`, `<nav>`, `<section>`, `<article>`, `<footer>`) for better accessibility and SEO.
Always include an alt attribute for images.
Use `<label>` for form inputs for better accessibility.

### Accessibility in Forms

Forms are a fundamental part of the web, used for various purposes from search engines to registration forms. Ensuring forms are accessible is vital so that all users, regardless of their abilities or the technologies they use, can interact with them.

#### Use Proper Markup

Labels: Every input field should have an associated `<label>` element. This ensures screen readers can announce the field's purpose correctly. Use the for attribute in the `<label>` tag to associate it with the specific form control by matching it to the id of the input element.

```html
<label for="name">Name:</label>
<input type="text" id="name" name="user_name">
```

Fieldsets and Legends: For grouping related elements in a form, use `<fieldset>` and `<legend>` elements. This is particularly useful for radio buttons and checkboxes, as it groups the options under a single question.

```html
<fieldset>
  <legend>Gender</legend>
  <label><input type="radio" name="gender" value="male"> Male</label>
  <label><input type="radio" name="gender" value="female"> Female</label>
</fieldset>
```

#### Focus Management

Ensure that all form controls are reachable and usable through keyboard navigation. Users should be able to tab through elements in a logical order.
Highlight focus: Make sure the focus state (e.g., when an element is selected/tabbed to) is visually clear.
Input Errors and Validation Feedback
Provide clear, specific error messages and place them where they can be easily associated with the corresponding field.
Use live regions (aria-live) to announce dynamic content changes, such as error messages, so screen reader users are aware when validation errors occur.

### Using ARIA Correctly

ARIA is a set of attributes you can add to HTML elements to communicate roles, states, and properties to assistive technology when native HTML semantics are not sufficient.

#### Basic Principles of ARIA

First Rule of ARIA Use: If you can use a native HTML element or attribute with the semantics and behavior you require, do so.
Role Attribute: Use the role attribute to define what an element is supposed to do. For example, role="button" tells assistive technologies that an element should be treated as a button, even if it isn't a `<button>` tag.

```html
<div tabindex="0" role="button">Click me</div>
```

#### ARIA for Forms

ARIA Labels: Use aria-label or aria-labelledby to provide an accessible name when a visible label cannot be used.

```html
<input type="text" id="fname" aria-label="First name">
```

ARIA Describedby: Use aria-describedby to associate additional descriptive text with a form control, particularly useful for providing hints or error messages.

```html
<input type="text" id="email" aria-describedby="emailHint">
<div id="emailHint">Your email will not be shared with anyone.</div>
```

#### Managing Focus and State

ARIA Live Regions: Use aria-live to make dynamic content changes accessible, as mentioned earlier for form validation messages. The aria-live attribute can be set to different values (off, polite, assertive) depending on the urgency of the update.

```html
<div aria-live="polite">Content updates will be announced.</div>
```

ARIA States: Attributes like aria-expanded, aria-selected, and aria-checked communicate the state of interactive components (e.g., dropdowns, selected tabs, checkboxes) to assistive technologies.

```html
<button aria-expanded="false">More options</button>
```

## Meta Tags and Responsiveness

```html
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="description" content="A brief description of your page">
  <meta name="author" content="Author's Name">
  <meta name="keywords" content="HTML, CSS, JavaScript">
  <link rel="icon" href="favicon.ico" type="image/x-icon">
</head>
```

## Microdata

Enhance SEO and machine readability with microdata by using Schema.org Vocabulary.

```html
<div itemscope itemtype="http://schema.org/Person">
  <span itemprop="name">Jane Doe</span>
  <span itemprop="jobTitle">Web developer</span>
  <div itemprop="address" itemscope itemtype="http://schema.org/PostalAddress">
    <span itemprop="streetAddress">123 Main St</span>,
    <span itemprop="addressLocality">Anytown</span>,
    <span itemprop="addressRegion">CA</span>
  </div>
  Phone: <span itemprop="telephone">+1234567890</span>
  Email: <a href="mailto:jane.doe@example.com" itemprop="email">jane.doe@example.com</a>
</div>
```

## Performance Optimization

Use async or defer attributes with `<script>` tags to control the loading and execution of JavaScript.
Optimize images using appropriate sizes and formats.

## Events

### Window / Load Events

load: Fired when the whole page has loaded, including all dependent resources such as stylesheets and images.
DOMContentLoaded: Fired when the DOM is fully loaded and parsed, but without waiting for stylesheets, images, and subframes to finish loading.
unload: Fired when the document is being unloaded (e.g., when navigating to another page).
beforeunload: Fired before the document is about to be unloaded, allowing the opportunity to ask the user for confirmation if needed.
resize: Fired when the document view (window) has been resized.
scroll: Fired when the document is scrolled.

### Form Events

submit: Fired when a form is submitted.
reset: Fired when a form is reset.
change: Fired when the value of a form element (e.g., input, select) has been changed.
input: Fired when the value of an `<input>`, `<select>`, or `<textarea>` element is changed.
focus: Fired when an element receives focus.
blur: Fired when an element loses focus.
focusin: Fired when an element is about to receive focus.
focusout: Fired when an element is about to lose focus.

### Keyboard Events

keydown: Fired when a key is pressed down.
keypress: Fired when a key is pressed down and that key normally produces a character value (deprecated).
keyup: Fired when a key is released.

### Mouse Events

click: Fired when a mouse button is clicked.
dblclick: Fired when a mouse button is double clicked.
mousedown: Fired when a mouse button is pressed down.
mouseup: Fired when a mouse button is released.
mousemove: Fired when the mouse is moved.
mouseover: Fired when the mouse enters an element.
mouseout: Fired when the mouse leaves an element.
mouseenter: Fired when the mouse enters an element (does not bubble).
mouseleave: Fired when the mouse leaves an element (does not bubble).

### Drag & Drop Events

drag
dragstart
dragend
dragover
dragenter
dragleave
drop

### Clipboard Events

cut
copy
paste

### Touch Events

touchstart
touchmove
touchend
touchcancel

## Security

1. Use HTTPS for Resources
Always use HTTPS URLs for embedding resources (images, scripts, CSS files, etc.) in your HTML documents. This prevents man-in-the-middle attacks and ensures the integrity and confidentiality of the data between the user's browser and the server.

2. Escape User Input
When displaying user-generated content, ensure that any HTML or JavaScript is properly escaped. This prevents Cross-Site Scripting (XSS) attacks, where an attacker could inject malicious code into your web pages. Although primarily a server-side concern, when generating HTML dynamically (e.g., via JavaScript), make sure to sanitize input.

3. Use the rel="noopener" Attribute on External Links
When using target="_blank" on `<a>` tags for external links, add rel="noopener" (or rel="noreferrer", which also prevents the Referer header from being sent). This prevents the newly opened page from having access to the original page's window object, mitigating potential security risks.

```html
<a href="https://example.com" target="_blank" rel="noopener noreferrer">External Link</a>
```

1. Avoid Inline JavaScript
Inline JavaScript (e.g., `<button onclick="...">`) can make it harder to implement a strong Content Security Policy (CSP). CSP is a security layer that helps detect and mitigate certain types of attacks, including XSS and data injection attacks. Instead, attach event listeners to elements using external JavaScript files.

1. Implement Content Security Policy (CSP)
CSP allows you to specify which sources are trusted for content like scripts, styles, and images. Implementing CSP can significantly reduce the risk of XSS attacks. CSP is implemented through an HTTP header, but understanding the types of content your HTML pages load will inform your CSP policy.

1. Use Subresource Integrity (SRI)
When including third-party resources, such as scripts or stylesheets, use Subresource Integrity (SRI) to ensure that the files fetched from CDN or external servers have not been tampered with. This involves adding a sha integrity attribute to your <script> and <link> tags.

```html
<script src="https://example.com/script.js" integrity="sha384-OgVRvuATP0bJFfikXjFaP0S8gJ3u7JWgzoVjE7kBwlnaP0i2s2L0iQBrewCovXC6" crossorigin="anonymous"></script>
```

7. Limit Use of Iframes
Iframes can be used for clickjacking attacks, where an attacker tricks a user into clicking on something different than what the user perceives. Use the X-Frame-Options HTTP header to control whether your site can be framed. Also, consider setting the sandbox attribute on iframes to restrict the actions that content can perform.

8. Input Validation
Though primarily a server-side concern, ensure all user input is validated both on the client and server-side. Client-side validation can be bypassed, so never rely on it for security.

9. Secure Forms with Autocomplete Attributes
For forms that involve sensitive information (like payment or personal details), use the autocomplete="off" attribute to prevent browsers from storing and auto-filling sensitive information. However, be aware of the usability implications.

10. Regularly Update Dependencies
For any HTML templates or frameworks that depend on JavaScript or CSS libraries, regularly update them to the latest versions. This ensures that any known vulnerabilities are patched.
