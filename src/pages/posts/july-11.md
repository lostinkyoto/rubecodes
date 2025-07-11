---
layout: ../../layouts/MarkdownPostLayout.astro
title: 'Dev Log – Learning about Tailwind, Media Queries, HTML Tags & JavaScript Methods'
pubDate: 2025-07-11
description: 'A haphazard but honest record of what I learned today: Tailwind dark mode, media queries, semantic HTML, and the nature of JavaScript methods.'
author: 'Akila'
image:
url: '[https://docs.astro.build/assets/hero-light-mode.webp](https://docs.astro.build/assets/hero-light-mode.webp)'
alt: 'Illustration representing frontend development topics like Tailwind and JavaScript.'
tags: \['q and a style notes', 'tailwind', 'astro', 'css', 'html', 'javascript', 'learning in public']
---


## Q\&A Style Notes

### Q. can i use tailwind in an astro project for only dark/light mode implementation? does it do so without js? does this make the code faster without weighing it down by using tailwind in other areas \[as tailwind is slow generally?]. are there better options than tailwind that are light weight and implement dark and light with ease without too much or any js?

A. it does implement dark mode without js. and thats good because i want to keep things light? why does js make things 'heavy'?

> "So: **If you only use a few Tailwind classes**, and purge unused ones, your CSS bundle can be **extremely small (e.g., 5–10 KB)**."

* whats a small or large size for css bundle?
* can i purge unused css classes without usin tailwind? just like, normally?

**TIL:** `prefers-color-scheme` is a Css thing i can use directly.

* its a "**CSS media feature**"
  {whats that? part of css media query that applies styles conditionally}
  (whats **media query** - ive seen it and ive used it but what is it? rule that applies styles when some condition abt device is true - i think of t like a class of its own)

```css
@media media-type and (media-feature) {}
```

media-type: `all`, `screen`, `print`, `speech`
media-feature: `min-width`, `max-width`, `orientation`, `aspect-ratio`, `resolution`, `hover`, `pointer`, `prefers-color-scheme`, `prefers-reduced-motion`

### Q. why would i use orientation, aspect ratio? why would I use hover inside a media query when I can use it as a psuedo class?

A.

```
orientation - for video player.

aspect ratio - games/videos render properly
{do different devices have different aspect ratios of visible screen space? - yes. most common in phones - 20:9 (android) or 19.5 instead of 20 {why u do dis apple?}, 16:9 for laptops and tvs, 16:12 or 10 for tablets}
```

Use media query for hover to prevent hover effects from applying on touchscreens

```css
@media (hover: hover)  /* Target devices with hover */
@media (hover: none)   /* Target devices without hover */
```

### Q. what is a <button> in html?

A. element is used to create a clickable button
Types: submit, reset, button
Submit and reset for forms (inside forms automatically button is submit button)

### Q. how in a form to tell button where to submit form? also what are all the elements in html? what's this onClick business?

A1.

A2. all the elements - ones i didnt know - ANOTHER PAGE

<base>

QA2. whats the difference between meta and head? between section, article and main?

AA2. meta always placed inside head
AAA2. encoding - how text/characters is represented in bytes

A3. onclick - what js code or function will run on clicking button.

```
CHECK: seems to me there are 2 ways to do this onclick business.
either in the button tag, say onclick="somejsfunction()" and define the function inside a script tag.
or. give the button an id. then in script tag do getElementById and fetch button. to this add event listener for click. then define what to do when clicked.
```

What to use when? latter for code separation and multiple event listeners on same thing.

### Q. what all can i do with onclick?

A. (tbd - still exploring)

### Q. what is a predefined JavaScript method?

A. functions already provided by js, use directly no need to define.

### Q. why are they called methods and not functions?

A. method is a function that belongs to an object
(ie property of object)

js built-in utilities called methods cause associated with js objects like push() is method of Array object so arr.push() to use it.

### Q. so in document.getElementById is document the object? what are js objects?

A1. yes.
A2. collection of properties as key-value pairs (x\:y, watch for colon inside {} x is key, y value). y can be js function.

### Q. common js objects are predefined objects? what are the ones relevant to web?

A.

```
window (browser window)
document (DOM)
navigator (which browser)
location (page URL)
history (browser session history)
console
```

### Q. window document difference? why do i need to know navigator? what would i use location or history for?

A1.

```
window: whole house
document: blueprint (rooms, furniture)
```

A2.

```
check if online
detect language
detect if cookies enabled
```

A3. control navigation without reloading

### Q. Go N pages in history history.go(-2) - when would I use this? why not let browser handle?

A. run logic before navigation - like save data or show message - in multistep forms, to cancel actions like edit details

### Q. why do main, article, and section need to be 3 different things? it seems like main contains articles and sections?

A.

```
main: one per page - wraps everything meaningful
article: self-contained, reusable, complete without the context of the site
section: grouped, "should have a heading"
```

### Q. why?

A.

```
Understandable for humans
Navigable for screen readers
Semantically correct for search engines and other tools
```

### Q. what does it mean "navigable" and "semantically correct"?

A1.

```
Screen readers can press H key to jump between headings
Headings are announced as landmarks
```

A2.

```
Semantically correct - SEO, Machine interpretation, code readability
```

### Q. what's machine interpretation?

A. Google, screen readers, and browsers to understand your site’s structure and meaning - to rank, render properly (how?)
A. default styles, automatic spacings, cleaner DOM so fast, better with modern layouts like grid and flexbox.


can I use tailwind for dark/light without js --> yes
    --> why?
        --> js heavy --> why?
        --> makes small css bundle --> what's a small or large size for css bundle?

tailwind dark/light code --> prefers-color-scheme
    --> what's this?
        --> css media feature --> what's that?
            --> part of css media query --> what's media query?
                --> rule that applies styles when condition abt device is true

media features --> orientation --> why use?
                             --> for video player
                --> aspect-ratio --> why use?
                                  --> diff devices have diff aspect ratios
                --> hover --> why in media query not pseudo class?
                          --> media query hover prevents hover on touch devices

<button> in html --> types: submit, reset, button
form button --> how to tell where to submit?
             --> what's onclick?
                 --> 2 ways: inline attr OR addEventListener
                     --> when to use what?
                     --> what all can I do with onclick?

html elements --> <base> (new to me)
               --> meta vs head?
                   --> meta: encoding, etc
               --> section vs article vs main?
                   --> main: 1 per page, wraps content
                   --> article: self-contained
                   --> section: grouped content w/ heading
                       --> why?
                           --> understandable
                           --> navigable for screen readers
                           --> semantically correct
                               --> what's machine interpretation?
                                   --> SEO, screen readers, render styles/layout better

predefined js method --> what's that? --> functions provided by js
    --> why 'method' not 'function'?
        --> method = function belonging to object

document.getElementById --> is document an object? --> yes
    --> what's an object in js?
        --> key:value pairs, can include function

common js objects --> window, document, navigator, location, history
    --> window vs document?
        --> window: whole house
        --> document: blueprint
    --> why navigator?
        --> detect language, online status, cookies
    --> location --> get/change URL
    --> history --> go back/forward
        --> history.go(-2) --> why not let browser handle?
            --> run logic before leaving page

| **Term**                 | **Language** | **Type**                 | **My Definition**                                         |
| ------------------------ | ------------ | ------------------------ | --------------------------------------------------------- |
| **prefers-color-scheme** | CSS          | media feature            | tells browser to apply dark/light based on system setting |
| **media query**          | CSS          | rule                     | applies styles based on device conditions                 |
| **media feature**        | CSS          | condition in media query | checks things like width, orientation, hover, etc         |
| **method**               | JS           | function on object       | e.g. `arr.push()` - function attached to an object        |
| **object**               | JS           | data structure           | key-value pairs inside `{}` where value can be a function |
| **document**             | JS           | DOM object               | represents HTML content of the page                       |
| **window**               | JS           | browser object           | represents the whole browser window                       |
| **navigator**            | JS           | browser object           | info about browser environment (lang, cookies, online)    |
| **location**             | JS           | browser object           | current page URL, can change or read it                   |
| **history**              | JS           | browser object           | lets you go back/forward in session history               |
| **onclick**              | JS           | event                    | code to run when something is clicked                     |
