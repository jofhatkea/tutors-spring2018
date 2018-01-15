# tutors-Spring 2018
## New stuff that you might not know (yet)

# HTML
## The `<template>` tag

# CSS
We're working with two new layout systems (Bootstrap is gone, but probably still used)

## CSS Flexbox
https://css-tricks.com/snippets/css/a-guide-to-flexbox/

## CSS grid
https://css-tricks.com/snippets/css/complete-guide-grid/

# Other stuff
## JSON
You do remember JSON, right?

## git
We're using a plugin for brackets called `Brackets Git`, but the goal is to switch to the terminal (my goal)

## WP REST API
WordPress theming is gone, now we're using the WP REST API to fetch data.

It's a big, and somewhat complex topic, you can take a look at [https://kea-alt-del.dk/courses/t7/2-wp-rest-api.php](these slides) to get up and running. We could also hold a "tutors-only-masterclass"?

# JavaScript
## fetch
AJAX done right. Take a look at the final example, then google it.

## let / const
Two new types of variables, take a look at [https://github.com/jofhatkea/jsdic#variables-let-const--var](https://github.com/jofhatkea/jsdic#variables-let-const--var) or google it

# An example incorporating the whole JS-shebang
## the html
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta http-equiv="X-UA-Compatible" content="ie=edge">
  <title>Document</title>
</head>
<body>

  <div id="app"></div>

  <template id="articletemplate">
    <h2 class="articleheader"></h2>
    <div class="description"></div>
  </template>
  <script src="somescript.js"></script>
</body>
</html>
```

## The JSON
```json
[
  {
    "header": "JS",
    "description": "bla, bla"
  },
  {
    "header": "HTML",
    "description": "yada yada"
  }
]
```

## The JavaScript
```javascript
window.addEventListener('load', start);

let template = document.querySelector("#articletemplate").content;
let daddy = document.querySelector("#app");
function start(){
  fetch("json.json")
    .then(e=>e.json())
    .then(gotData)
}

function gotData(data){
  data.forEach(showOneArticle);
}

function showOneArticle(article){
  let clone = template.cloneNode(true);
  clone.querySelector(".articleheader").textContent=article.header;
  clone.querySelector('div').textContent=article.description;
  daddy.appendChild(clone)
}
```
